While Nosto's crawler attempts to keep its copy of your catalog as fresh as possible, there are scenarios where we may not be able to update all the information as quickly as needed.

In these scenarios, we recommend that you implement our lightweight Recrawl API which allows you programmatically instruct our crawler to reindex a given URL.

For example, if you add a discount of -10% to all the products in your "Shirts" category, you can use the Recrawl API to recrawl all the given URLs and update the prices.

Here's an example of a Curl request.

```
curl -v --user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw -H "Content-Type: application/json" -X POST https://api.nosto.com/products/recrawl -d '{  
  "products":[  
    {  
      "productId":"339",
      "url":"https://magento1.plugintest.nos.to/retro-chic-eyeglasses.html?___store=default"
    }
  ]
}
```

### How many items can I recrawl at a time?

The Recrawl API takes an array of product ids and URLs and has no hard limit on the number of items that you can specify.

### How often can I invoke a recrawl?

You can recrawl as often as you need but bear in mind that every recrawl adds an extra page load to your server.