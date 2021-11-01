```erb
<div aria-label="Lightbox" data-controller="lightbox" class="flex  bg-white justify-center ">
<%= render partial: "components/lightbox", collection: @slider_image_list, as: :image_list%>
</div>
```