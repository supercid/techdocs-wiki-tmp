The JS API can be used to register callbacks to hook into the recommendation events. To register a listener for a callback, use `api.listen(callbackId, callbackFunction)` function.

## Post Render Callback

Called when Nosto has responded and finished recommendation placement.

```js
nostojs(function(api) {
  api.listen('postrender', function(event) {
    console.log(event.filledElements);
    console.log(event.unFilledElements); 
  });
});
```

#### Fields

| Field      | Type   | Reason                                                                                                                                                                                                                                                                                                    |
|------------|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| email      | String | The email address in the user input.                                                                                                                                                                                                                                                                      |
| newsletter | String | Whether the user gave their consent to subscribing to a newsletter. E.g. either the pop­up prompting for the email address input was worded similarly to “Please enter your email address to subscribe to our newsletter:” or there was an explicit checkbox that the user checked to give their consent. |