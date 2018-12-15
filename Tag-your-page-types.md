The page-type tagging enables Nosto to trigger actions, such as showing popups, depending upon a page type. Tagg the page types is optional but you won't be able to avail the use of page type based triggers. 

Here is a list of all the valid page types:

* The home page of your store should be tagged as `front`.
* All category pages should be tagged as `category`.
* All product pages should be tagged as `product`.
* The shopping cart and checkout pages should be tagged as `cart`.
* The order confirmation page should be tagged as `order`.
* The search results page should be tagged as `search`.
* All no-found pages should be tagged as `notfound`.
* All the remaining pages that should be tagged as `other`.

```html
 <div class="nosto_page_type" style="display:none">product</div>
```