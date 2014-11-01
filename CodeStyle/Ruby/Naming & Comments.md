# Naming & Comments
* <a name="method-naming"></a>Use snake_case for symbols, methods and variables, files, directories. <sup>[[link](#method-naming)]</sup>
```Ruby
# bad
secondsPath = Calculate_Seconds_Path

# good
seconds_path = calculate_seconds_path
```
* <a name="class-naming"></a>Use CamelCase for classes and modules. <sup>[[link](#class-naming)]</sup>
```Ruby
# bad
class item_service
end

module timeHelper
end

# good
class ItemService
end

module TimeHelper
end
```
* <a name="predicate-methods-naming"></a>The names of predicate methods (methods that return a boolean value) should end in a question mark. <sup>[[link](#predicate-methods-naming)]</sup>
```Ruby
# bad
def is_big
  item.size > 10
end

# good
def big?
  item.size > 10
end
```
* <a name="dangerous-methods-naming"></a>The names of potentially dangerous methods (i.e. methods that modify self or the arguments, exit! (doesn't run the finalizers like exit does), etc.) should end with an exclamation mark if there exists a safe version of that dangerous method. <sup>[[link](#dangerous-methods-naming)]</sup>
```Ruby
# bad
class Person

  def update!
  end
  
end

# good
class Person

  def update!
  end

  def update
  end
  
end
```
* <a name="safe-methods-naming"></a>Define the non-bang (safe) method in terms of the bang (dangerous) one if possible. <sup>[[link](#safe-methods-naming)]</sup>
```Ruby
class Array

  def flatten_once!
    res = []
    each do |e|
      [*e].each { |f| res << f }
    end
    replace(res)
  end

  def flatten_once
    dup.flatten_once!
  end
  
end
```
* <a name="string-arrays"></a>Prefer declaring arrays of string(words)/symbols with `%w`/`%i`. <sup>[[link](#string-arrays)]</sup>
```Ruby
# ok
summer_months = ['june', 'july', 'august']

# good
summer_months = %w(june july august)
```
* <a name="hash-keys"></a>Use symbols instead of strings as hash keys. <sup>[[link](#hash-keys)]</sup>
```Ruby
# bad
attributes = { 'type' => 'text', 'class' => 'input-holder' }

# good
attributes = { :type => 'text', :class => 'input-holder' }
```
* <a name="hash-rockets"></a>Prefer symbols instead of strings as hash keys. <sup>[[link](#hash-rockets)]</sup>
```Ruby
# bad
hash = { 'one' => 1, 'two' => 2, 'three' => 3 }

# good
hash = { one: 1, two: 2, three: 3 }
```
* <a name="string-concat"></a>Prefer string interpolation and string formatting instead of string concatenation. <sup>[[link](#string-concat)]</sup>
```Ruby
# ok
full_name = first_name + ' ' + last_name

# good
full_name = "#{first_name} #{last_name}"
full_name = format('%s %s', first_name, last_name)
```
* <a name="single-quote-string"></a>Prefer single-quoted strings when you don't need string interpolation or special symbols such as `\t`, `\n`, `'`, etc. <sup>[[link](#single-quote-string)]</sup>
```Ruby
# ok
name = "Batman"

# good
name = 'Batman'
```
* <a name="string-escaping"></a>Prefer using `%()`, `%Q()` and `%q()` for escaping. <sup>[[link](#string-escaping)]</sup>
```Ruby
%(<tr><td class="name">#{name}</td>)
```
* <a name="string-symbolize"></a>Avoid the use of `%s`. <sup>[[link](#string-symbolize)]</sup>
```Ruby
# ok
%s(Bruce Wayne)

# good
:'Bruce Wayne'
```
* <a name="block-comments"></a>Don't use block comments. <sup>[[link](#block-comments)]</sup>
```Ruby
# bad
=begin
Some long comment
that describes the 
number 42
=end

# good

# Some long comment
# that describes the 
# number 42
```
