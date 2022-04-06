```erb
<div class="relative"
       data-controller="slider"
       data-slider-auto-value="false"
       data-slider-speed-value="3000"
       data-action="mouseover->slider#mouseOver mouseout->slider#mouseOut">

    <div class="">
      <div data-slider-target="slide" class="flex justify-center items-center h-64 w-full bg-blue-500 text-9xl rounded-lg">1</div>
      <div data-slider-target="slide" class="flex justify-center items-center h-64 w-full bg-purple-500 text-9xl rounded-lg hidden">2</div>
      <div data-slider-target="slide" class="flex justify-center items-center h-64 w-full bg-yellow-500 text-9xl rounded-lg hidden">3</div>
      <div data-slider-target="slide" class="flex justify-center items-center h-64 w-full bg-green-500 text-9xl rounded-lg hidden">4</div>
    </div>

    <button data-action="slider#prev" class="flex justify-center items-center absolute top-0 left-0 z-30 px-4 h-full cursor-pointer">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
      </svg>
    </button>

    <button data-action="slider#next" class="flex justify-center items-center absolute top-0 right-0 z-30 px-4 h-full cursor-pointer">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
      </svg>
    </button>
  </div>
```
