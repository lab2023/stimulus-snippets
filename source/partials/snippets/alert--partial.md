``` html
<% flash.each do |type, msg| %>
  <div data-controller="alert" class="text-white px-6 py-4  rounded relative mb-4 <%= flashTypeBgColor(type) %> w-6/12 mx-auto text-center my-4">
    <span class="text-xl inline-block mr-5 align-middle w-8 h-8 float-left">
      <%= raw flashTypeIcon(type) %>
    </span>
    <span class="inline-block align-middle mr-8 text-black text-thin">
      <%= msg %>
    </span>
    <button class="absolute bg-transparent text-2xl text-black font-semibold leading-none right-0 top-0 mt-4 mr-6 outline-none focus:outline-none">
      <span data-action="click->alert#closeAlert">×</span>
    </button>
  </div>

<% end %>
```
