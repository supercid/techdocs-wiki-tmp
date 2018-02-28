Nosto utilizes a proprietary Crawler mechanism to fetch product data from the online store. The crawler makes sure that new products which have not been discovered yet will be added to the catalogue whenever users interact with them. The crawler is designed to fire on certain actions which are the following: 

* Every time a new product is viewed.
* Every 3rd visit to a already known product.
* After every order of a certain product.

You can also schedule a manual reindex of your entire catalogue whenever you bulk update a lot of information in the store (for example after a platform switch where all the product ids change). You can find this panel under Tools -> Products -> Update Products in the Nosto admin UI.

![Recrawl products](https://nosto-campaign-assets.s3.amazonaws.com/images/recrawl-products.png)

In some instances you might need to whitelist the crawler manually if you are working in a development environment that is blocked for other than whitelisted users. The crawler works with ever changing IP-addresses but you can use the following header/agent details to whitelist the crawler.

```
Mozilla/5.0 (compatible; NostoCrawlerBot/1.0; +http://my.nosto.com/tagging)
```