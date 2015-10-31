#General priority rules for selecting elements on the page
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

    page.find('#email').set(@email)
    page.find('#password').set(@passwod)
    page.find('.submit-button', :match => :first).click

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
  ```slim
  # bad[add custom selector]

  <!-- change template  -->

    div.profile-box(type="text" id="email" name="email")
      p.box-title Facebook
      div.btn-container
        button.btn.submit-button(test-attr="facebook-btn") Activate
  ```
  ```Ruby
    find["button[test-attr='facebook-btn']").click

  # good[class with visible content]

     find('.profile-box', :text => 'Facebook').click_button('Activate')

  ```
  -  Add custom selector (only in exceptional cases)
