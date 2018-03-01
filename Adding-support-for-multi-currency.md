In this article, you will learn how to implement multi-currency in Nosto. When the implementation is complete, you will be able to display product prices (in any feature) in different currencies to relevant target groups.

Prior to the multi-currency implementation, ensure that the Nosto tagging is correctly in place. Once the tagging has been implemented.

The tagging must be slightly amended to add support for multiple currencies.

## Changes to the product tagging

The product page tagging must be amended to denote the primary currency code of the product. Typically, most retailers have a primary currency which is the default currency of the inventory.

For example, a US-based retailer who sells in Euros (EUR) and Sterling Pounds (GBP) would have US Dollar (USD) as the primary currency while Euro (EUR) and Sterling Pounds (GBP) would be secondary currencies whose exchange rates would need to be sent via an API.

An additional span tag must be placed within the product page tagging with a class name `variation_id`. The tag is a child element of the `nosto_product` element.

```html
<div class="nosto_product" style="display: none;">
  ...
  ...
  ...
  <!-- Variation ID for the primary currency --> 
  <span class="variation_id">USD</span>
</div>
```

> **Note:** The code in the `variation_id` element must remain static, regardless of the currency active on-site. This is the primary currency of your catalog. Although `variation_id` element often has the same currency code as in the `price_currency_code` element and may seem redundant, they support different use cases and both need to be tagged.

## Specifying the active currency

Once you have amended the product tagging, an additional DIV element must be added to all the other pages (including the product page itself). The tag should not be encapsulated in the `nosto_product` DIV tag. The information sent in the tag refers to the currency active of the customer.

```html
<div class="nosto_variation" style="display: none;">USD</div>
```

For example, on the site of a US-based retailer who sells in Euros (EUR) and Sterling Pounds (GBP), if the customer changes the currency to Sterling Pounds (GBP), the `nosto_variation` element should show `GBP`. If the customer changes the currency to Euros (EUR), the `nosto_variation` element should show `EUR`. 

