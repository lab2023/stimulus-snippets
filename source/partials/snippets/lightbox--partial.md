```html
<div data-lightbox-target="thumbnail" class=" my-5 mx-2 rounded-md  bg-black box-content w-32 h-32">
    <button type="button"
            data-action="click->lightbox#open"
            data-lightbox-target="image_button"
            data-lightbox-id="<%= image_list.id %>"
            data-lightbox-img="<%= image_list.imageUrl %>"
            class="w-full h-full">
      <img src="<%= image_list.imageUrl %>" class="w-auto mx-auto h-full rounded-md" alt="">
    </button>
  </div>
```