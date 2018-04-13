Product tagging is a series of meta attributes that describe the product for Nosto. The service incorporates a crawling mechanism that collects and stores these products in our catalogue for use within the different delivery methods of Nosto. 

Please note that the meta attributes need to exist within the page source when the page has rendered and Nosto is unable to crawl details injected via Google Tag Manager or other dynamic sources based on Javascript.

```html
<div class="nosto_product"> 
  <span class="id">Canoe123</span>
  <span class="name">Acme Canoe</span>
  <span class="url">https://example.com/canoe123</span>
  <span class="image">https://image.example.com/canoe1.jpg</span>
  <span class="availability">Instock</span>
  <span class="price">999.50</span>
  <span class="price_currency_code">USD</span>
  <span class="categories">/interior</span>
  <span class="categories">/interior/towels</span>
</div>
```

Nosto also supports multiple optional values which may enrich the usage of the service, but are not required. These span elements should be inserted into the "nosto_product" parent container.

```html
<span class="brand">Acme</span>
<span class="description">This is a great product!</span>
<span class="list_price">1299.00</span>
<span class="tag1">Aluminium</span>
<span class="tag2">Charcoal Black</span>
<span class="tag3">Outdoor</span>
<span class="tag3">Canoeing</span>
<span class="rating_value">3.8</span>
<span class="review_count">36</span>
<span class="alternate_image_url">https://image.example.com/canoe2.jpg</span>
<span class="alternate_image_url">https://image.example.com/canoe3.jpg</span>
<span class="custom_fields">
  <span class="material">Cotton</span>
  <span class="weather">Summer</span>
</span>
```

### Tagging the categories

Categories must always be delimited by a slash. For example, `/Home/Accessories` is a valid category while `Home > Accessories` is not.

### Tagging the currencies

Currencies should always be represented in the ISO-4471 three-letter format. For example, use the code `USD` instead of `$` to represent the United States Dollar.

### Tagging the availability

The availability of a product is represented by `InStock` or `http://schema.org/InStock` for products that are in stock and saleable. For products that are out of stock or you don't want recommended, you can use `OutOfStock` or `http://schema.org/OutOfStock`

### Tagging the Rating

The rating of a product must be represented as a number between 0.0 and 5.0. For example, a product cannot be rated 9.1. You must normalize your rating value to fit our specified range.

### Tagging the Tags

The three tag fields, `tags1`, `tags2` and `tags3` are simply labels that accept any value you give them. Used mainly for filtering and reporting. Common use-cases for these are to annotate colour, material or other grouping attributes.

## Troubleshooting product tagging:
Once included on all pages, you can review if the site is transmitting data using the [Nosto Debug Toolbar](https://help.nosto.com/get-started/guides/how-to-use-the-nosto-debug-toolbar). If you can see product attributes being picked up under "Tagging" then the product details are correctly set up. You can further verify that products are being indexed to the catalogue under the Nosto admin by navigating to Tools → Products: https://my.nosto.com/admin/$accountID/campaigns/products/list


![Nosto debug toolbar / products](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-product-tagging.png)

![Nosto product catalogue](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-product-catalogue.png)

![live-feed-product-view](https://nosto-campaign-assets.s3.amazonaws.com/images/live-feed-view.png)
 