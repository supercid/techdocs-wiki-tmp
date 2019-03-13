You can open up a Nosto behavioral pop-up by calling the api.openPopup() function. The first argument of the function is the ID of the popup campaign whose pop-up you want to show. The pop-up campaigns, including the pop-up templates themselves, are created in the Nosto Administration UI

Please note that some campaigns have active trigger types and can be opened automatically. If you want to use only the api.openPopup() call to open pop-ups, please create the respective campaigns using the JavaScript API pop-up trigger type.

You can also give a second, optional argument to the api.openPopup() function. The second argument is an object with the following fields:

```js
nostojs(function(api) {
  var arrayOfPopupCampaigns = api.popupCampaigns();

  // arrayOfPopupCampaigns = [
  //   { id: "campaignId", name: "campaignName", type: "triggerType" },
  //   ...
  // ];

  var popupCampaignId = arrayOfPopupCampaigns[0].id;

  api.openPopup(popupCampaignId);

  // or

  var popupOptions = {
    // Effects corresponding to the ones in the admin UI
    effects: {
      overlayOpacity: 0.8,
      fadeInDelayMs: 300
    },
    preview: false
  };
  api.openPopup(popupCampaignId, popupOptions);  
});
```