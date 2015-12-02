# Capybara selectors priority
- #####Using build-in Capybara DSL
    - Text field (fill_in): related label element content, name
    - Click link/button (click_link/click_button:
    - Checkbox/radio button/dropdown (check/uncheck/choose/select): related label element text, name
    - Upload file (attach_file): name
    - All (find), id, class, custom attribute

- For scenarios where basic the DSL cannot help, we use xpath and CSS selectors

```slim
<!-- example template snippet  -->

input.input-class(type="text" id="email" name="email")
input.password-class(type="password" name="password" id="password")
div.btn-container
  button.btn.submit-button Submit
```

```Ruby

# bad[find]

  find('#email').set(@email)
  find('#password').set(@passwod)
  find('.submit-button', :match => :first).click

# good[fill_in, click_button]

  fill_in 'email', :with => @email
  fill_in 'password', :with => @passwod
  click_button 'Submit'

```
