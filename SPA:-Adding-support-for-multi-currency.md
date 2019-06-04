In this article, you will learn how to implement multi-currency in Nosto. When the implementation is complete, you will be able to display product prices (in any feature) in different currencies.

Prior to the multi-currency implementation, ensure that your implementation is correct. Some of the API calls must be slightly amended to support multi-currency.

## Changes to the product metadata

The product page tagging must be amended to denote the primary currency code of the product. Typically, most retailers have a primary currency which is the default currency of the inventory.

For example, a US-based retailer who sells in Euros (EUR) and Sterling Pounds (GBP) would have US Dollar (USD) as the primary currency while Euro (EUR) and Sterling Pounds (GBP) would be secondary currencies whose exchange rates would need to be sent via an API.

An additional property must be placed within the product page tagging with a class name `variation_id`. The tag is a child element of the `nosto_product` element.

```json
[
  {
    ...
    ...
    "variation_id":"EUR_1",
    ...
    ...
  }
]
```

**Note:** The code in the `variation_id` element must remain static, regardless of the currency active on-site. This is the primary currency of your catalog. Although `variation_id` element often has the same currency code as in the `price_currency_code` element and may seem redundant, they support different use cases and both need to be tagged.

### Do child-products (SKUs) support multi-currency?

Yes. Prices for all SKUs will automatically be converted using the same logic. As long as your SKUs are tagged, no additional changes are needed.

### What about the prices in the cart and the order tagging?

The cart and order tagging can be left as-is but the prices must be in the customer's currently active currency. For example, a customer shopping in Swiss Francs (CHF) should have all the cart items tagged in Swiss Francs (CHF). Failure to do so will result in incorrect prices in any triggered emails such as abandoned cart or order followup.

## Specifying the active currency

Once you have amended the product metadata, you must change the session usage to also pass the active currency of the customer.

```js
nostojs(api => {
  api.defaultSession()
    .setVariation("USD")
});
```

For example, on the site of a US-based retailer who sells in Euros (EUR) and Sterling Pounds (GBP), if the customer changes the currency to Sterling Pounds (GBP), the `setVariation` method must be passed `GBP`. If the customer changes the currency to Euros (EUR), the `setVariation` method must be passed `EUR`. 


## Sending the exchange-rates

In order to send the exchange rate multipliers to Nosto, you will need to use our Exchange Rate API. The exchange rates must be included within a JSON message and an authenticated HTTP request must be executed. You will need to make an authenticated POST request to https://api.nosto.com/exchangerates with a JSON payload in the given structure:

```json
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

In the example above, `0.77` is the exchange rate from US Dollars (USD) to British Pounds (GBP) and `0.91` is the exchange rate from US Dollars (USD) to Euros (EUR).

The `valid_until` entry defines the expiration date. When the expiration date is reached, the exchange rates won't be applied anymore and prices will be hidden for all the secondary currencies to prevent displaying outdated prices.

When recommendations are served, then exchange rates are dynamically applied to the product prices to reflect the active currency.

Here is an example of the request above as a cURL:

```
curl -v -X POST -H 'Content-Type: application/json'-d '{"rates": {"GBP": {"rate": 0.77, "price_currency_code": "GBP"}, "EUR": {"rate": 0.91, "price_currency_code": "EUR"}}, "valid_until": "2015-02-27T12:00:00Z"}' -u ':tokenSecretHere' https://api.nosto.com/exchangerates
```

### How can I get an API token?

You can request an API token (API_RATES) by getting in touch with our support personnel. Once the token has been granted, you will be able to find it listed in the [authentication tokens section in the admin.](https://help.nosto.com/settings-and-troubleshooting-faq/settings-authentication-tokens)

### How often should I send exchange-rates?

You can send exchange rates as often as you like but at the bare minimum, the exchange rates should be sent when they are changed.

## Enabling multi-currency from the admin

Once the tagging changed have been done and the API implemented, you need to configure and enable it from your admin panel under **Settings** > **Other** > **Multi-Currency**. Toggle the **Use Multiple Currencies** and **Use Exchange Rates** switches on and set the variation ID of the primary currency via the input field and toggle on the exchange rates switch.

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