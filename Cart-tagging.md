Cart tagging is a series of meta attributes that describe the contents of the shopping cart for Nosto. The service incorporates a crawling mechanism that collects and stores these products in our catalogue for use within the different delivery methods of Nosto. Cart tagging lets Nosto track add to cart events and also use the cart contents to tailor recommendations and utilise the data for other feature types like triggered emails or Facebook retargeting. 

Please note that the meta attributes need to exist within the page source when the page has rendered and Nosto is unable to crawl details injected via Google Tag Manager or other dynamic sources based on Javascript.

The cart tagging should be looped out whenever the user has added something in the cart and the information is loopable into the source code. This should be looped out on all pages and not just on the cart page so Nosto can pick up abandoned cart events in all possible situations. 

```html
<div class="nosto_cart" style="display:none">
 
    <div class="line_item">
        <span class="product_id">Canoe123</span>
        <span class="quantity">1</span>
        <span class="name">Acme Canoe</span>
        <span class="unit_price">999.00</span>
        <span class="price_currency_code">EUR</span>
    </div>
 
    <div class="line_item">
        <span class="product_id">Canoe245</span>
        <span class="quantity">3</span>
        <span class="name">Acme Large Canoe</span>
        <span class="unit_price">19.00</span>
        <span class="price_currency_code">EUR</span>
    </div>
 
</div>

```
If the platform itself has support for persistent shopping cart or other technologies that remember the users cart contents you do not need to worry about filling out the cart when a user returns to the site. If your platform generates a restore cart link you can also send that to Nosto by adding it as a new attribute within the parent container "nosto_cart". 

```html
<div class="restore_link">https://example.com/cart/restore?cart=4D5C3060-1334-4C63-B6FA-D9D342D88B08</div>
```

**Troubleshooting cart tagging:**

Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If you can see cart contents being picked up under "Tagging" → "Cart" then the cart details are correctly set up in the source code. You can further verify your session in the Nosto admin by using the live feed under: https://my.nosto.com/admin/$accountID/liveFeed to see if Nosto correctly picks up product view → product carted events. 

![Nosto debug toolbar cart](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-embed-script-cart.png)