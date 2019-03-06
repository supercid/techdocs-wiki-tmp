

## Creating a session

When a new user comes to the app, you can use this parameterless method to get a new session. It will return you a customer-id that can save on the device and use for future requests. This would be ideal.

## Updating a session

When a customer logs in, you can update the existing customer with the customer-reference. This would merge the online and mobile sessions. If not needed, I would omit this for now.

## Working with recommendations

### On the Product Page

```graphql
mutation {
  updateSession(by: BY_CID, id: "5b1a481060b221115c4a251e",
    params: {
      event: {
        type: VIEWED_PRODUCT
        target: "11923861519"
      }
    }
  ) {
    pages {
      forProductPage(params: {
        isPreview: false, imageVersion:  VERSION_8_400_400
      }, product: "11923861519") {
        divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```

### On the Category Page

```graphql
mutation {
  updateSession(by: BY_CID, id: "5b1a481060b221115c4a251e",
    params: {
      event: {
        type: VIEWED_CATEGORY
        target: "Shorts"
      }
    }
  ) {
    pages {
      forCategoryPage(params: {
        isPreview: false, imageVersion:  VERSION_8_400_400
      }, category: "Shorts") {
        divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```

### On the Search Page

```graphql
mutation {
  updateSession(by: BY_CID, id: "5b1a481060b221115c4a251e",
    params: {
      event: {
        type: SEARCHED_FOR
        target: "black shoes"
      }
    }
  ) {
    pages {
      forSearchPage(params: {
        isPreview: false, imageVersion:  VERSION_8_400_400
      }, term: "black shoes") {
        divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```

### On the Cart Page

```graphql
mutation {
  updateSession(by: BY_CID, id: "5b1a481060b221115c4a251e",
    params: {
      event: {
        type: SEARCHED_FOR
        target: "black shoes"
      }
    }
  ) {
    pages {
      forCartPage(params: {
        isPreview: false, imageVersion:  VERSION_8_400_400
      }, value: 100) {
        divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```

### On the Front Page

```graphql
mutation {
  updateSession(by: BY_CID, id: "5b1a481060b221115c4a251e",
    params: {
      event: {
        type: SEARCHED_FOR
        target: "black shoes"
      }
    }
  ) {
    pages {
      forFrontPage(params: {
        isPreview: false, imageVersion:  VERSION_8_400_400
      }) {
        divId
        resultId
        primary {
          productId
        }
      }
    }
  }
}
```