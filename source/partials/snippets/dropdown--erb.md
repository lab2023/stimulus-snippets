```erb
<div data-controller="dropdown">
  <details aria-label="Details" data-dropdown-target="dropdown" class="details-reset dropdown ">

    <summary data-action="click->dropdown#openDropdown" data-dropdown-target="dropdown__toggle" class="float-right m-3 inline-block w-8 h-8 bg-no-repeat bg-center " role="button">

    </summary>


    <section aria-label="Dropdown">
      <nav aria-label="Mobile nav" class=" grid absolute top-14 z-10 w-11/12 lg:mx-16 md:mx-10 mx-4 list-none justify-center  bg-gray-100 rounded-md text-center">
        <li class="m-5 font-medium">
          Link
        </li>
        <li class="m-5 font-medium">
          Link
        </li>
        <li class="m-5 font-medium">
          Link
        </li>
        <li class="m-5 font-medium">
          Link
        </li>
      </nav>
    </section>
  </details>
  <div class="border-b-2 bg-white w-full h-24 top-12 "></div>
  <div class="block  text-center">
    <a href="#" class="inline bottom-10 relative m-5 font-medium rounded-sm text-black border-b-4 border-white hover:border-yellow-500 hover:bg-white hover:text-black pb-2">Link</a>
    <a href="#" class="inline bottom-10 relative m-5 font-medium rounded-sm text-black border-b-4 border-white hover:border-yellow-500 hover:bg-white hover:text-black  pb-2">Link</a>
    <a href="#" class="inline bottom-10 relative m-5  font-medium rounded-sm text-black border-b-4 border-white hover:border-yellow-500 hover:bg-white hover:text-black pb-2">Link</a>
  </div>
</div>
```