While Nosto is initialized automatically when you are using the direct-include you may encounter situations where you may need to initialize it manually.


```js
nostojs.init("account-id");
```

### Disabling Autoloading

In the event that you would like to initialize Nosto but not have it automatically load the recommendations, you can pass a `disableAutoLoad` flag.

```js
nostojs.init("account-id", {disableAutoLoad:true});
```

*Note:* you will need to manually load the recommendations when the autoloading is disabled.