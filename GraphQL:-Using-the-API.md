## Sending JSON GraphQL queries

You can send your GraphQL requests as JSON to our API and have it correctly interpolate variables passed into it. To do so, set the `Content-Type` header to `application/json`.

Authentication |    Token      |    Method    | Endpoint
---------------|---------------|--------------|--------------------------------------
Basic          |   API_APPS    |     POST     | `https://api.nosto.com/v1/graphql`   

```shell
curl -0 -v -X POST https://api.nosto.com/v1/graphql \
-u ":<token>" \
-H 'Content-Type: application/json' \
-d @- << EOF
{
  "query": "query { recos (preview: false, image: VERSION_7_200_200) { toplist(hours: 168, sort: BUYS, params: { minProducts: 1 maxProducts: 10 } ) { primary { name productId } } } }"
}
EOF
```

## Sending raw GraphQL queries

If you want to send raw GraphQL queries to the API, you can still do so but you must set the `Content-Type` header to `application/graphql`.

<aside class="warning">
<b>NOTE:</b>If you do not set the correct Content-Type header, the request will be interpreted as JSON and will fail.
</aside>

Authentication |    Token      |    Method    | Endpoint
---------------|---------------|--------------|---------------------------------
Basic          |   API_APPS    |     POST     | `https://api.nosto.com/v1/graphql`


```shell
curl -0 -v -X POST https://api.nosto.com/v1/graphql \
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
