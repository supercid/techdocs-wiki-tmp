When a user places an order onsite, you must send the conversion tracking information to Nosto. 


```graphql
mutation {
  placeOrder(by:BY_REF, id: "514421fce84abcb61bd45241", params: {
    customer: {
      firstName: "Mridang"
      lastName: "Agarwalla"
      email: "mridang@nosto.com"
      marketingPermission: false
    }
    order: {
      number: "25435"
      orderStatus: "paid"
      paymentProvider: "klarna"
      ref: "0010"
      purchasedItems: [
        {
          name: "Shoe"
          productId: "1"
          skuId: "11"
          priceCurrencyCode: "EUR"
          unitPrice: 22.43
          quantity: 1
        }
      ]
    }
  }) {
    id
    pages {
      forOrderPage(value: "25435", params: {
        imageVersion: VERSION_3_90_70
        isPreview: true
      }) {
	divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```