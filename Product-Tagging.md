 Product tagging is a series of meta attributes that describe the product for Nosto. The service incorporates a crawling mechanism that collects and stores these products in our catalogue for use within the different delivery methods of Nosto. Please note that the meta attributes need to exist within the page source when the page has rendered and Nosto is unable to crawl details injected via Google Tag Manager or other dynamic sources based on Javascript.

```html
<div class=”nosto_product”> 
<!-- Open product tagging. -->
	<span class=”id”>Canoe123</span> <!-- Unique ID of product. -->
	<span class=”name”>Acme Canoe</span> <!-- Name of product. -->
	<span class=”url”>https://example.com/canoe123</span> <!-- Url to product eg. This page.	-->
	<span class=”image”>https://image.example.com/canoe1.jpg</span> <!-- Url to product image. -->
	<span class=”availability”>Instock</span> <!-- Availability eg. Instock, Outofstock, Discontinued. -->
	<span class=”price”>999,00</span> <!-- Current price or price after discount applied. -->
	<span class=”currency-code”>USD</span> <!-- ISO-4471 format eg. USD, EUR, SEK etc.
	<span class=”categories”>/interior</span> <!-- Output associated categories. --> 
	<span class=”categories”>/interior/towels</span> <!-- Also loop out all associated the sub-categories. -->
</div>
<!-- End product tagging. -->
```

Nosto also supports multiple optional values which may enrich the usage of the service, but are not required. These span elements should be inserted into the "nosto_product" parent container.

```html
<span class=”brand>Acme</span> <!-- Brand of the product. -->
<span class=”description”> </span> <!-- Description of the product. -->
<span class=”list-price”>1299,00</span> <!-- Price before discount eg. Regular price used together with the price attribute. -->
<span class=”tag1”>Aluminium</span> <!-- Wildcard attribute that accepts any value you send it. Used mainly for filtering and reporting. -->
<span class=”tag2”>Charcoal Black</span> <!-- Common use-cases for these are colour, material or unique attributes. -->
<span class=”tag3”>Outdoor</span> <!-- Another example on where/how the product can be used. -->
<span class=”tag3”>Canoeing</span> <!-- Tags also accept multiple values on separate lines to denote multiple use-cases for filtering purposes. -->
<span class=”rating-value>3.8</span> <!-- Current rating score of product. -->
<span class=”review-count”>36</span> <!-- How many reviews the above score is based on. -->
<span class=”alternate-image-url”> https://image.example.com/canoe2.jpg</span> <!-- Alternate images of the product that can be used for example on a hover-effect. -->
<span class=”alternate-image-url”> https://image.example.com/canoe3.jpg</span> <!-- Nosto supports mapping of multiple images and these are accessible through templating. -->
```

## Troubleshooting product tagging:
Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If you can see product attributes being picked up under "Tagging" then the product details are correctly set up. You can further verify that products are being indexed to the catalogue under the Nosto admin by navigating to Tools → Products: https://my.nosto.com/admin/$accountID/campaigns/products/list

 