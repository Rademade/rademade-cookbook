#General rules for selecting elements on the page
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

  -  Use data
  -  Find elements using css selectors(by class, position, type etc.)
  -  Add data-ci-selector="profile-bu" (only in exceptional cases)
