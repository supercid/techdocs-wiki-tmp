
```graphql
query {
  identity(email:"john.smith@example.com") {
    email,
    attributes {
      name,
      value
    }
    recos(preview: true, image: VERSION_ORIGINAL) {
      history(params: {
        minProducts: 3,
        maxProducts: 10,
        showRelatedProducts: true,
        skipProductsInCart: true,
        skipBoughtProducts: true
      }) {
        primary {
          url
          imageUrl
        }
      }
    }
  }
}
```