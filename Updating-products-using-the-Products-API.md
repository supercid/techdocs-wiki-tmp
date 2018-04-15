While Nosto's crawler attempts to keep its copy of your catalog as fresh as possible, there are scenarios where we may not be able to update all the information as quickly as needed.

In these scenarios, we recommend that you implement our enhanced Products API which allows you push all your product metadata and have the changes instantly reflect across our entire engine.

For example, if you add a discount of -10% to all the products in your "Shirts" category, you can use the Products API to bulk update all the products.

Here's an example of a Curl request.

```
curl -v --user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw -H "Content-Type: application/json" -X POST https://api.nosto.com/v1/products/upsert -d '{  
  [
    {
      "url":"http://shop.example.com/product/123",
      "product_id":"123",
      "name":"Example product 123",
      "image_url":"http://cdn.example.com/product_123.jpg",
      "price_currency_code":"EUR",
      "availability":"InStock",
      "categories":[
        "sale/summer",
        "shirts"
      ],
      "description":"Example description",
      "price":10.00,
      "list_price":12.34,
      "brand":"Example Brand",
      "tag1":[
        "red",
        "green"
      ],
      "tag2":[
        "women"
      ],
      "tag3":[
        "Foldable"
      ],
      "date_published":"2013-­04-­23",
      "variation_id":"EUR_1",
      "variations":{
        "USD_2":{
          "price_currency_code":"USD",
          "availability":"InStock",
          "price":12.00,
          "list_price":15.67
        },
        "GBP_3":{
          "price_currency_code":"GBP",
          "availability":"OutOfStock",
          "price":20.00,
          "list_price":21.99
        }
      },
      "google_category":"shirts",
      "gtin":"example123",
      "condition":"new",
      "age_group":"adult",
      "gender":"unisex",
      "inventory_level":25,
      "supplier_cost":1312.96
    }
  ]
}'
```

### How can I get an API token?

You can request an API token (API_PRODUCTS) by getting in touch with our support personnel. Once the token has been granted, you will be able to find it listed in the [authentication tokens section in the admin.](https://help.nosto.com/settings-and-troubleshooting-faq/settings-authentication-tokens)

### How many items can I update at a time?

The Products API takes an array of product metadata and has no hard limit on the number of items that you can specify and is only limited by the maximum size of the payload of 2 MB.

### How often can I update products?

You can update products as often as you need.