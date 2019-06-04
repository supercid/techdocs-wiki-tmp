To start tracking visits and content the Nosto script needs to be active on all pages within the store where the user might navigate. Replace $accountID from the code below with your own account ID and place the code within the `<head>` section of your sites HTML content. You can find your stores account IDs from the account list within the Nosto admin.

```html
<script type="text/javascript">
    (function(){var name="nostojs";window[name]=window[name]||function(cb){(window[name].q=window[name].q||[]).push(cb);};})();
</script>
<script src="//connect.nosto.com/include/$accountID" async></script>
```

The script should be added as high up in to the `<head>` portion of the page so the connection is initialised as soon as possible. This is because Nosto first creates the initial connection between the service and the store and populates the recommendation elements when the site has loaded. If you add the script lower down in the content there might be a visible delay between page load and loading the recommendations.

## Troubleshooting Nosto script:

Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If the debug toolbar executes and shows up on the page Nosto can track visits on the page. You can further verify your session in the Nosto admin by using the live feed under: https://my.nosto.com/admin/$accountID/liveFeed

![Nosto debug toolbar](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-embed-script-debug.png)