To start tracking visits and content the Nosto script needs to be active on all pages within the store where the user might navigate. Replace $accountID from the code below with your own account ID and place the code within the <head> section of your sites HTML content. You can find your stores account IDs from the account list within the Nosto admin.

```html
<script src="//connect.nosto.com/include/$accountID" async></script>
```

The script should be added as high up in to the `<head>` portion of the page so the connection is initialised as soon as possible. This is because Nosto first creates the initial connection between the service and the store and populates the recommendation elements when the site has loaded. If you add the script lower down in the content there might be a visible delay between page load and loading the recommendations.

**Note: There are several ways an external script can be executed:**
* If async tag is present (recommended): The script is executed asynchronously with the rest of the page (the script will be executed while the page continues the parsing)
* If async is not present and defer is present: The script is executed when the page has finished parsing
* If neither async or defer is present: The script is fetched and executed immediately, before the browser continues parsing the page

```html
<script src="//connect.nosto.com/include/$accountID" defer></script>
<script src="//connect.nosto.com/include/$accountID"></script>
```

**Note: Difference between XHTML and HTML**
In XHTML, attribute minimization is forbidden, and the async attribute must be defined as `<script async="async">` or `<script defer="defer">`.

**Troubleshooting Nosto script:**
Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If the debug toolbar executes and shows up on the page Nosto can track visits on the page. You can further verify your session in the Nosto admin by using the live feed under: https://my.nosto.com/admin/$accountID/liveFeed

![Nosto debug toolbar](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-embed-script-debug.png)