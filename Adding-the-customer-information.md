Customer information allows you to annotate contact details for the current customer. This information can be outputed from your ecommerce platfrom, CRM system or any other mechanisms you have in place onsite that can modify the tagging.

```html
<div class="nosto_customer" style="display:none">
  <span class="email">john.doe@example.com</span>
</div>
```

The email address is the only required parameter in the tagging, but you can enrich the profile with other optional attributes.

```html
  <span class="first_name">John</span>
  <span class="last_name">Doe</span>
  <span class="customer_reference">e18daf14-d715-4d77-82f2-93eceb4ae1ef</span>               
  <span class="birth_date">2011-12-31</span>
  <span class="marketing_underscore_permission">true</span>
```

> **Note:** Marketing permission is false by default but if this user has explicitly agreed to receive marketing 
> then you can set it to true manually 