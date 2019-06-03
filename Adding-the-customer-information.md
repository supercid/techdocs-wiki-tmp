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

The new marketing-permission flag denotes whether the customer has consented to email marketing. If the marketing-permission field is omitted, we assume that the current customer has not given their consent and Nosto will refrain from sending out any personalized triggered emails.

The marketing permission is false by default but if a user has explicitly agreed to receive marketing then you can set it to true manually. In practice, this means reading and mapping the value from opt-in for marketing in your platform e.g. a consumer explicitly subscribed for marketing emails when checking out.

The marketing-permission should be included as a part of the customer tagging and should be rendered on all pages.

## Tagging customer reference

The customer reference attribute to match the customer across Nosto stores, devices or even between offline/online sessions if you are using a unified customer loyalty program.

The customer-reference should be a long, secure and a non-guessable identifier. For example, use your internal customer-id or the customer's loyalty program identifier and use a secure hash function like an HMAC-SHA256 to hash it.

**Note:** If a customer reference is in use in the customer information tagging, make sure the identifier is secure enough. Nosto recommends using a UUID or the structure in the above example if a UUID can’t be supported.