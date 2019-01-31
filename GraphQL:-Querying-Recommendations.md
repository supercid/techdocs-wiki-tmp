You can generic recommendations using the GraphQL orders endpoint. The recommendations offered here don't use sessions so they aren't personalized but still offer enough flexibility to support a multitude of use-cases.

### Fetching bestsellers

query {
  recos (preview: false, image: VERSION_7_200_200) {
    toplist(hours: 168, sort: BUYS, params: {
      minProducts: 1
      maxProducts: 10
    }) {
      primary {
        name 
        productId
      }
    }
  }
}