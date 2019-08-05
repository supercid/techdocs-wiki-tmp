When a user places an order onsite, you must send the conversion tracking information to Nosto. 


```graphql
mutation {
  updateStatus(number: "ORD102-33", params: {
    orderStatus: "fraud"
    paymentProvider: "klarna"
    statusDate: "2011-12-03T10:17:30"
  }) {
    number
    statuses {
      date
      orderStatus
      paymentProvider
    }
  }
}
```

