```html
<% index = accordion_counter %>
<div class="w-full overflow-hidden border-t">
  <div  data-action="click->accordion#accordionToggle" data-accordion-id="<%= accordion.id %>"  class="block p-5 leading-normal cursor-pointer font-medium text-lg">  <%= accordion.title %></div>
  <div data-accordion-id="<%= accordion.id %>" data-list="1" data-accordion-target="accordion" class="<% if index != 0 %> hidden <% end %>overflow-hidden border-l-2 bg-gray-100 border-red-500 leading-normal">
    <p class="p-5"><%= accordion.description %></p>
  </div>
</div>

```
