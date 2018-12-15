When using multi-currency, this endpoint is used to update the exchange rates for your account. When new rates are sent via this endpoint, the changes will reflect instantly on your store as the product prices are multiplied with the provided rates in real-time.

**Note:** This endpoint should only be used when using multi-currency. Please refer to our multi-currency guide prior to using this endpoint. Incorrect usage of these endpoints will result in a total outage of your personalisation setup.

#### Token

These endpoints require a Rates token.

### Usage

```shell
curl -v --user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw -H "Content-Type: application/json" -X POST https://api.nosto.com/exchangerates -d '
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
}'
```