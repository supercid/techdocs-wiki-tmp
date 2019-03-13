You can use the JS API to conditionally enable or disable a popup. 

## Enabling a Popup

The following snippet enabled the specified popup.

```js
nostojs(function(api) {
  api.enablePopup("popupCampaignId");
});
```

#### Parameters

| Field | Type   | Default | Reason                               |
|-------|--------|---------|--------------------------------------|
| id    | String |         | The identifier of the popup campaign |

## Disabling a Popup

The following snippet disables the specified popup.

```js
nostojs(function(api) {
  api.enablePopup("popupCampaignId");
});
```

#### Parameters

| Field | Type   | Default | Reason                               |
|-------|--------|---------|--------------------------------------|
| id    | String |         | The identifier of the popup campaign |