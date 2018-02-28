Nosto utilizes meta tags to track what category a certain visitor is viewing or what page type the currently viewed page is. These values are then used for dynamic filtering for categories applied through the Nosto admin UI or exposure of certain pop-up campaigns for page types.  

Category tagging should be exposed whenever a user is viewing a certain category. 
```html
<div class="nosto_category" style="display:none">/Boats/Canoes</div>
```
Page type tagging should be exposed whenever a user is interacting with a page so Nosto understands what kind of page this is. 
```html
<div class="nosto_page_type" style="display:none">product</div>
```

>**Note:** The accepted values for page type are: front, category, product, cart, order, search, notfound

**Troubleshooting category/page type tagging:**

Once included on all pages, you can review if the site is transmitting data using the Nosto Debug Toolbar. If you can see order contents being picked up under "Tagging" → "Category" then the category and page type tagging are correctly set up in the source code.

![Nosto debug category ](https://nosto-campaign-assets.s3.amazonaws.com/images/nosto-debug-toolbar-category.png)
