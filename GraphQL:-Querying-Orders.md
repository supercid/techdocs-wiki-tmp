```graphql
query {
  order(id: "M2_2") {
    number
    reference
    items {
      productId
      skuId
      unitPrice
      priceCurrencyCode
      quantity
    }
    recos(preview: true, image: VERSION_1_170_170) {
      related(params: {
        minProducts: 1,
        maxProducts: 5
      }) {
        primary {
          productId
          name
          price
        }
      }
    }
  }
}
```