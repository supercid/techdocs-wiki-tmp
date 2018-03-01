In this article, you will learn how to implement multi-variants in Nosto. When the implementation is complete, you will be able to display different products in different prices to the different customer groups.

You will need to implement the multi-variate tagging if you have any such scenarios:

* Your store has different prices for logged-in and logged-out customers
* Your store has different prices for loyalty customers
* Your store has different prices and availabilities for different locations

Prior to the multi-variate implementation, ensure that the Nosto tagging is correctly in place. Some of the tagging must be slightly amended to support multi-variants.

## Changes to the product tagging

The product page tagging must be amended to denote the primary variation code of the product.

For example, a retailer who has different prices for normal and loyal customers would have `GENERAL` as the default variation id and `LOYAL` as an extra variation.

An additional span tag must be placed within the product page tagging with a class name `variation_id`. The tag is a child element of the `nosto_product` element.

```html
<div class="nosto_product" style="display: none;">
  ...
  ...
  ...
  <!-- Variation ID for the primary currency --> 
  <span class="variation_id">GENRAL</span>
  <!-- Variation block for a secondary currency -->
  <div class="variation">
    <span class="variation_id">LOYAL</span>
    <span class="price_currency_code">EUR</span>
    <span class="price">27.00</span>
    <span class="list_price">45.19</span>
    <span class="availability">InStock</span>
  </div>
  <!-- Variation block for a secondary currency -->
  <div class="variation">
    <span class="variation_id">B2B</span>
    <span class="price_currency_code">GBP</span>
    <span class="price">24.00</span>
    <span class="list_price">41.55</span>
    <span class="availability">OutOfStock</span>
  </div>
</div>
```

> **Note:** The code in the `variation_id` element must remain static, regardless of the current context. For example, if a loyal customer is logged in, the `variation_id` field would still `GENERAL` and not change.

### What about the prices in the cart and the order tagging?

The cart and order tagging can be left as-is but the prices must be in the customer's currently active currency. For example, a customer shopping in Swiss Francs (CHF) should have all the cart items tagged in Swiss Francs (CHF). Failure to do so will result in incorrect prices in any triggered emails such as abandoned cart or order followup.