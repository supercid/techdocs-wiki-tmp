If you want to expose Nosto in a dynamic overlay that either is created upon a certain action, or exposed for example on a event you will need to utilize the Nosto Javascript API and refresh the exposed recommendations. JavaScript API works only in on-site context. Using the API does not require authentication but requires [Adding the Nosto Script](Add-Nosto-script). 

### Exposing Nosto elements in a dynamic overlay on site. 

If you were to expose a overlay you first need to add a `<div class="nosto_element" id="overlay-nosto-1"></div>` within the code you are either modifying or creating. Whenever your function that creates or modifies the overlay triggers you can utilize the callback function to also go ahead and reload the Nosto recommendations to match the current event status. 

Example of how a overlay with Nosto recommendations could work:

```html
<div style="display: none;" id="overlay">
  <h3>You have succesfully added a product to cart!</h3>
  <div class="nosto_element" id="overlay-nosto-1"></div>
</div>

<button id="add-to-cart" onclick="showOverlay()">Add to cart!</button>
```
```javascript

function showOverlay(callback) {
    var overlay = document.getElementById("overlay"); // Get overlay
    overlay.style.display = "block"; // Expose overlay
    callback(); // Trigger callback function to reload Nosto recommendations
}

showOverlay(function() { 
    // Use nostojs to loadRecommendations. The function both updates tagging and fetches new recommendations to 
    match changes in the tagging (for example changing the cart contents)

    nostojs(function(api){ 
       api.loadRecommendations();
    });
});

```