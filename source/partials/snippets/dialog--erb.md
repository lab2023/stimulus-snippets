```html
<details aria-label="Deatils dialog" class="list-none text-center z-2" data-controller="dialog">
  <summary class=" inline-block  font-bold mt-10" role="button">Open dialog</summary>
  <div class=" h-screen w-full fixed left-0 top-0 flex justify-center items-center bg-black bg-opacity-50">
    <!-- modal -->
    <div class="bg-white rounded shadow-lg w-10/12 md:w-1/3">
      <!-- modal header -->
      <div class="border-b px-4 py-2 flex justify-between items-center">
        <h3 class="font-semibold text-lg">Title</h3>
        <button class="text-black" data-action="click->dialog#close">&#10005;</button>
      </div>
      <!-- modal body -->
      <div class="p-3">
        Modal body text goes here.
      </div>
      <div class="flex justify-end items-center w-100 border-t p-3">
        <button class="bg-red-600 hover:bg-red-700 px-3 py-1 rounded text-white mr-1" data-action="click->dialog#close">Cancel</button>
        <button class="bg-blue-600 hover:bg-blue-700 px-3 py-1 rounded text-white">Save </button>
      </div>
    </div>
  </div>
</details>

```
