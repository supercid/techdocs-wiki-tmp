The JS API can be used to register callbacks to hook into the popup events.

To register listener to a callback, use api.listen(callbackId, callbackFunction).



```js
 nostojs(function(api){
   api.listen("postrender", function(nostoPostRenderEvent) { 
     console.log("Callback");
    });
  });
```

```js
nostojs(function(api){
  api.listen("emailgiven", function(emailSubscriptionEvent){
  console.log(emailSubscriptionEvent.email);
  console.log(emailSubscriptionEvent.newsletter);
  });
});```

```js
api.listen("popupOpened", function(popupEvent) {
    if (popupEvent.error) {
      console.error(popupEvent.error);
    } else {
      console.log(popupEvent.campaignId);
      console.log(popupEvent.type);
    }
  });
```

```js
  api.listen("popupRibbonShown", function(ribbonEvent) {
    console.log(ribbonEvent.campaignId);
  });
```

```js
  api.listen("popupMinimized", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

```js
  api.listen("popupMaximized", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

```js
  api.listen("popupClosed", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

```js
  api.listen("couponGiven", function(couponEvent) {
    if (couponEvent.error) {
      console.error(couponEvent.error);
    } else {
      console.log(couponEvent.campaignId);
      console.log(couponEvent.couponCode);
      console.log(couponEvent.origin);
    }
  });
```

```js
  api.listen("sendabandonedcartemail", function(sendMailEvent) {
    if (!sendMailEvent.sent) {
      console.error(sendMailEvent.message);
    } else {
      console.log(sendMailEvent.campaignId);
      console.log(sendMailEvent.email);
    }
  });
```