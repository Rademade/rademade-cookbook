# Capybara selectors priority
- #####Using build-in Capybara DSL 
    - Text field (fill_in): id, name, related label element
    - Click link/button (click_link/click_button): id, title, text within tag, value
    - Checkbox/radio button/dropdown (check/uncheck/choose/select): id, name, related label element
    - Upload file (attach_file): id, name

- For scenarios where basic the DSL cannot help, we use xpath and CSS selectors
