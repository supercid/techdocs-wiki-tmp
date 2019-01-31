You can query products using the GraphQL products endpoint. So long as you are able to specify the product id, you will be able to query the product.

```graphql
curl -0 -v -X GET https://api.nosto.com/v1/graphql \
-u ":<token>" \
-H 'Content-Type: application/graphql' \
-d @- << EOF
query {
  product(id: "5358") {
    productId
    name
    url
    price
    listPrice
    imageUrl
    attributes {
      key
      value
    }
    skus {
      name
      price
      listPrice
      availability
      imageUrl
      url
    }
  }
}
EOF
```