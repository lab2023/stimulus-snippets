```html
<div data-controller="textarea"
     data-textarea-lenght-value="250"
     data-textarea-danger-class="text-red-600" class="font-medium ">
  <label for="biography" class="text-gray-400 ">
    Biography<small>(<span data-textarea-target="lenght">250</span>)</small>
  </label>
  <div>
 <textarea name="biography"
           id="biography"
           data-textarea-target="textarea"
           data-action="input->textarea#update" class="border-2 font-medium " rows="10" cols="50"></textarea>
  </div>
</div>

```
