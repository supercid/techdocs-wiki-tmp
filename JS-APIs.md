In most implementations, there isn't any need to use the Nosto JavaScript API and the regular tagging implementation approach will suffice. 

Typically calling the API should be approached only after the normal tagging implementation has been done and now needs to be extended with something that doesn’t come out of the box. The JavaScript API is commonly used to support dynamic functionality i.e. without a page reload. For example, showing recommendations in a product quick view.

## Prerequisites

JavaScript API works only in on-site context. Using the API does not require authentication but requires that Nosto embed script is included.

Nosto embed script needs to be recent enough. The easiest way to check that you are using a recent version enough, is to view your site’s html source and make sure it includes the text nostojs.init. In case that is there you are using the version that supports the Nosto Javascript API.

If you are using Nosto with a async script tag (AKA Direct Include), then you must add a javascript stub as an inline script block before you call the Nosto Javascript API (see the Javascript examples). You do not need to call nostojs.init() when using Direct Include.

Using the stub ensures that your code will be executed correctly even if you call the Nosto JS API before the Nosto script has loaded.