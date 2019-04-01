To start tracking visits and content the Nosto script needs to be active on all pages within the store where the user might navigate. Replace $accountID from the code below with your own account ID and place the code within the `<head>` section of your sites HTML content. You can find your stores account IDs from the account list within the Nosto admin.

```html
<script type="text/javascript">
    (function(){var name="nostojs";window[name]=window[name]||function(cb){(window[name].q=window[name].q||[]).push(cb);};})();
</script>
<script src="//connect.nosto.com/include/$accountID" async></script>
```

The script should be added as high up in to the `<head>` portion of the page so the connection is initialised as soon as possible. This is because Nosto first creates the initial connection between the service and the store and populates the recommendation elements when the site has loaded. If you add the script lower down in the content there might be a visible delay between page load and loading the recommendations.

>**Note: There are several ways an external script can be executed:**
>* If async tag is present (recommended): The script is executed asynchronously with the rest of the page (the >script will be executed while the page continues the parsing)
>* If async is not present and defer is present: The script is executed when the page has finished parsing
>* If neither async or defer is present: The script is fetched and executed immediately, before the browser >continues parsing the page

```html
<script src="//connect.nosto.com/include/$accountID" defer></script>
<script src="//connect.nosto.com/include/$accountID"></script>
```

>**Note: Difference between XHTML and HTML**
>In XHTML, attribute minimization is forbidden, and the async attribute must be defined as `<script >async="async">` or `<script defer="defer">`

## Deprecated Nosto script

Previously Nosto embed script included a separate `iframe` object and was a lot larger in format. If you are still using the old script we highly recommend you to change it to the new method. 

```html
<script type="text/javascript">
//<![CDATA[
(function(){function a(a){var b,c,d=window.document.createElement("iframe");d.src="javascript:false",(d.frameElement||d).style.cssText="width: 0; height: 0; border: 0";var e=window.document.createElement("div");e.style.display="none";var f=window.document.createElement("div");e.appendChild(f),window.document.body.insertBefore(e,window.document.body.firstChild),f.appendChild(d);try{c=d.contentWindow.document}catch(g){b=document.domain,d.src="javascript:var d=document.open();d.domain='"+b+"';void(0);",c=d.contentWindow.document}return c.open()._l=function(){b&&(this.domain=b);var c=this.createElement("scr".concat("ipt"));c.src=a,this.body.appendChild(c)},c.write("<bo".concat('dy onload="document._l();">')),c.close(),d}var b="nostojs";window[b]=window[b]||function(a){(window[b].q=window[b].q||[]).push(a)},window[b].l=new Date;var c=function(d,e){if(!document.body)return setTimeout(function(){c(d,e)},30);e=e||{},window[b].o=e;var f=document.location.protocol,g=["https:"===f?f:"http:","//",e.host||"connect.nosto.com",e.path||"/include/",d].join("");a(g)};window[b].init=c})();

nostojs.init('[accountID]');

//]]>
</script>

```

## Troubleshooting Nosto script:

Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If the debug toolbar executes and shows up on the page Nosto can track visits on the page. You can further verify your session in the Nosto admin by using the live feed under: https://my.nosto.com/admin/$accountID/liveFeed

![Nosto debug toolbar](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-embed-script-debug.png)