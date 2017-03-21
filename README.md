# ShopifyKnockoutFilters
Knockout filters for Shopify using regular 'ol Shopify tags

Add this snippet to your collection.liquid file.

``` liquid
<div data-bind="visible: filtersVisible">
  <div class="grid--colection-tag-categories" data-bind="foreach: collectionTagCategories">
    <div class="tagCategory">
      <h6 data-bind="text: type"></h6>
      <div class="tags" data-bind="foreach: tags">
        <div class="checkbox">
          <label>
            <input type="checkbox" data-bind="attr: { value: machineName, name: machineName }, click: $root.checkedChangeUrl, checked: isChecked"> <span data-bind="text: tagName"></span>
          </label>
        </div>
      </div>
    </div>
  </div>
  <a href="#" class="clear-filters" data-bind="click: clearFilters">Clear Filters</a>
</div>
<div data-bind="visible: hasFilters()">
  <div>
    <a class="button" data-bind="click: toggleVisible, text: buttonText()"></a>
  </div>
</div>

{% include 'sort-and-process-filter-tags' %}
```

Place this script tag into your header:
``` liquid 
{{ '//cdnjs.cloudflare.com/ajax/libs/knockout/3.4.1/knockout-min.js' | script_tag }}
```

Create a new file called ```sort-and-process-liquid-tags.liquid``` and add it to snippets.
