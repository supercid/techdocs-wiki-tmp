In this article, you will learn how to implement multi-currency in Nosto. When the implementation is complete, you will be able to display product prices (in any feature) in different currencies to relevant target groups.

Prior to the multi-currency implementation, ensure that the Nosto tagging is correctly in place. Once the tagging has been implemented.

The tagging must be slightly amended to add support for multiple currencies.

## Changes to the product tagging

The product page tagging must be amended to denote actual currency code of the product.

Typically, a primary currency has been set for the online store. For example, a US-based retailer who sells in Euros (EUR) and Sterling Pounds (GBP) would have US Dollar (USD) as the primary currency while Euro (EUR) and Sterling Pounds (GBP) would be secondary currencies whose exchange rates would need to be sent via and API.

An additional span tag must be placed within the product page tagging with a class name variation_id. The tag is a child element of the nosto_product div tag.

With the example above, the extended product page would be the following:

```html
<div class="nosto_product" style="display: none;">
  ...
  ...
  ...
  <!-- Variation ID for the primary currency --> 
  <span class="variation_id">USD</span>
</div>

> **Note:** The code in the `variation_id` element must remain static, regardless of the currency active on-site. This is the primary currency of your catalog.

