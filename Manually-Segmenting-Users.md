While Nosto leverages customer attributes and behavioral signals to automatically segment users, there may be scenarios where you may want to explicitly segment users. You can do so by affixing a segment-code to the current user and then leverage Nosto's segmentation tool to segment users with that specified attribute.

```js
nostojs(function(api) {
  api.addSegmentCodeToVisit('women');
});
```

