Order tagging is a series of meta attributes that notify Nosto of what products finally ended up in a finalised order. The order tagging should be outputted on the order-thank-you page after a customer has finalized payment. If you are using a 3rd party payment provider and you do not have edit access to your order-thank-you page please reach out to Nosto support or your assigned Technical Solutions Manager for further assistance in setting up the tracking. 

Please note that the meta attributes need to exist within the page source when the page has rendered and Nosto is unable to crawl details injected via Google Tag Manager or other dynamic sources based on Javascript.

```html
<div class="nosto_page_type" style="display:none">order</div>
<div class="nosto_purchase_order" style="display:none">
    <span class="order_number">1445</span>
 
    <div class="buyer">
        <span class="email">john.doe@example.com</span>
        <span class="first_name">John</span>
        <span class="last_name">Doe</span>
        <span class="marketing_permission">false</span>
    </div>
 
    <div class="purchased_items">
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
</div>
```
> **Note:** The product ID of the product tagging, cart tagging and order tagging must match. Failure to do so 
> will lead to a mismatch in both attribution and statistics across the Nosto product.

### Tagging the buyer

You can omit the buyer tagging completely if you do not want Nosto to crawl this information. The user details are stored for possible marketing purposes and mainly observed email address is used in this context. Marketing permission is false by default but if this user has explicitly agreed to receive marketing then you can set it to true manually.

### Tagging the currencies

Currencies should always be represented in the ISO-4471 three-letter format. For example, use the code `USD` instead of `$` to represent the United States Dollar.

## Troubleshooting order tagging:

Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If you can see order contents being picked up under "Tagging" → "Order" then the order details are correctly set up in the source code. 

You can further verify your session in the Nosto admin by using the live feed under: https://my.nosto.com/admin/$accountID/liveFeed to see if Nosto correctly picks up product view → product carted → product bought events. You can export all the order history from the store under Settings → Other → Order report under https://my.nosto.com/admin/$account/account/orders/report

![Nosto debug toolbar order](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-debug-toolbar-order.png)
![live-feed-product-order](https://nosto-campaign-assets.s3.amazonaws.com/images/live-feed-order.png)
