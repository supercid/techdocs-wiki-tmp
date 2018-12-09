


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