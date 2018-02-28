Nosto supports individual product SKUs under parent products. If you have not set up [Product tagging](https://github.com/Nosto/docs-nosto-com/wiki/Product-Tagging) you should start there and extend the tagging if needed. 

The SKU attributes should be listed on the last row of the `nosto_product` block that you have already implemented on the product pages. 

```html
<div class="nosto_product" style="display:none">
  <span class="nosto_sku">
    <span class="id">1</span>
      <span class="name">S-Orange</span>
      <span class="price">1269.00</span>
      <span class="list_price">1299.00</span>
      <span class="url">http://www.example.com/product/CANOE123#/1-size-s/13-color-orange</span>
      <span class="image_url">http://www.example.com/product/images/CANOE123-1.jpg</span>
      <span class="availability">InStock</span>
      <span class="custom_fields">
        <span class="size">S</span>
        <span class="color">Orange</span>
      </span>
  </span>

  <span class="nosto_sku">
    <span class="id">2</span>
      <span class="name">S-Blue</span>
      <span class="price">1269.00</span>
      <span class="list_price">1299.00</span>
      <span class="url">http://www.example.com/product/CANOE123#/1-size-s/14-color-blue</span>
      <span class="image_url">http://www.example.com/product/images/CANOE123-2.jpg</span>
      <span class="availability">InStock</span>
      <span class="custom_fields">
        <span class="size">S</span>
        <span class="color">Blue</span>
      </span>
   </span>

</div>
```

>**Note:** The attribute `custom_fields` can contain whatever unique information for individual SKUs that you can >consider helpful. Frequently used attributes would be size, color, material.