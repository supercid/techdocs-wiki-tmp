Using Nosto within a SPA (single-page-application) is entirely possible. However due to Nosto more or less expecting a static environment with all information accessible on page load you will need to define Javascript calls manually within your own functions.

### Direct including Nosto:

To initialize Nosto you will only need to add the Nosto embed script and the Nosto Javascript stub that initializes the service. You can use the optional disableAutoLoad if you want to have full control on when recommendations are populated. 

HTML
```html
<script src="//connect.nosto.com/include/$accountID" async></script>
```

Javascript
```js
nostojs.init("nostoAccountId", {disableAutoLoad:true});
```

After doing these steps you can test if the nostojs API is available by testing a simple command.

```js
nostojs(function(api){ console.log("API is functional"); });
```
