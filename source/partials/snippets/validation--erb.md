```erb
<%= form_with(url: '/abc',
              html: { novalidate: true,
                      'data-controller': 'validation',
                      'data-validation-hidden-class': 'hidden',
                      'data-validation-error-class': 'text-red-600',
                      'class': 'grid justify-center w-auto h-auto'
              }, local: true) do |form| %>
  <div aria-label="Input with addon" class="my-2">
    <%= form.label :profile_name, 'class': 'font-medium text-gray-500' %>
    <div aria-label="Form input">
      <%= form.text_field :profile_name,
                          'data-action': 'input->validation#validity',
                          'data-validation-target': 'input',
                          'data-input-has-addon': true,
                          'data-input-message': 'doldurulmalı',
                          'aria-invalid': false,
                          'class': 'focus:ring-1 focus:ring-red-600 border-2 rounded w-full h-10 focus:outline-none px-2 text-xl py-2 relative',
                          required: true %>
      <span aria-label="Addon icon">
          <img src="images/email.png" alt="">
        </span>
    </div>
  </div>
  <div aria-label="Input with addon" class="my-2">
    <%= form.label :password, 'class': 'font-medium text-gray-500' %>
    <div aria-label="Form input">
      <%= form.password_field :password,
                          'data-action': 'input->validation#validity',
                          'data-validation-target': 'input',
                          'data-input-has-addon': true,
                          'data-input-message': 'doldurulmalı',
                          'aria-invalid': false,
                          'class': 'focus:ring-1 focus:ring-red-600 border-2 rounded w-full h-10 focus:outline-none px-2 text-xl py-2 relative',
                          required: true %>
      <span aria-label="Addon icon">
          <img src="images/email.png" alt="">
        </span>
    </div>
  </div>
  <div aria-label="Input without addon" class="my-2">
    <%= form.label :site_url, 'class': 'font-medium text-gray-500' %>
    <div aria-label="Form input">
      <%= form.url_field :site_url,
                         pattern:"https?://.*",
                         size: "30",
                         placeholder: 'http://example.com or https://example.com',
                         'data-action': 'input->validation#validity',
                         'data-validation-target': 'input',
                         'data-input-has-addon': false,
                         'aria-invalid': false,
                         'data-input-message': 'doldurulmalı',
                         'data-validation-hidden-class': 'hidden',
                         'data-validation-target': 'message',
                         'data-validation-error-class': 'form__input--error',
                         'class': 'focus:ring-1 focus:ring-red-600 border-2 rounded w-full h-10 focus:outline-none px-2 text-xl py-2' %>
      <span aria-label="Addon icon">
          <img src="images/email.png" alt="">
        </span>
    </div>
  </div>

  <div class="flex">
    <label class="inline-flex items-center mt-3">
      <%= form.check_box :checkBox,
                         'data-action': 'input->validation#validity',
                         'data-validation-target': 'input',
                         'data-input-has-addon': false,
                         'aria-invalid': false,
                         'required': true,
                         'data-input-message': 'doldurulmalı',
                         'data-validation-hidden-class': 'hidden',
                         'data-validation-target': 'message',
                         'data-validation-error-class': 'form__input--error',
                         'class': 'w-3 h-3 bg-white rounded-sm border border-solid border-gray-400 appearance-none checked:bg-gray-500 checked:border-transparent ' %>
      <p class="ml-2 text-gray-600 "> <span class="underline text-gray-700 font-semibold">Kullanıcı sözleşmesini</span> okudum ve kabul ediyorum.</p>
    </label>
  </div>

  <%= form.submit "save", class: "bg-yellow-500 my-4 h-3/4 text-white text-lg font-medium rounded cursor-pointer"%>
<% end %>
```
