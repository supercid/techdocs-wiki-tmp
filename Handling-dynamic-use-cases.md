In most implementations there isn’t any need to use the Nosto JavaScript API and the normal tagging implementation approach will work best. The JavaScript API is useful mostly in cases where the store is doing something dynamic and not reloading the page. For example showing recommendations in a product quick view, that opens the product in a css overlay via Ajax. Another case is when the whole store is implemented as a single page application.

We have gathered some of the most-used use-cases where dynamic requests or responses are needed. 

  * [Sending email addresses to Nosto](Sending-email-addresses-to-Nosto)
  * [Exposing Nosto elements in dynamic overlays](Exposing-nosto-elements-in-dynamic-overlays)
  * [Registering add-to-cart events from dynamic buttons](Registering-add-to-cart-events-from-dynamic-buttons)