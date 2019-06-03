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

## Managing Sessions

### Setting the cart

On every page load, the cart content _must_ be passed. The cart contents are the 1:1 representation of the user's mini-cart.

The cart information is used by the Nosto to tailor the recommendations, dispatch abandoned cart emails and fire Facebook pixel events for retargeting purposes.

```js
nostojs(api => {
  api.defaultSession()
   .setCart({
     items: [
      {
        name: "Men's Running Shirt",
        price_currency_code: "EUR",
        product_id: "181503",
        quantity: 2,
        sku_id: "181505",
        unit_price: 123.45
      },
      {
        name: "Men's Training Shoe",
        price_currency_code: "EUR",
        product_id: "34552",
        quantity: 1,
        sku_id: "39912",
        unit_price: 999.00
      }
    ]
   })
});
```

**Note:** Passing `null` or `undefined` will prevent the cart contents from being mutated on Nosto. Passing an empty object `{}` will reset the cart contents.

### Setting the customer

On every page, the customer information _should_ be passed if the customer is logged in. If the customer isn't logged in, this but can be omitted.

The customer information is primarily used for sending personalised triggered emails and for building multi-channel experiences.

```js
nostojs(api => {
  api.defaultSession()
    .setCustomer({
      customer_reference: "b369f1235cf4f08153c560.82515936",
      email: "mridang@nosto.com",
      first_name: "Mridang",
      last_name: "Agarwalla",
      newsletter: true
    })
});
```

**Note:** Passing `null` or `undefined` will prevent the customer information from being mutated on Nosto. Passing an empty object `{}` will reset the customer information.

## Tracking Events

### When viewing the homepage

When viewing a home-page, there's no context to be provided, so invoking the `viewIndex` will suffice.

```js
nostojs(api => {
  api.defaultSession()
    .viewIndex()
    .setElements(['product-crosssells'])
    .load()
    .then(data => {
      console.log(data.recommendations);
    })
});
```


### When viewing a product

When viewing a product, you should send the product-id of the current product being viewed.

```js
nostojs(api => {
  api.defaultSession()
    .viewProduct('product-id')
    .setElements(['product-crosssells'])
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
    .setElements(['category-related'])
    .load()
    .then(data => {
      console.log(data.recommendations);
    })
});
```

**Note:** You don’t need to ensure the case-sensitivity of the category being passed so long as the path is tagged in the same way as your product’s categories are.

### When doing a search

When viewing the results of a search, you must send the exact search-term as queried for.

```js
nostojs(api => {
  api.defaultSession()
    .viewSearch('womens dresses')
    .setElements(['search-related'])
    .load()
    .then(data => {
      console.log(data.recommendations);
    })
});
```

**Note:** You don’t need to normalize or encode the search query in any way.

### When going to checkout

When viewing a checkout page, there's no context to be provided, so invoking the `viewCheckout` will suffice.

```js
nostojs(api => {
  api.defaultSession()
    .viewCheckout()
    .setElements(['cart-related'])
    .load()
    .then(data => {
      console.log(data.recommendations);
    })
});
```

### When placing an order

On all thank-you and order-confirmation pages, the conversion metadata _must_ be passed. 

The conversion metadata is used for sending personalised order-followup emails, personalise the recommendations e.g. order-related, for segmentation insights and conversion statistics.

```js
nostojs(api => {
  api.defaultSession()
    .placeOrder(
      {
        "external_order_ref": "145000006",
        "info": {
          "order_number": "195",
          "email": "mridang@nosto.com",
          "first_name": "Mridang",
          "last_name": "Agarwalla",
          "type": "order",
          "newsletter": true
      },
      "items": [
        {
          "product_id": "406",
          "sku_id": "243",
          "name": "Linen Blazer (White, S)",
          "quantity": 1,
          "unit_price": 455,
          "price_currency_code": "EUR"
        }
      ]
    })
    .setElements(['order-related'])
    .load()
    .then(data => {
      console.log(data.recommendations);
    })
});
```





How do I consume the recommendation response?
How do I reload the recommendations?
How do I send a recommendation clicked event?
How do I sent an add to cart event?

