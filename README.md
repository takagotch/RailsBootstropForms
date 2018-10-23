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

<%= f.from_group :terms, label: { text: "Optional Label" } do %>
  <%= f.check_box :terms do %>
    txt
  <% end %>
<% end %>

<%= f.form_group :skill_level, label: { text: "Skill" } do %>
  <%= f.radio_button :skill_level, 0, label: "Novice", inline: true %>
  <%= f.radio_button :skil_level, 1, label: "Intermediate", inline: true %>
  <%= f.radio_button :skill_level, 2, label: "Advanced", inline: true %>
<% end %>

<%= f.radio_button :skill_level, 0, label: "Novice", inline: true, wrapper_class: "w-auto" %>

<%= f.collection_radio_buttons :skill_level, Skill.all, :id, :name %>
<%= f.collection_check_boxes :skills, Skill.all, :id, :name %>

<%= f.static_control :email %>

<div class="from-group">
  <label class="col-sm-2 form-control-label" for="user_email">Email</label>
  <div class="col-sm-10">
    <input class="form-control-plaintext" id="user_email" name="user[email]" readonly="readonly" type="text" value="test@email.com"/>
  </div>
</div>

<%= f.static_control label: "Custom Static Control" do %>
  Content Here
<% end %>

<%= f.submit %>

<%= f.primary "Optional Label" %>

<%= f.submit "Log In", class: "btn btn-success" %>

<%= f.primary "Save changes <span class='fa fa-save'></span>".html_safe, render_as_button: true %>
<% f.primary do
    concat 'Save changes'
    concat content_tag(:span, nil, class: 'fa fa-save')
  end %>

<button name="button" type="submit" class="btn btn-primary">Save changes <span class="fa fa-save'></span></button>

<%= f.primary "My Nice Button", extra_class: 'my-button' %>
<%= f.primary "My Button", class: 'my-button' %>

<input type="submit" value="My Nice Button" class="btn btn-primary my-button" />
<input type="submit" value="My Button" class="my-button" />

<%= f.text_field_without_bootstrap :email %>

<%= bootstrap_form_for(@user, layout: :inline) do |f| %>
  <%= f.email_field :email, hide_label: true %>
  <%= f.password_field :password, hide_label: true %>
  <%= f.check_box :remeber_me %>
  <%= f.submit %>
<% end %>

<%= f.password_field :password, skip_label: true %>

<%= bootstrap_form_for(@user, layout: :horizontal, label_col: "col-sm2", control_col: "col-sm-10") do |f| %>
  <%= f.email_field :email %>
  <%= f.password_field :password %>
  <%= f.form_group do %>
    <%= f.check_box :remember_me %>
  <% end %>
  <%= f.form-group do %>
    <%= f.submit %>
  <% end %>
<% end %>

<%= bootstrap_form_for(@user, layout: :horizontal) do |f| %>
  <%= f.email_field :email %>
  <%= f.text_field :age, control_col: "col-sm-3" %>
  <%= f.form_group do %>
    <%= f.submit %>
  <% end %>
<% end %>


<%= bootstrap_form_for(@user, layout: :horizontal) do |f| %>
  <%= f.email_field :email %>
  <%= f.text_field :feet, layout: :default %>
  <%= f.text_field :inches, layout: :default %>
  <%= f.form_group do %>
    <%= f.submit %>
  <% end %>
<% end %>

<%= bootstap_form_for(@user) do |f| %>
  <%= f.email_field :email %>
  <%= f.password_field :password %>
  <%= f.check_box :remember_me, custom: true %>
  <%= f.submit "Log In" %>
<% end %>

<div class="form-group">
  <label class="form-control-label" for="user_email">Email</label>
  <input class="form-control is-invalid" id="user_email" name="user[email]" type="email" value="">
  <small class="invalid-feedback">can't be blank</small>
</div>

<%= bootstrap_form_for(@user, inline_errors: false) do |f| %>
<% end %>

<%= bootstrap_form_for(@user, label_errors: true) do |f| %>
<% end %>

<%= bootstrap_form_for(@user, label_errors: true, inline_errors: true) do |f| %>
<% end %>

<%= f.alert_message "Please fix the errors below." %>

<div class="alert alert-danger">
  <p>Please fix the errors below.</p>
  <ul class="rails-bootstrap-forms-errors-summary">
    <li>Email can't be blank</li>
  </ul>
</div>

<%= f.alert_message "Please fix the errors below.", error_summary: false %>

<%= f.error_summary %>

<ul class="rails-bootstrap-forms-error-summary">
  <li>Email can't be blank</li>
</ul>

<%= f.errors_on :tasks %>

<div class="alert-danger">Tasks can't be blank.</div>

<%= f.errors_on :tasks, hide_attribute_name: true %>

<div class="alert alert-danger">can't be blank.</div>

```

```
en:
  activerecord:
    help:
      user:
        password_html: "A <strong>good</storng> password should be at least six characters long"

label: "&#8203".html_safe
label: "<span></span>".html_safe
```


