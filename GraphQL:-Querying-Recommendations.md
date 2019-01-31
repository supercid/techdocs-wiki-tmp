You can generic recommendations using the GraphQL orders endpoint. The recommendations offered here don't use sessions so they aren't personalized but still offer enough flexibility to support a multitude of use-cases.

### Fetching toplists

The endpoint can be used to fetch toplist recommendations. Toplists recommendations are either sorted by views or buys.

```graphql
curl -0 -v -X GET https://api.nosto.com/v1/graphql \
-u ":<token>" \
-H 'Content-Type: application/graphql' \
-d @- << EOF
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
EOF
```

## Fetching random recommendations

The endpoint can be used to fetch random recommendations. Random recommendations are a totally randomized selection of products and often used for testing purposes.

```
curl -0 -v -X GET https://api.nosto.com/v1/graphql \
-u ":<token>" \
-H 'Content-Type: application/graphql' \
-d @- << EOF
query {
  recos (preview: true, image: VERSION_7_200_200) {
    random(params: {
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
EOF
```