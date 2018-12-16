This endpoint is used for toggling the email consent for an email. 

#### Token

This endpoint requires an Email token.

### Usage

#### Granting consent

```shell
curl -v -X POST https://api.nosto.com/v1/customers/consent/john.doe@nosto.com/true \
--user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw
```

#### Revoking consent

```shell
curl -v -X POST https://api.nosto.com/v1/customers/consent/john.doe@nosto.com/false \
--user :WI0j2oN7TgG42tlblX3yzOQ5xvCYc2oYj9eWg79lghVq8R0nKQXlVE9wvihBUFOw
```