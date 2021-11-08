``` html
<div class="flex justify-center items-center h-screen bg-gray-200"
     data-controller="tooltip"  >
  <div data-action="mouseover->tooltip#over mouseout->tooltip#out" data-tooltip-title="This is right tooltip" data-tooltip-placement="right" class="relative inline-block">
    <button  type="button"   class="bg-blue-600 text-gray-200 rounded hover:bg-blue-500  mx-4 px-4 py-2 focus:outline-none">Right</button>
  </div>

  <div data-action="mouseover->tooltip#over mouseout->tooltip#out" data-tooltip-title="This is right tooltip" data-tooltip-placement="left" class="relative inline-block">
    <button  type="button"   class="bg-blue-600 text-gray-200 rounded hover:bg-blue-500  mx-4 px-4 py-2 focus:outline-none">Left</button>
  </div>

  <div data-action="mouseover->tooltip#over mouseout->tooltip#out" data-tooltip-title="This is right tooltip" data-tooltip-placement="bottom" class="relative inline-block">
    <button  type="button"   class="bg-blue-600 text-gray-200 rounded hover:bg-blue-500  mx-4 px-4 py-2 focus:outline-none">Bottom</button>
  </div>

  <div data-action="mouseover->tooltip#over mouseout->tooltip#out" data-tooltip-title="This is right tooltip" data-tooltip-placement="top" class="relative inline-block">
    <button  type="button"   class="bg-blue-600 text-gray-200 rounded hover:bg-blue-500  mx-4 px-4 py-2 focus:outline-none">Top</button>
  </div>

</div>
```
