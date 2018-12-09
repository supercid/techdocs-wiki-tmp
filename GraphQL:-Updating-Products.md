Mutations can be used to update the product catalog in Nosto. The `updateProducts` mutation allows you to update one or more products at a go.

**Note:** This mutation is currently in beta and may not support mutating all product fields.

The given example updates the UGC image for product #74 and requests the details of the updated products and any associated errors.

```shell
curl -0 -v -X POST https://api.nosto.com/v1/graphql \
-u ":<token>" \
-H 'Content-Type: application/graphql' \
-d @- << EOF
```graphql
mutation {
  updateProducts(products: [
    {
      id: "74"
      url: "https://store.mybigcommerce.com/sample-french-connection-straw-bag/"
      ugcImages: [
        {
          url: "https://instagram.com/photo.jpg"
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
EOF
```