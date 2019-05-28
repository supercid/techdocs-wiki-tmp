# Documentation

## Setting Up

### Including the script

To start tracking visits and content the Nosto script needs to be active on all pages within the store where the user might navigate. Replace $accountID from the code below with your own account ID and place the code within the <head> section of your sites HTML content. You can find your stores account IDs from the account list within the Nosto admin.

```html
<script type="text/javascript">
(function(){var name="nostojs";window[name]=window[name]||function(cb){(window[name].q=window[name].q||[]).push(cb);};})();
</script>
<script src="//connect.nosto.com/include/$accountID" async></script>
```

**Note:** The script should be added as high up in the <head> portion of the page so the connection is initialised as soon as possible. As the script is flagged async, the page load isn’t delayed.
Note: This needs to exist on every page.


### Disabling autoload

In order to prevent Nosto from automatically initializing once the script is loaded, you’ll need to disable autoloading.

```js
nostojs.init("account-id", { disableAutoLoad:true });
```

**Note:** This needs to exist on every page.

## Tracking Events

### When viewing a product

When viewing a product, you should send the product-id of the current product being viewed.

```js
nostojs(api => {
  api.defaultSession()
   .viewProduct('product-id')
   .setElements(['frontpage-bestsellers'])
   .load()
   .then(data => {
     console.log(data.recommendations);
   })
});
```

### When viewing a category or a collection

When viewing a category or collection, you should send the slash-delimited and fully-qualified path of the current category.

```js
nostojs(api => {
  api.defaultSession()
   .viewCategory('/Womens/Dresses')
   .setElements(['frontpage-bestsellers'])
   .load()
   .then(data => {
     console.log(data.recommendations);
   })
});
```

**Note:** You don’t need to ensure the case-sensitivity of the category being passed so long as the path is tagged in the same way as your product’s categories are.





How do I consume the recommendation response?
How do I reload the recommendations?
How do I send a recommendation clicked event?
How do I sent an add to cart event?


