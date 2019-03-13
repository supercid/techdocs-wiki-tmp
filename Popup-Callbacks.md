The JS API can be used to register callbacks to hook into the popup events.

To register listener to a callback, use api.listen(callbackId, callbackFunction).

## Post Render Callback

```js
 nostojs(function(api){
   api.listen("postrender", function(nostoPostRenderEvent) { 
     console.log("Callback");
    });
  });
```

#### Fields

## Email Given Callback

```js
nostojs(function(api){
  api.listen("emailgiven", function(emailSubscriptionEvent){
  console.log(emailSubscriptionEvent.email);
  console.log(emailSubscriptionEvent.newsletter);
  });
});
```

#### Fields

## Popup Opened Callback

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

## Popup Ribbon Callback

```js
  api.listen("popupRibbonShown", function(ribbonEvent) {
    console.log(ribbonEvent.campaignId);
  });
```

#### Fields

| Field      | Type   | Reason                               |
|------------|--------|--------------------------------------|
| campaignId | String | The identifier of the popup campaign |

## Popup Minimised Callback

```js
  api.listen("popupMinimized", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

#### Fields

| Field      | Type   | Reason                               |
|------------|--------|--------------------------------------|
| campaignId | String | The identifier of the popup campaign |

## Popup Maximised Callback

```js
  api.listen("popupMaximized", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

#### Fields

| Field      | Type   | Reason                               |
|------------|--------|--------------------------------------|
| campaignId | String | The identifier of the popup campaign |

## Popup Closed Callback

```js
  api.listen("popupClosed", function(popupEvent) {
    console.log(popupEvent.campaignId);
  });
```

#### Fields

| Field      | Type   | Reason                               |
|------------|--------|--------------------------------------|
| campaignId | String | The identifier of the popup campaign |

## Coupon Given Callback

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

#### Fields

### Cart Abandonment Callback

The callback will be called when a customer clicks a button inside a Nosto abandoned cart pop-up to get an abandoned cart email.

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

#### Fields

| Field      | Type    | Reason                                           |
|------------|---------|--------------------------------------------------|
| sent       | boolean | A boolean indicating whether the email was sent  |
| campaignId | String  | The identifier of the popup campaign             |
| email      | String  | The email address to which the email was sent    |
| message    | String  | Any error messages relating to the email sending |