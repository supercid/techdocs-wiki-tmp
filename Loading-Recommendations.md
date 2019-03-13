By default, Nosto loads the recommendations as soon as the site’s DOM is loaded. In some use cases, Nosto needs to be loaded manually. This is done by using a manual cal:

```js
nostojs(function(api) {
  api.loadRecommendations();
});
```