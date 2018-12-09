Mutations can be used to update the product catalog in Nosto. The `updateProducts` mutation allows you to update one or more products at a go.

*Note:* This mutation is currently in beta and may not support mutating all product fields.


```graphql
mutation {
  updateProducts(products: [
    {
      id: "74"
      url: "httddps://test-store--1.mybigcommerce.com/sample-french-connection-straw-bag/"
      ugcImages: [
        {
          url: "https://instagram.com/xxx.jpg"
        }
      ]
    }
  ]) {
    result {
      errors {
        field
        message
      }
      data {
        productId
      }
    }
  }
}```