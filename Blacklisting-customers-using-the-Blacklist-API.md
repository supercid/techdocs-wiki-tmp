This endpoint is used for blacklisting email addresses from receiving Nosto's triggered emails.

#### Token

This endpoint requires an Email token.

#### Granting consent

```shell
curl -v -X POST https://api.nosto.com/v1/email/blacklist \
--user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw
```

#### Revoking consent

```shell
curl -v -X POST https://api.nosto.com/v1/email/unblacklist \
--user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw
```