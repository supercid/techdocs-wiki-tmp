# Table of contents

* [Introduction](README.md)

## Implement Nosto On a Regular Site

* [Manual Tagging - Essentials](implement-nosto-on-a-regular-site/manual-implementation/README.md)
  * [Setting up your account](implement-nosto-on-a-regular-site/manual-implementation/setting-up-your-account.md)
  * [Adding the Nosto Script](implement-nosto-on-a-regular-site/manual-implementation/add-nosto-script.md)
  * [Adding the Cart Tagging](implement-nosto-on-a-regular-site/manual-implementation/cart-tagging.md)
  * [Adding the Customer information](implement-nosto-on-a-regular-site/manual-implementation/adding-the-customer-information.md)
  * [Adding the Product Tagging](implement-nosto-on-a-regular-site/manual-implementation/product-tagging/README.md)
    * [Default Product Tagging](implement-nosto-on-a-regular-site/manual-implementation/product-tagging/default-product-tagging.md)
    * [Basic Tagging](implement-nosto-on-a-regular-site/manual-implementation/product-tagging/minimum-product-tagging.md)
  * [Adding the Category/Brand Tagging](implement-nosto-on-a-regular-site/manual-implementation/category-and-brand-tagging.md)
  * [Adding the Search Tagging](implement-nosto-on-a-regular-site/manual-implementation/search-tagging.md)
  * [Adding the Order Tagging](implement-nosto-on-a-regular-site/manual-implementation/order-tagging.md)
  * [Defining Nosto placements](implement-nosto-on-a-regular-site/manual-implementation/defining-nosto-placements.md)
  * [Tagging your page types](implement-nosto-on-a-regular-site/manual-implementation/tag-your-page-types.md)
* [Advanced Usage](implement-nosto-on-a-regular-site/advanced-implementation/README.md)
  * [Extending tagging with SKUs](implement-nosto-on-a-regular-site/advanced-implementation/extending-tagging-with-skus.md)
  * [Adding support for multi-currency](implement-nosto-on-a-regular-site/advanced-implementation/adding-support-for-multi-currency.md)
  * [Adding support for customer group pricing](implement-nosto-on-a-regular-site/advanced-implementation/adding-support-for-customer-group-pricing.md)
* [FAQ](implement-nosto-on-a-regular-site/faq.md)

## Implement Nosto On a Single-Page App - Session Api

* [Session Api](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/README.md)
  * [Terminology](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/session-api-terminology.md)
  * [Setting up](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/spa-basics-setting-up.md)
  * [Managing Sessions](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/spa-basics-managing-sessions.md)
  * [Tracking Events](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/spa-basics-tracking-events.md)
  * [Leveraging Features](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/spa-basics-leveraging-features.md)
  * [Advanced Usage](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/advanced-usage/README.md)
    * [Adding support for multi-currency](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/advanced-usage/spa-adding-support-for-multi-currency.md)
    * [Adding support for customer group pricing](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/advanced-usage/spa-adding-support-for-customer-group-pricing.md)
  * [FAQ](implement-nosto-on-a-single-page-app-session-api/implementation-guide-session-api/spa-faq.md)

## 3rd party data integrations

* [3rd party data integrations](3rd-party-data-integrations/3rd-party-data-integrations/README.md)
  * [Tracking Nosto with Google Analytics Enhanced Ecommerce](3rd-party-data-integrations/3rd-party-data-integrations/tracking-nosto-with-google-analytics.md)

## Physical Retail

* [Physical Retail](physical-retail/physical-retail/README.md)
  * [Sending Offline Orders](physical-retail/physical-retail/sending-offline-orders.md)

## Native Mobile

* [Native Mobile](native-mobile/native-mobile/README.md)
  * [Implementing on iOS and Android](native-mobile/native-mobile/implementing-on-ios-and-android.md)

## JS API

* [JS API](js-api/js-apis/README.md)
  * [Initializing Nosto](js-api/js-apis/initializing-nosto.md)
  * [Recommendations](js-api/js-apis/recommendations/README.md)
    * [Loading Recommendations](js-api/js-apis/recommendations/loading-recommendations.md)
    * [Recommendation Callbacks](js-api/js-apis/recommendations/recommendation-callbacks.md)
    * [Setting up dynamic filtering](js-api/js-apis/recommendations/setting-up-dynamic-filtering.md)
  * [Popups](js-api/js-apis/popups/README.md)
    * [Listing Popup Campaigns](js-api/js-apis/popups/listing-popup-campaigns.md)
    * [Opening a Popup](js-api/js-apis/popups/opening-a-popup.md)
    * [Enabling & Disabling Popups](js-api/js-apis/popups/enabling-and-disabling-popups.md)
    * [Popup Callbacks](js-api/js-apis/popups/popup-callbacks.md)
  * [Common Examples](js-api/js-apis/common-examples/README.md)
    * [Sending Product-View Events](js-api/js-apis/common-examples/sending-product-view-events.md)
    * [Sending Add-To-Cart Events](js-api/js-apis/common-examples/sending-add-to-cart-events.md)
    * [Sending Customer Information](js-api/js-apis/common-examples/sending-customer-information.md)
    * [Sending email addresses to Nosto](js-api/js-apis/common-examples/sending-email-addresses-to-nosto.md)
    * [Manually segmenting users](js-api/js-apis/common-examples/manually-segmenting-users.md)

## APIs

* [APIs Introduction](apis/apis/README.md)
  * [GDPR](apis/apis/gdpr/README.md)
    * [Redacting customer data](apis/apis/gdpr/sanitizing-customer-data-using-the-redaction-api.md)
    * [Initiating data takeouts](apis/apis/gdpr/initiating-data-takeouts-via-the-takeout-apis.md)
  * [Customers](apis/apis/customers/README.md)
    * [Blacklisting Customers](apis/apis/customers/blacklisting-customers-using-the-blacklist-api.md)
    * [Toggling marketing consent](apis/apis/customers/toggling-email-opt-in-using-the-consent-api.md)
  * [Products](apis/apis/products/README.md)
    * [Updating Products](apis/apis/products/updating-products-using-the-products-api.md)
    * [Discontinuing Products](apis/apis/products/discontinuing-products.md)
    * [Recrawling Products](apis/apis/products/recrawling-products-using-the-recrawl-api.md)
  * [Other](apis/apis/other/README.md)
    * [Updating Rates](apis/apis/other/updating-rates-using-the-rates-api.md)

## GraphQL

* [GraphQL](graphql/graphql-an-introduction/README.md)
  * [The Playground](graphql/graphql-an-introduction/graphql-the-playground.md)
  * [Using the API](graphql/graphql-an-introduction/graphql-using-the-api.md)
  * [Testing and Debugging](graphql/graphql-an-introduction/graphql-testing-and-debugging.md)
  * [Using Mutations](graphql/graphql-an-introduction/graphql-using-mutations/README.md)
    * [Updating Products](graphql/graphql-an-introduction/graphql-using-mutations/graphql-updating-products.md)
    * [Updating Identities](graphql/graphql-an-introduction/graphql-using-mutations/graphql-updating-identities.md)
    * [GraphQL: Onsite Sessions](graphql/graphql-an-introduction/graphql-using-mutations/graphql-onsite-sessions.md)
    * [Working with Orders](graphql/graphql-an-introduction/graphql-using-mutations/working-with-orders/README.md)
      * [GraphQL: Placing Orders](graphql/graphql-an-introduction/graphql-using-mutations/working-with-orders/graphql-placing-orders.md)
      * [GraphQL: Updating Order Statuses](graphql/graphql-an-introduction/graphql-using-mutations/working-with-orders/graphql-updating-order-statuses.md)
  * [Using Queries](graphql/graphql-an-introduction/graphql-using-queries/README.md)
    * [Querying Products](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-products.md)
    * [Querying Identities](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-identities.md)
    * [Querying Orders](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-orders.md)
    * [Querying Recommendations](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-recommendations.md)
    * [Querying Segments](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-segments.md)
    * [Querying Category Merchandising Products](graphql/graphql-an-introduction/graphql-using-queries/graphql-querying-category-merchandising-products.md)
  * [For iOS & Android](graphql/graphql-an-introduction/graphql-for-ios-and-android.md)
  * [For Headless](graphql/graphql-an-introduction/graphql-for-headless.md)
  * [FAQ](graphql/graphql-an-introduction/graphql-faq.md)

