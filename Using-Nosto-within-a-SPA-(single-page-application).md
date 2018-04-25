Using Nosto within a SPA (single-page-application) is entirely possible. However due to Nosto more or less expecting a static environment with all information accessible on page load you will need to define Javascript calls manually within your own functions.

### Direct including Nosto:

To initialize Nosto you will only need to add the Nosto embed script and the Nosto Javascript stub that initializes the service. You can use the optional disableAutoLoad if you want to have full control on when recommendations are populated. 

HTML
```html
<script src="//connect.nosto.com/include/$accountID" async></script>
```

Javascript
```js
nostojs.init("nostoAccountId", {disableAutoLoad:true});
```

After doing these steps you can test if the nostojs API is available by testing a simple command. Make sure that the url in the Nosto admin UI matches the page source from where the call is made. 

Javascript
```js
nostojs(function(api){ console.log("API is functional"); });
```

### Sending requests manually with Nostojs

You will need to go through the entire tagging approach listed under [Manual Implementation](https://github.com/Nosto/docs-nosto-com/wiki/Manual-implementation) to structure the metadata on the page in a digestable format. You can utilize one of two available functions to send the tagging to Nosto.

Javascript
```js
nostojs(function(api){
  api.sendTagging();
});

nostojs(function(api){
  api.loadRecommendations();
});
```

The function `api.sendTagging();` will send all Nosto tagging on the page without any modifications to onpage content. However the function `api.loadRecommendations();` will both send the tagging and request recommendations for any recommendation slots currently on the page. 

Using `disableAutoLoad:true` in the initialization phase will prevent Nosto recommendations being fetched on initial connection so in this case you would need to use `api.loadRecommendations();` directly when initial page content has loaded. Best practice in terms of functionality would be to omit or set `disableAutoLoad:false` on initial page load, utilizing `api.sendTagging();` whenever a unique pageLoad happens and only using `api.loadRecommendations();` when the change in tagging will also lead to a change in fetched recommendations (for example a add to cart event leading to a change in cart based recommendations). 

> **Note:** Both autoload, sendTagging and loadRecommendations all send tagging, productView, addToCart and 
> productPurchased events automatically as long as the required tagging is available on the page. 
