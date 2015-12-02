#Priority rules for search items on the page
  -  Find elements by visible content or name

  ```slim
  <!-- example template snippet  -->

  input.input-class(type="text" id="email" name="email")
  input.password-class(type="password" name="password" id="password")
  div.btn-container
    button.btn.submit-button Submit
  ```

  ```Ruby

  # bad[class, id]

    find('#email').set(@email)
    find('#password').set(@passwod)
    find('.submit-button', :match => :first).click

  # good[visible content, name]

    fill_in 'email', :with => @email
    fill_in 'password', :with => @passwod
    click_button 'Submit'

  ```

  -  Find elements using css selectors(by class, position, type etc.)
  ```slim
  <!-- example template snippet  -->

  div.profile-box(type="text" id="email" name="email")
    p.box-title Facebook
    div.btn-container
      button.btn.submit-button Activate

  div.profile-box(type="text" id="email" name="email")
    p.box-title Twitter
    div.btn-container
      button.btn.submit-button Activate
  ```
  ```Ruby
  # bad[add custom selector]
  ```
  ```slim
  <!-- change template  -->

    div.profile-box(type="text" id="email" name="email")
      p.box-title Facebook
      div.btn-container
        button.btn.submit-button(test-selector="facebook-btn") Activate
  ```
  ```Ruby
    find["button[test-selector='facebook-btn']").click
  ```
  ```Ruby
  # good[class with visible content]

     find('.profile-box', :text => 'Facebook').click_button('Activate')

  ```
  - Add custom selector '[test-selector]' (only in exceptional cases)
  - Never use [id, class] as a custom selector
