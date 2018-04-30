In many cases a store might have a dynamic add to cart button that triggers an event without a page load. Supporting this use case in Nosto is trivial but needs a few lines of Javascript to function. JavaScript API works only in on-site context. Using the API does not require authentication but requires [Adding the Nosto Script](Add-Nosto-script).

### Dynamically refreshing Nosto after an add-to-cart event

You can either refresh the cart tagging or use an all-in one function to both refresh the tagging and fetch new recommendations if you are using the `cart-based recommendation` type for example to get exakt results immediately after a user has clicked the add-to-cart button. 

Below is a basic example on how the add-to-cart events can be sent to Nosto: 

HTML
```html
<button id="add-to-cart" onclick="productCarted()">Add to cart!</button>
```

Javascript
```javascript

function productCarted(){
// Here you add your code that adds the product to the shopping cart.
loadNosto(); // Trigger function to reload Nosto recommendations
}

function loadNosto(){
  // Use nostojs to loadRecommendations.

  /* sendTagging function updates the tagging for the current session but does not refresh recommendations so if you are exposing for example cart-based recommendations in a overlay they would show the old results */ 

  nostojs(function(api){
     api.sendTagging();
  });

  /* loadRecommendations function both updates tagging and fetches new recommendations to match changes in the tagging. This function would be used if you aim to update recommendations after add-to-cart event. */ 

  nostojs(function(api){
     api.loadRecommendations();
  });
}

```