In this article, you will learn to use certain tags and fields to dynamically filter and facet your recommendation results.

You can use any combination of the different filtering mechanisms outlined below. For example, you can use category and the tag filtering to constrain the recommendation results.

## Filtering by tags

You can filter by tags to narrow down the recommendation results to only show products containing the specified tag or tags. If multiple tags are specified, the products must contain all the specified tags.

```html
<div class="nosto_tag" style="display:none">colourful</div>
```

You can even use multiple

```html
<div class="nosto_tag" style="display:none">colourful</div>
<div class="nosto_tag" style="display:none">shiny</div>
```

## Filtering by attributes

You can filter by attributes to narrow down the recommendation results to only show products containing the specified attributes. If multiple attributes are specified, the products must contain all the attributes.

```html
<div class="nosto_custom_field" style="display:none">gender:male</div>
```

You can even use multiple

```html
<div class="nosto_custom_field" style="display:none">gender:male</div>
<div class="nosto_custom_field" style="display:none">material:cotton</div>
```

## Filtering by categories

You can filter by categories to narrow down the recommendation results to only show products from the specified category or categories. If multiple categories are specified, the products must be in each of those categories.

```html
<div class="nosto_category" style="display:none">/Men's/Shirts</div>
```

You can even use multiple

```html
<div class="nosto_category" style="display:none">/Men's/Shirts</div>
<div class="nosto_category" style="display:none">/Men's/Sale</div>
```