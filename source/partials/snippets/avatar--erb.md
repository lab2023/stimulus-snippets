```erb
  <%= form_with(model: [:user, profile],
                html: { 'data-controller': 'avatar',
                        'data-avatar-size-value': '5000000'}) do |form| %>
    <%= image_tag "/assets/human.png", 'data-avatar-target': "image", "class": "text-center mx-auto w-24 h-24  left-2 top-2 rounded-full my-5"  %>

    <label for="file" >
    <p class="text-center mx-auto rounded-full bg-white text-gray-900 border w-60 h-9 cursor-pointer hover:bg-gray-900 hover:text-white px-4 py-1 "> Avatarı Değiştir </p>
    <%= form.file_field :avatar,
                        accept: '.png, .jpg, .jpeg',
                        'data-action': 'change->avatar#upload', 'class': 'hidden py-1 px-5 rounded-full bg-white text-gray-900 border  h-9 focus:cursor-pointer focus:bg-gray-900 focus:text-white' %>
                          </label>
   <div class="my-5 text-center mx-9 font-medium">
    <p data-avatar-target="message" >
      Avatar ".png, .jpg, .jpeg" dosya tipinde olmalı ve dosya boyutu 5 Megabyte'dan küçük olmalıdır.
    </p>
  </div>
  <% end %>
```
