In this article, you will learn how to collect email addresses from other sources. If you have implemented the customer tagging, Nosto will automatically collect the information for logged-in users. For all other scenarios, you will need to use our Javascript API to push the customer information to us:

## Collecting email addresses from a form field

If your website has a form field that accepts email address, you can capture email addresses using our JS API. Here's a small example on how to accomplish that:

```javascript
jQuery("form input.nosto_email_capture").each(function(idx, input) {
    if (!input.form) {
        return;
    }
    input.form.onsubmit = function(event) {
        var email = input.value;
        if (email) {
            // Push customer information to current visit
            nostojs(function(api) {
                console.log("Collecting email " + email);
                api.customer({email: email});
            });
        } else {
            console.log("No email specified");
        }
    }
});
```

https://developer.nosto.com/?javascript#sending-customer-information