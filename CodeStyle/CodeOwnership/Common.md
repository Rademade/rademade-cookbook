### Rademade code ownership

We use **Weak code ownership**. [More information](http://martinfowler.com/bliki/CodeOwnership.html)

**Our approach:**

 1. Every new file mark with `@author` block
 2. Don't edit files of other developers without owner agreement
 2. You need discuss your changes before out start edit code
 3. File owner need to approve your changes with github comment on Pull Request

####Author block examples

**Ruby**
```ruby
# @author Name Surname <github-nickname>
# This class does something
class Service
```

**Coffee**
```coffeescript
###
# @author Name Surname <github-nickname>
# This class does something
###
a = () ->
```

**Javascript**
```javascript
/**
 * @author Name Surname <github-nickname>
 */
 function() {
 }
```

**Jade/Slim**
```jade
// @author Name Surname <github-nickname>
h1() Tag
```

**HTML**
```html
<!-- @author Name Surname <nickname> -->
<h1>Tag</h1>
```
