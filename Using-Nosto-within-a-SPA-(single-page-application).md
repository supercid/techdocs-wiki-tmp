Using Nosto within a SPA (single-page-application) is entirely possible. However due to Nosto more or less expecting a static environment with all information accessible on page load you will need to define Javascript calls manually within your own functions.

### Direct including Nosto:

To initialize Nosto you will only need to add the Nosto embed script and the Nosto Javascript stub that initializes the service. You can use the optional disableAutoLoad if you want to have full control on when recommendations are populated. 

HTML
```html
/* Nosto direct include script */
<script src="//connect.nosto.com/include/$accountID" async></script>
```

Javascript
```js
/* Initalize Nostojs, disableAutoLoad is a optional parameter and False by default */
nostojs.init("nostoAccountId", {disableAutoLoad:true});

/* Create a stub called nostojs to access Nosto JS API */
(function(){
 var name="nostojs";
 window[name]=window[name]||function(cb){(window[name].q=window[name].q||[]).push(cb);};
})();

//Your code using the Nosto JS API
//...
```

After doing these steps you can test if the nostojs API is available by testing a simple command. Make sure that the url in the Nosto admin UI matches the page source from where the call is made. 

Javascript
```js
nostojs(function(api){ console.log("API is functional"); });
```

### Dynamically updating tagging components

In most SPA implementations this section of the guide is enough since Nosto aims to automatically send events while you can have control on when these are manually sent and also when recommendation elements should be populated on page. 

You will need to go through the entire tagging approach listed under [Manual Implementation](https://github.com/Nosto/docs-nosto-com/wiki/Manual-implementation) to structure the metadata on the page in a digestable format. 

You can utilize one of two available functions to send the tagging to Nosto.

Javascript
```js

/* Call will read the page’s tagging information again and send it to Nosto. If for example the shopping cart information is tagged on the page, it will also update the visitor’s shopping cart. */ 

nostojs(function(api){
  api.sendTagging();
});

/* Refreshes the recommendations on the page and reports a new page view or product view if the page’s DOM contains the product tagging. Which recommendations to update will be searched from the page DOM by finding all elements where the class is “nosto_element” and then getting their id attributes. */

nostojs(function(api){
  api.loadRecommendations();
});
```

The function `api.sendTagging();` will send all Nosto tagging on the page without any modifications to onpage content. However the function `api.loadRecommendations();` will both send the tagging and request recommendations for any recommendation slots currently on the page. 

Using `disableAutoLoad:true` in the initialization phase will prevent Nosto recommendations being fetched on initial connection so in this case you would need to use `api.loadRecommendations();` directly when initial page content has loaded. 

Best practice in terms of functionality would be to omit or set `disableAutoLoad:false` on initial page load and only using `api.loadRecommendations();` when a change in tagging will also lead to a change in fetched recommendations (for example a add to cart event leading to a change in cart based recommendations). 

> **Note:** Both autoload, sendTagging and loadRecommendations all send tagging, productView, addToCart and 
> productPurchased events automatically as long as the required tagging is available on the page. 

### Creating full requests manually

You can also create requests manually specifying events and slots to be populated within the call. This should be done only in cases where you have done the previous step and concluded that either Nosto is not properly sending events or you want to have more granular control of what is happening in the page context. 

Javascript
```js
/* To create manual requests, first thing is to create a recommendation request object. */

nostojs(function(api){
  var request = api.createRecommendationRequest();
});

/* Following example creates a new request, adds view product event for productId3 and sends the event to Nosto. Request did not specify any recommendation slots, this request only submits view event to Nosto. */

nostojs(function(api){
  var request = api.createRecommendationRequest();
  request.addEvent('vp', "productId3");
  request.loadRecommendations(request);
});

/* Following is a more complex example which submits more information in single request to Nosto. */ 

nostojs(function(api){
   var request = api.createRecommendationRequest();
   request.addElements(["nosto-product-page1", "nosto-product-page2"]);
   // if viewed from nosto element, add element's id as 3rd. parameter
   request.addEvent('vp', "productId3", "nosto-categorypage-1");
   request.addCartItems(["productId1", "productId2"]);
   request.loadRecommendations();
});
```

> **Note:** The product ID of the product tagging, cart tagging and order tagging must match. Failure to do so will > lead to a mismatch in both attribution and statistics across the Nosto product.

You can find the full API documentation for this section here: https://developer.nosto.com/?javascript#creating-requests-manually

### Utilizing postrender callback to track, influence or render Nosto recommendations on page

Nosto leverages a callback called `postrender` to give implementors an easy way to hook onto Nosto recommendation elements after recommendations have been populated. Using this functions you can easily track what elements have been populated, change the layout depending on results or if you are outputting the results as pure JSON you can render the whole layout within your framework.

Javascript
```js
/* Following script executes at the post-render callback. which is called right after Nosto has responded with recommendations. */ 

nostojs(function(api){
    api.listen('postrender', function(nostoPostRenderEvent){
        console.log(nostoPostRenderEvent.filledElements);
        console.log(nostoPostRenderEvent.unFilledElements); 
    });
});

/* Post render callback is useful in situations when recommendation markup is rendered client-side (Browser) e.g. with customizations that are simpler to handle client-side. */ 

// Extract recommendation 
(function () {
    // Callback which connects to postrender callback
    // loads the raw data from recommendations,
    // and finally converts the data to JSON object.
    function exampleCallHandler(filledElements) {
        // Extract the data from nosto DIV
        var data = document.getElementById("nosto-recommendation-example");
        var jsonObject;
        if (data) {
            jsonObject = JSON.parse(data.textContent);
            ExampleRecommendationDecorator.decorateNostoSlot("nosto- recommendation - example", jsonObject);
        }
    }

    // Register the handler to post render
    nostojs(function (api) {
        api.listen("postrender", function (NostoPostRenderEvent) {
            exampleCallHandler(NostoPostRenderEvent.filledElements);
        });
    });
})();
```

You can find the full API documentation for this section and other callbacks as well here: https://developer.nosto.com/?javascript#callbacks
