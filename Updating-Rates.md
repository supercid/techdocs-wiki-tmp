### Update Exchange Rates [POST]

Updates the exchange rates for your account. When new rates are sent via this endpoint, the changes will reflect instantly on your store as the product prices are multiplied with the provided rates in real-time.

+ Request (application/json)

    + Headers

            Authorization: Basic OjAxMDk4ZDBmYzg0ZGVkN2M0MjI2ODIwZDVkMTIwN2M2OTI0M2NiYjM2MzdkYzRiYzJhMjE2ZGFmY2YwOWQ3ODM=

    + Body

            [
                {
                    "currency_code": "EUR",
                    "exchange_rate": "0.1",
                    "name": "Euros"
                }
            ]

+ Response 200 (application/json)

        {}

+ Response 400 (application/json)

        {}

+ Response 500 (application/json)

        {}