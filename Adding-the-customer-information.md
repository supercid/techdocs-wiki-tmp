Customer information allows you to annotate contact details for the current customer. This information can be outputed from your ecommerce platfrom, CRM system or any other mechanisms you have in place onsite that can modify the tagging.

The customer tagging should be exposed on every page whenever we have the necessary information available in the front-end context.

```html
<div class="nosto_customer" style="display:none">
  <span class="email">john.doe@example.com</span>
</div>
```

The email address is the only required parameter in the tagging, but you can enrich the profile with other optional attributes.

```html
  <span class="first_name">John</span>
  <span class="last_name">Doe</span>
  <span class="marketing_permission">false</span>
```

## Tagging marketing permission

The new marketing_permission flag denotes whether the customer has consented to email marketing. If the marketing_permission field is omitted, we assume that the current customer has not given their consent and Nosto will refrain from sending out any personalized triggered emails.

Marketing permission is false by default but if a user has explicitly agreed to receive marketing then you can set it to true manually. In practice this means reading and mapping the value from opt-in for marketing in your platform e.g. a consumer explicitly subscribed for marketing emails when checking out.

The marketing_permission should be included as a part of the customer tagging and should be rendered on all pages.