Nosto is expecting the default web behavior of page loads and static assets on the page for core functionality to work out of the box. In certain cases where a lot of the page content is created, modified or removed dynamically by the use of Javascript some modifications to the core functionality might be needed. 

In most cases its enough to add one or two Javascript functions that take care of certain use-cases like creating a dynamic overlay with Nosto recommendations or reading the contents of a shopping cart built with Javascript to name a couple of examples. In some cases however you will need to overwrite the base functionality all together and send events, product data and fetch recommendations manually. 

In most implementations there isn’t any need to use the Nosto JavaScript API and the normal tagging implementation approach will work best. Nosto JavaScript API is useful mostly in cases where the store is doing something dynamic and not reloading the page. You can find the whole API documented here: https://developer.nosto.com/#javascript

Some of the most-used use-cases where dynamic requests or responses are needed are listed here. 

  * [Sending email addresses to Nosto](Sending-email-addresses-to-Nosto)
  * [Exposing Nosto elements in dynamic overlays](Exposing-nosto-elements-in-dynamic-overlays)
  * [Dynamically refreshing Nosto after an add-to-cart event](Dynamically-refreshing-Nosto-after-an-add-to-cart-event)
  * [Using Nosto within a SPA (single page application)](Using-Nosto-within-a-SPA-(single-page-application))