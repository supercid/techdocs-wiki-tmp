##### How do I track clicks on recommendations
This is done automatically by Nosto as long as you follow the [Handling attribution- topic](SPA/Basics.md#handling-attribution-1).

Alternatively you can define the recommendation (`result_id`) after an [action](Session-API---Terminology.md#action) by adding `.setRef(productId, result_id)` to your call. In practise you would only do this when performing [the action for product view](SPA/Basics.md#upon-viewing-a-product).

Example when productId 123 was clicked on a recommendation _nosto-frontpage-1_:

```
nostojs(api => {
    api
        .defaultSession()
        .viewProduct('123')
        .setRef('123', 'nosto-frontpage-1')
        .setPlacements(['nosto-page-product1'])
        .load()
        .then(data => {
            console.log(data);
        });
});
```

##### Tracking external advertisement campaigns
Tracking external campaigns such as Google Ads, Facebook Ads, etc. will work automatically as long as you perform an [action](Session-API---Terminology.md#action)  on the landing page of your ad.