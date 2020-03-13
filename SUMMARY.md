* Implement Nosto
  * On a regular site
    * [Manual Tagging - Essentials](Manual-implementation.md)
      * [Setting up your account](Setting-up-your-account.md)
      * [Adding the Nosto Script](Add-Nosto-script.md)
      * [Adding the Cart Tagging](Cart-Tagging.md)
      * [Adding the Customer information](Adding-the-customer-information.md)
      * [Adding the Product Tagging](Product-Tagging.md)
        * [Default Product Tagging](Basic/Default-Product-Tagging.md)
        * [Basic Tagging](Basic/Minimum-Product-Tagging.md)
      * [Adding the Category/Brand Tagging](Category-&-Brand-tagging.md)
      * [Adding the Search Tagging](Search-Tagging.md)
      * [Adding the Order Tagging](Order-Tagging.md)
      * [Defining Nosto placements](Defining-Nosto-placements.md)
      * [Tagging your page types](Tag-your-page-types.md)
    * [Advanced Usage](Advanced-implementation.md)
      * [Extending tagging with SKUs](Extending-tagging-with-SKUs.md)
      * [Adding support for multi-currency](Adding-support-for-multi-currency.md)
      * [Adding support for customer group pricing](Adding-support-for-customer-group-pricing.md)
    * [FAQ](Basic/FAQ.md)
  * [On a Single-Page App (Session API.md)](SPA/Implementation-Guide-(Session-API.md).md)
      * [Terminology](Session-API---Terminology.md)
      * [Setting up your account](SPA/Basics#Setting-up-your-account.md)
      * [Setting up the catalog sync](SPA/Basics#setting-up-the-catalog-sync.md)
      * [Adding the Nosto Script](SPA/Basics#Add-Nosto-script.md)
      * Managing Sessions
        * [Setting the cart
](SPA/Basics#setting-the-cart.md)
        * [Setting the customer
](SPA/Basics#setting-the-customer.md)
       * Tracking Events
         * [Upon viewing the homepage](SPA/Basics#upon-viewing-the-homepage.md) 
         * [Upon viewing a product
](SPA/Basics#upon-viewing-a-product.md)
         * [Upon viewing a collection
](SPA/Basics#upon-viewing-a-collection.md)
         * [Upon doing a search
](SPA/Basics#upon-doing-a-search.md)
         * [Upon starting a checkout
](SPA/Basics#upon-starting-a-checkout.md)
         * [Upon placing an order](SPA/Basics#upon-placing-an-order.md)
         * [Upon a not found page](SPA/Basics#upon-viewing-a-page-that-was-not-found-404.md)
    * Leveraging Features
      * [Working with recommendations](SPA/Basics#working-with-recommendations.md)
      * [Working with content](SPA/Basics#working-with-content.md)
      * [Working with popups](SPA/Basics#working-with-popups.md)
    * Advanced Usage
      * Extending tagging with SKUs
      * [Adding support for multi-currency](SPA/Adding-support-for-multi-currency.md)
      * [Adding support for customer group pricing](SPA/Adding-support-for-customer-group-pricing.md)
    * [FAQ](SPA/FAQ.md)
* [3rd party data integrations](3rd-party-data-integrations.md)
  * [Tracking Nosto with Google Analytics Enhanced Ecommerce](Tracking-Nosto-with-Google-Analytics.md)
* [Physical Retail](Physical-Retail.md)
  * [Sending Offline Orders](Sending-Offline-Orders.md)
* [Native Mobile](Native-Mobile.md)
  * [Implementing on iOS and Android](Implementing-on-iOS-and-Android.md)
* [JS API](JS-APIs.md)
  * [Initializing Nosto](Initializing-Nosto.md)
  * [Recommendations](Recommendations.md)
    * [Loading Recommendations](Loading-Recommendations.md)
    * [Recommendation Callbacks](Recommendation-Callbacks.md)
    * [Setting up dynamic filtering](Setting-up-dynamic-filtering.md)
  * [Popups](Popups.md)
    * [Listing Popup Campaigns](Listing-Popup-Campaigns.md)
    * [Opening a Popup](Opening-a-Popup.md)
    * [Enabling & Disabling Popups](Enabling-&-Disabling-Popups.md)
    * [Popup Callbacks](Popup-Callbacks.md)
  * Common Examples
    * [Sending Product-View Events](Sending-Product-View-Events.md)
    * [Sending Add-To-Cart Events](Sending-Add-To-Cart-Events.md)
    * [Sending Customer Information](Sending-customer-information.md)
    * [Sending email addresses to Nosto](Sending-email-addresses-to-Nosto.md)
    * [Manually segmenting users](Manually-Segmenting-Users.md)
* [APIs](APIs.md)
  * GDPR
    * [Redacting customer data](Sanitizing-customer-data-using-the-Redaction-API.md)
    * [Initiating data takeouts](Initiating-data-takeouts-via-the-Takeout-APIs.md)
  * Customers
    * [Blacklisting Customers](Blacklisting-customers-using-the-Blacklist-API.md)
    * [Toggling marketing consent](Toggling-email-opt-in-using-the-Consent-API.md)
  * Products
    * [Updating Products](Updating-products-using-the-Products-API.md)
    * [Discontinuing Products](Discontinuing-Products.md)
    * [Recrawling Products](Recrawling-products-using-the-Recrawl-API.md)
  * Other
    * [Updating Rates](Updating-Rates-using-the-Rates-API.md)
* [GraphQL](GraphQL/An-Introduction.md)
    * [The Playground](GraphQL/The-Playground.md)
    * [Using the API](GraphQL/Using-the-API.md)
    * [Testing and Debugging](GraphQL/Testing-&-Debugging.md)
    * [Using Mutations](GraphQL/Using-Mutations.md)
        * [Updating Products](GraphQL/Updating-Products.md)
        * [Updating Identities](GraphQL/Updating-Identities.md)
        * [GraphQL: Onsite Sessions
](GraphQL/Onsite-Sessions.md)
        * Working with Orders
          * [GraphQL: Placing Orders
](GraphQL/Placing-Orders.md)
          * [GraphQL: Updating Order Statuses
](GraphQL/Updating-Order-Statuses.md)
    * [Using Queries](GraphQL/Using-Queries.md)
        * [Querying Products](GraphQL/Querying-Products.md)
        * [Querying Identities](GraphQL/Querying-Identities.md)
        * [Querying Orders](GraphQL/Querying-Orders.md)
        * [Querying Recommendations](GraphQL/Querying-Recommendations.md)
        * [Querying Segments](GraphQL/Querying-Segments.md)
        * [Querying Category Merchandising Products](GraphQL/Querying-Category-Merchandising-Products.md)
    * [For iOS & Android](GraphQL/For-iOS-&-Android.md)
    * [For Headless](GraphQL/For-Headless.md)
    * [FAQ](GraphQL/FAQ.md)