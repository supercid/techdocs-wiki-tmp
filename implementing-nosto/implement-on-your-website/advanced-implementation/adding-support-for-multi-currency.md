# Adding support for multi-currency

In this article, you will learn how to implement multi-currency in Nosto. When the implementation is complete, you will be able to display product prices \(in any feature\) in different currencies.

Prior to the multi-currency implementation, ensure that the Nosto tagging is correctly in place. Some of the tagging must be slightly amended to support multi-currency.

## Shopify Multi-Currency

For instructions on integrating with Shopify's multi-currency, please go [here](https://github.com/Nosto/nosto-shopify/wiki/Multi-Currency-Support).

## Changes to the product tagging

The product page tagging must be amended to denote the primary currency code of the product. Typically, most retailers have a primary currency which is the default currency of the inventory.

For example, a US-based retailer who sells in Euros \(EUR\) and Sterling Pounds \(GBP\) would have US Dollar \(USD\) as the primary currency while Euro \(EUR\) and Sterling Pounds \(GBP\) would be secondary currencies whose exchange rates would need to be sent via an API.

An additional span tag must be placed within the product page tagging with a class name `variation_id`. The tag is a child element of the `nosto_product` element.

```markup
<div class="nosto_product" style="display: none;">
  ...
  ...
  ...
  <!-- Variation ID for the primary currency --> 
  <span class="variation_id">USD</span>
</div>
```

> **Note:** The code in the `variation_id` element must remain static, regardless of the currency active on-site. This is the primary currency of your catalog. Although `variation_id` element often has the same currency code as in the `price_currency_code` element and may seem redundant, they support different use cases and both need to be tagged.

### Do child-products \(SKUs\) support multi-currency?

Yes. Prices for all SKUs will automatically be converted using the same logic. As long as your SKUs are tagged, no additional changes are needed.

### What about the prices in the cart and the order tagging?

The cart and order tagging can be left as-is but the prices must be in the customer's currently active currency. For example, a customer shopping in Swiss Francs \(CHF\) should have all the cart items tagged in Swiss Francs \(CHF\). Failure to do so will result in incorrect prices in any triggered mails such as abandoned cart or order followup.

## Specifying the active currency

Once you have amended the product tagging, an additional DIV element must be added to all the other pages \(including the product page itself\). The tag should not be encapsulated in the `nosto_product` DIV tag. The information sent in the tag refers to the currency active of the customer.

```markup
<div class="nosto_variation" style="display: none;">USD</div>
```

For example, on the site of a US-based retailer who sells in Euros \(EUR\) and Sterling Pounds \(GBP\), if the customer changes the currency to Sterling Pounds \(GBP\), the `nosto_variation` element should show `GBP`. If the customer changes the currency to Euros \(EUR\), the `nosto_variation` element should show `EUR`.

## Sending the exchange-rates

In order to send the exchange rate multipliers to Nosto, you will need to use [our exchange-rates API](../../../apis/rest/other/updating-rates-using-the-rates-api.md). Below is a small snippet of what the payload looks like.

```javascript
{
  "rates":{
    "GBP":{
      "rate":0.77,
      "price_currency_code":"GBP"
    },
    "EUR":{
      "rate":0.91,
      "price_currency_code":"EUR"
    }
  },
  "valid_until":"2015-02-27T12:00:00Z"
}
```

In the example above, `0.77` is the exchange rate from US Dollars \(USD\) to British Pounds \(GBP\) and `0.91` is the exchange rate from US Dollars \(USD\) to Euros \(EUR\).

The `valid_until` entry defines the expiration date. When the expiration date is reached, the exchange rates won't be applied anymore and prices will be hidden for all the secondary currencies to prevent displaying outdated prices.

When recommendations are served, then exchange rates are dynamically applied to the product prices to reflect the active currency.

## Enabling multi-currency from the admin

Once the tagging changed have been done and the API implemented, you need to configure and enable it from your admin panel under **Settings** &gt; **Other** &gt; **Multi-Currency**. Toggle the **Use Multiple Currencies** and **Use Exchange Rates** switches on and set the variation ID of the primary currency via the input field and toggle on the exchange rates switch.

![](https://user-images.githubusercontent.com/327432/36842403-419416ae-1d54-11e8-9bea-a979d7896977.png)

> **Note:** Ensure that the Variation ID of the primary currency matches the value sent via the `variation_id` element in the product tagging.

You will also need to configure the price formatting for your primary and secondary currencies.

## Reviewing your changes

Once you enabled multi-currency and made an API call, you can review the exchange rates received by Nosto by navigating to **Settings** &gt; **Other** &gt; **Multi-currency**.

![](https://user-images.githubusercontent.com/327432/36842599-d47f1748-1d54-11e8-9880-5250b129e62d.png)

You can also preview the product prices for different currencies by navigating to **Tools** &gt; **Products** and choosing a product.

You will see one or more dropdowns that contain the prices and price calculation for the currency.

![](https://user-images.githubusercontent.com/327432/36842669-15cb7412-1d55-11e8-8b48-5f769bb4ecd2.png)

When you have reviewed your set-up, Nosto updates in real-time product prices for all the currencies and display the appropriate currency to the right target groups of users. You’re all set and ready to go live with our features.

