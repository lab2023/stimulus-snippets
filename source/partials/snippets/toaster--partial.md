```html
<div class="absolute z-10 right-0">
  <% flash.each do |type, msg| %>
  <div  class="grid justify-items-end">
    <section data-controller="toaster"
             data-action="animationend->toaster#animationEnd"
             data-toaster-type-class="<%= toasterTypeBgColor(type) %>"
             data-toaster-in-class="animate-slide-in-right"
             data-toaster-out-class="animate-fade-out-right"
             data-toaster-has-progress-value="true"
             data-toaster-target="toaster_container"
             class="mr-3 w-80 duration-300 animate-slide-in-right z-10 my-5 rounded-t-md">
      <div class="flex">
        <p class="flex pl-10 mt-2">
          <%= toasterTypeTitle(type) %>
        </p>
        <button data-action="click->toaster#close" class="float-right border-gray-600 border rounded-md  font-medium px-4 m-auto mr-5 mt-2">&#10005;</button>

      </div>
      <div class=" border-b border-black my-2"></div>
      <div class="flex">
        <p class=" pl-5 pr-30 my-2 font-medium">
          <%= msg %>
        </p>
      </div>
      <div aria-label="Progress bar"
           role="progressbar"

           data-toaster-target="progress" class="w-full h-1 mt-4 rounded-2xl bg-gray-400 transition duration-100 ease-linear">
      </div>
    </section>
  </div>
  <%end %>
</div>
```
