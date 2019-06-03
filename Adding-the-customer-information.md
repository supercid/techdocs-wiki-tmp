On every page, the customer information _should_ be tagged if the customer is logged in. If the customer isn't logged in, this but can be omitted.

The customer information is primarily used for sending personalised triggered emails and for building multi-channel experiences.

```html
<div class="nosto_customer" style="display:none">
  <span class="email">john.doe@example.com</span>
  <span class="first_name">John</span>
  <span class="last_name">Doe</span>
  <span class="customer_reference">e18daf14-d715-4d77-82f2-93eceb4ae1ef</span>
  <span class="marketing_permission">false</span>
</div>
```

## Tagging marketing permission

The new marketing_permission flag denotes whether the customer has consented to email marketing. If the marketing_permission field is omitted, we assume that the current customer has not given their consent and Nosto will refrain from sending out any personalized triggered emails.

Marketing permission is false by default but if a user has explicitly agreed to receive marketing then you can set it to true manually. In practice this means reading and mapping the value from opt-in for marketing in your platform e.g. a consumer explicitly subscribed for marketing emails when checking out.

The marketing_permission should be included as a part of the customer tagging and should be rendered on all pages.

## Tagging customer reference (supporting cross-device sessions)

You can use the customer reference attribute to match the customer across Nosto stores, devices or even between offline/online sessions if you are using a unified customer loyalty program.

```html
– SHA-1
– {customer_id}_{UUID}
– {customer_id}_{merchant_specific_secret}_{customer_specific_data}_{timestamp}_{random}
– {customer_id}_{merchant_specific_secret}_{customer_specific_data}_{timestamp}
– {customer_id}_{merchant_specific_secret}_{timestamp}
```

> **Note:** If a customer reference is in use in the customer information tagging, make sure the identifier is 
> secure enough. Nosto recommend to use a UUID or the structure in above example if a UUID can’t be supported.