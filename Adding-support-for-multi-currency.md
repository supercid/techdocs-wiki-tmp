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


## Sending the exchange-rates

In order to send the exchange rate multipliers to Nosto, you will need to use our Exchange Rate API. The exchange rates must be included within a JSON message and an authenticated HTTP request must be executed. 

An API Token is required. Please contact support@nosto.com to get an API Token. Please inform our Support Team about your Nosto Account ID and request an API_RATES Token.

Once you have the token in hands, you can proceed to the API calls. Use an empty string as the username, and the API token provided by Nosto as the password. The authenticated HTTP POST request must be made to:

https://api.nosto.com/exchangerates
Including a JSON message body following the structure:

{
  "rates": {
    "GBP": {
      "rate": 0.77,
      "price_currency_code": "GBP"
    },
    "EUR": {
      "rate": 0.91,
      "price_currency_code": "EUR"
    }
  },
  "valid_until": "2015-02-27T12:00:00Z"
}

> **Note:** The request must be made in HTTPS exclusively. You can view your API token value by signing up to your Nosto back-end at https://my.nosto.com and go to Settings > Other > Authentication Tokens.

In the example above, 0.77 is the exchange rate to get the price value in British pound from US Dollar and 0.91 is the exchange rate to get the price in Euro from US Dollar.

The `valid_until` entry defines the expiration date. When the expiration date is reached, the exchange rates won't be applied anymore and prices will be hidden for all the secondary currencies to prevent displaying outdated prices.

When Nosto recommendations are loaded, exchange rates are dynamically applied to the price variable in use in the recommendation templates.

Here is an example of the request above as a cURL:

```
curl -v -X POST -H 'Content-Type: application/json'-d '{"rates": {"GBP": {"rate": 0.77, "price_currency_code": "GBP"}, "EUR": {"rate": 0.91, "price_currency_code": "EUR"}}, "valid_until": "2015-02-27T12:00:00Z"}' -u ':tokenSecretHere' https://api.nosto.com/exchangerates
```

### How often should I send exchange-rates?

You can send exchange rates as often as you like but at the bare minimum, the exchange rates should be sent when they are changed.

## Enabling multi-currency from the admin

Once the tagging changed have been done and the API implemented, you need to configure and enable it from your admin panel under **Settings** > **Other** > **Multi-Currency**. Toggle the multiple currencies switch on and set the variation ID of the primary currency via the input field and toggle on the exchange rates switch.

![](https://user-images.githubusercontent.com/327432/36842403-419416ae-1d54-11e8-9bea-a979d7896977.png)

> **Note:** Ensure that the Variation ID of the primary currency matches the value sent via the `variation_id` element in the product tagging.

You will also need to configure the price formatting for your primary and secondary currencies.

## Reviewing your changes

Once you enabled multi-currency and made an API call, you can review the exchange rates received by Nosto by navigating to **Settings** > **Other** > **Multi-currency**.

![](https://user-images.githubusercontent.com/327432/36842599-d47f1748-1d54-11e8-9880-5250b129e62d.png)
 
You can also preview the product prices for different currencies by navigating to **Tools** > **Products** and choosing a product.

You will see one or more dropdowns that contain the prices and price calculation for the currency. 

![](https://user-images.githubusercontent.com/327432/36842669-15cb7412-1d55-11e8-8b48-5f769bb4ecd2.png)

When you have reviewed your set-up, Nosto updates in real-time product prices for all the currencies and display the appropriate currency to the right target groups of users. You’re all set and ready to go live with our features.