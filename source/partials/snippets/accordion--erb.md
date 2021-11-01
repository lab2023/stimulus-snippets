```html
<div class="pt-10">
  <div class="w-full md:w-3/5 mx-auto p-8">
    <div class="shadow-md" data-controller="accordion" >
      <%= render partial: "components/accordion", collection: @accordions, as: :accordion%>
    </div>
 </div>
</div>

```
