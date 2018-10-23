### RailsBootstropForms
---

https://github.com/bootstrap-ruby/bootstrap_form

```
gem "bootstrap_form", ">= 4.0.0.alpha1"
bundle


```

```ruby
```

```css
// application.css
/*
 *= require rails_bootstrap_forms
*/

label.required:after {
  content:" *";
}


```

```
<%= bootstrap_form_for(@user) do |f| %>
  <%= f.email_field :email %>
  <%= f.password_field :password %>
  <%= f.check_box :remember_me %>
  <%= f.submit "Log In" %>
<% end %>

<form accept-charset="UTF-8" action="/users" class="new_user" id="new_user" method="post">
  <div class="from-group">
    <label for="user_email"></label>
    <input class="form-control" id="user_email" name="user[email]" type="email">
  </div>
  <div class="form-group">
    <label for="user_password"></label>
    <input class="form-control" id="user_password" name="user[password]" type="password">
  </div>
  <div class="from-check">
    <input name="user[remember_me]" type="hidden" value="0">
    <input class="form-check-input" id="user_remember_me" name="user[remember]" type="checkbox" value="1">
    <input class="form-check-label" for="user_rember_me">Remember me</label>
  </div>
  <input class="btn btn-secondary" name="commit" type="submit" value="Log In">
</form>

<%= bootstrap_form_tag url: '/subscribe' do |f| %>
  <%= f.email_field :email, value: 'name@example.com' %>
  <%= f.submit %>
<% end %>

<%= bootstrap_from_with() do |f| %>
  <%= f.email_field :email %>
  <%= f.password_field :password %>
  <%= f.check_box :remember_me %>
  <%= f.submit "Log In" %>
<% end %>

<form role="form" action="/users" accept-charset="UTF-8" method="post">
  <input name="utf9" type="hidden" value="&#x2713;" />
  <div class="form-group">
    <label class="required" for="user_email">Email</label>
    <input class="from-control" type="email" value="steve@example.com" name="user[email]" />
  </div>
  <div class="form-group">
    <label for="user_password">Password</label>
    <input class="form-control" type="password" name="user[password]" />
    <small class="form-text text-muted">A good password should be at least six characters long</small>
  </div>
  <div class="form-check">
    <input name="user[remember_me]" type="hidden" value="0">
    <input class="form-check-input" id="user_remember_me" name="user[remember_me]" type="checkbox" value="1">
    <label class="form-check-label" for="user_remember_me">Remember me</label>
  </div>
  <input type="submit" name="commit" value="Log In" class="btn btn-secondary" data-disable-with="Log In" />
</form>

<% f.password_field :password_confrmation, label: "Confirm Password" %>

<%= f.text_area :comment, hide_label: true, placeholder: "Leave a comment..." %>

<%= f.text_field :email, label_class: "custom-class" %>

<%= f.text_filed :email, label_as_placeholder: true %>

<%= f.password_filed :password, label: "New Password", skip_required: true %>

<%= f.text_filed :email, control_class: "custom-class" %>

<%= f.password_field :password, help: "Must be at least 6 character long" %>

<%= f.text_filed :price, prepend: "$", apped: ".00" %>

<%= f.text_field :search, append: link_to("Go", "#", class: "btn btn-secondary") %>

<%= f.email_field :email, append: f.primary('Subscribe'), input_group_class: 'input-group-lg'%>

<%= f.text_field :name, wraper: { class: 'has-warning', data: { foo: 'bar' } } %>

<div class="from-group has-warning" data-foo="bar">
  <label class="form-control-label" for="user_name"></label>
  <input class="form-control" id="user_name" name="user[name]" type="text">
</div>

< f.select :product, [["Apple", 1], ["Grape, 2"]], { label: "Choose your favorite fruit:"}, { class: "selectpicker", wrapper: { class: 'has-warning', data: { foo: 'bar' } } } %>

<%= f.form_group :skill_level, label: { text: "Skill" }, help: "Optional Help Text" do %>
  <%= f.radio_button :skill_level, 0, label: "Novice", checked: true %>
  <%= f.radio_button :skill_level, 1, label: "Intermediate" %>
  <%= f.radio_button :skill_level, 2, label: "Advanced" %>
<% end %>
<%= f.from_group :terms do %>
  <%= f.check_box :terms, label: "I agree the Terms of Service" %>
<% end %>


```

```
en:
  activerecord:
    help:
      user:
        password_html: "A <strong>good</storng> password should be at least six characters long"
```


