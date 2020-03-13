> A single-page application (SPA) is a web application or web site that interacts with the user by dynamically rewriting the current page rather than loading entire new pages from a server. This approach avoids interruption of the user experience between successive pages, making the application behave more like a desktop application. In a SPA, either all necessary code – HTML, JavaScript, and CSS – is retrieved with a single page load,[1] or the appropriate resources are dynamically loaded and added to the page as necessary, usually in response to user actions. The page does not reload at any point in the process, nor does control transfer to another page, although the location hash or the HTML5 History API can be used to provide the perception and navigability of separate logical pages in the application.[2] Interaction with the single page application often involves dynamic communication with the web server behind the scenes.

If you have a website, that is built atop JavaScript frameworks, such as AngularJS, Ember.js, ExtJS, Knockout.js, Meteor.js, React or Vue.js, your site has likely adopted SPA principles.

**Important**: You cannot mix [JS API](JS-APIs.md) and Session API. You need to use either or. If you are not sure which one to use, please contact Nosto's support.  

**Note:** The examples in the documentation are written in [ES5](https://www.ecma-international.org/ecma-262/5.1/) and leverage advanced browser features such as [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

  * [Terminology](Session-API---Terminology.md)
  * [Setting up your account](SPA:-Basics.md#Setting-up-your-account)
  * [Setting up the catalog sync](SPA:-Basics.md#setting-up-the-catalog-sync)
  * [Adding the Nosto Script](SPA:-Basics.md#Add-Nosto-script)
  * Managing Sessions
    * [Setting the cart](SPA:-Basics.md#setting-the-cart)
    * [Setting the customer](SPA:-Basics.md#setting-the-customer)
  * Tracking Events
    * [Upon viewing the homepage](SPA:-Basics.md#upon-viewing-the-homepage) 
    * [Upon viewing a product](SPA:-Basics.md#upon-viewing-a-product)
    * [Upon viewing a collection](SPA:-Basics.md#upon-viewing-a-collection)
    * [Upon doing a search](SPA:-Basics.md#upon-doing-a-search)
    * [Upon starting a checkout](SPA:-Basics.md#upon-starting-a-checkout)
    * [Upon placing an order](SPA:-Basics.md#upon-placing-an-order)
* Leveraging Features
  * [Working with recommendations](SPA:-Basics.md#working-with-recommendations)
  * [Working with content](SPA:-Basics.md#working-with-content)
  * [Working with popups](SPA:-Basics.md#working-with-popups)
* Advanced Usage
  * [Adding support for multi-currency](SPA:-Adding-support-for-multi-currency)
  * [Adding support for customer group pricing](SPA:-Adding-support-for-customer-group-pricing)
* FAQ:
  * [How do I track recommendation clicks?](SPA:-FAQ#how-do-i-track-clicks-on-recommendations)
  * [How do I track external ad campaigns?](SPA:-FAQ#tracking-external-advertisement-campaigns)
