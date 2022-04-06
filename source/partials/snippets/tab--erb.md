```html
<div data-controller="tab" class="grid grid-flow-row text-center">
  <div class="grid grid-flow-col">
    <button data-action="click->tab#changeTab"
            data-tab-id-param="0"
            data-tab-target="firstTab"
            type="button" class="tab-link tab-active">Tab 1</button>
    <button data-action="click->tab#changeTab"
            data-tab-id-param="1"
            type="button" class="tab-link">Tab 1</button>
    <button data-action="click->tab#changeTab"
            data-tab-id-param="2"
            type="button" class="tab-link">Tab 1</button>
  </div>
  
  <div>
    <div class="h-48 bg-red-500" data-tab-target="tabContent">
    </div>
    <div class="h-48 bg-green-500 hidden" data-tab-target="tabContent">
    </div>
    <div class="h-48 bg-blue-500 hidden" data-tab-target="tabContent">
    </div>
  </div>
</div>
```