Its important to understand a few of the concepts around how Nosto exchanges data between the site and our own backend, to make sure that you as a integrator understand the different steps and tools required. 

* Nosto initializes by using a [snippet of Javascript](https://github.com/Nosto/docs-nosto-com/wiki/Add-Nosto-script) that starts the dialogue to your dedicated account. 
* Nosto depends on structured data that we extract from your site. At the bare minimum you need to go through all the steps listed under [Manual Implementation - Essentials](https://github.com/Nosto/docs-nosto-com/wiki/Manual-implementation).
* Nosto utilizes a proprietary [Crawler](https://github.com/Nosto/docs-nosto-com/wiki/Nosto-crawler) to fetch product data from the online store. The crawler makes sure that new products which have not been discovered yet will be added to the catalogue whenever users interact with them.

It is important to understand that even if you augment the data collection process by following either the [Products API](https://github.com/Nosto/docs-nosto-com/wiki/Updating-products-using-the-Products-API) or [Recrawl API](https://github.com/Nosto/docs-nosto-com/wiki/Updating-products-using-the-Recrawl-API) you should still go ahead with tagging your site with metadata as detailed in [Manual Implementation - Essentials](https://github.com/Nosto/docs-nosto-com/wiki/Manual-implementation). These APIs are designed to augment the data collection process, not supersede it. 

