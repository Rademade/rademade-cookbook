# Syntax

* <a name="indentation"></a>Use two spaces per indentation level (aka soft tabs). No hard tabs. <sup>[[link](#indentation)]</sup>
```Ruby
# bad
class Dog

    def say
        print 'Bow-wow-wow'
    end
    
end

# good
class Dog

  def say
    print 'Bow-wow-wow'
  end

end
```
* <a name="semicolon"></a>Don't use semicolon for single-line body. <sup>[[link](#semicolon)]</sup>
```Ruby
# bad
puts 'Hello';

# good
puts 'Hello'
```
* <a name="double-colon"></a>Use `::` only to reference constants(this includes classes and modules) and constructors. Never use `::` for regular method invocation. <sup>[[link](#double-colon)]</sup>
```Ruby
# bad
SomeClass::some_method
some_object::some_method

# good
SomeClass.some_method
some_object.some_method
SomeModule::SomeClass::SOME_CONST
SomeModule::SomeClass()
```
* <a name="method-parentheses"></a>Use def with parentheses when there are arguments. Omit the parentheses when the method doesn't accept any arguments. <sup>[[link](#method-parentheses)]</sup>
```Ruby
# bad
def some_method()
 
end

# good
def some_method
 
end

# bad
def some_method_with_arguments arg1, arg2
 
end

# good
def some_method_with_arguments(arg1, arg2)
 
end
```
* <a name="unless"></a>Use `unless` instead of `if not`. <sup>[[link](#unless)]</sup>
```Ruby
# bad
if not items.empty?
  puts 'There is something there'
end

# good
unless items.empty?
  puts 'There is something there'
end
```
* <a name="untill"></a>Use `until` instead of `while not`. <sup>[[link](#untill)]</sup>
```Ruby
# bad
while not items.empty? do
  show_info(items.pop)
end

# good
until items.empty? do
  show_info(items.pop)
end
```
* <a name="unless-else"></a>Do not use `unless` with `else`. <sup>[[link](#unless-else)]</sup>
```Ruby
# bad
unless items.empty?
  puts 'There is something there'
else
  puts 'It is empty'
end

# good
if items.empty?
  puts 'It is empty'
else
  puts 'There is something there'
end
```
* <a name="not-assignment"></a>Avoid of using `not` in assignment. Use `!` instead. <sup>[[link](#not-assignment)]</sup>
```Ruby
# bad
good = not bad

# good
good = !bad
```
* <a name="conditional-statements"></a>In conditional statements use &&, ||, !. <sup>[[link](#conditional-statements)]</sup>
```Ruby
# bad
if good and not(red or green)
  puts 'Some magic'
end

# good
if good && !(red || green)
  puts 'Some magic'
end
```
* <a name="reversed-modifiers"></a>Use reversed `if`/`unless`/`while`/`until` modifiers for single-line body. <sup>[[link](#reversed-modifiers)]</sup>
```Ruby
# bad
if good
  puts 'It is good'
end

# good
puts 'It is good' if good
```
* <a name="condition-parentheses"></a>Don't use parentheses around the condition of an `if`/`unless`/`while`/`until`. <sup>[[link](#condition-parentheses)]</sup>
```Ruby
# bad
if (items.empty?) 
  puts 'It is empty'
end

# good
if items.empty?
  puts 'It is empty'
end
```
* <a name="while-do"></a>Keep `do` clause when using `while`/`until` for multi-line body. <sup>[[link](#while-do)]</sup>
```Ruby
# bad
until items.empty?
  puts 'Processing'
  items.pop
end

# good
until items.empty? do
  puts 'Processing'
  items.pop
end
```
* <a name="infinite-loop"></a>Use `loop` instead of `while`/`until` when you need an infinite loop. <sup>[[link](#infinite-loop)]</sup>
```Ruby
# bad
while true do
  puts '.'
end

# good
loop do
  puts '.'
end
```
* <a name="native-parentheses"></a>Omit parentheses when using Ruby native functions like `p`, `puts`, `attr_reader` etc. <sup>[[link](#native-parentheses)]</sup>
```Ruby
# bad
puts('Hello world')

# good
puts 'Hello world'
```
* <a name="implicit-hash"></a>Omit the outer braces around an implicit options hash. <sup>[[link](#implicit-hash)]</sup>
```Ruby
# bad
user.set({ name: 'John', age: 45, permissions: { read: true } })

# good
user.set(name: 'John', age: 45, permissions: { read: true })
```
* <a name="parentheses-without-arguments"></a>Omit parentheses for method calls with no arguments. <sup>[[link](#parentheses-without-arguments)]</sup>
```Ruby
# bad
2.even?()

# good
2.even?
```
* <a name="single-line-blocks"></a>Prefer `{...}` over `do...end` for single-line blocks. <sup>[[link](#single-line-blocks)]</sup>
```Ruby
# ok
items.map do |item|
  item.name
end

# good
items.map { |item| item.name }
```
* <a name="redundant-return"></a>Avoid return where not required for flow of control. <sup>[[link](#redundant-return)]</sup>
```Ruby
# bad
def say
  return 'Bow-wow-wow'
end

# good
def say
  'Bow-wow-wow'
end

# still good
def say
  return 'Гав-гав' if russian?
  'Bow-wow-wow'
end
```
* <a name="redundant-self"></a>Avoid `self` where not required. Omit this rule only when calling custom attribute writer inside class. <sup>[[link](#redundant-self)]</sup>
```Ruby
# bad
def full_name
  "#{self.first_name} #{self.last_name}"
end

# good
def full_name
  "#{first_name} #{last_name}"
end
```
* <a name="conditional-assignment"></a>Add parentheses in conditional statement when you are using assignment operator inside. <sup>[[link](#conditional-assignment)]</sup>
```Ruby
# bad
if show? and item = last_item
  show(item)
end

# good
if show? and (item = last_item)
  show(item)
end
```
* <a name="attr-accessors"></a>Use shorthand self assignment operators whenever applicable. <sup>[[link](#attr-accessors)]</sup>
```Ruby
# ok
x = x + y

# good
x += y
```
* <a name="memoization"></a>Use `||=` to initialize variables only if they're not already initialized, except boolean variables. <sup>[[link](#memoization)]</sup>
```Ruby
# bad
name = name ? name : 'Batman'

name = 'Batman' unless name

enabled ||= true

# good
name ||= 'Batman'

endabled = true if enabled.nil?
```
* <a name="preprocess-variables"></a>Use `&&=` to preprocess variables that may or may not exist. <sup>[[link](#preprocess-variables)]</sup>
```Ruby
# bad
something = something ? something.downcase : nil

# good
something &&= something.downcase
```
* <a name="equality-operator"></a>Try not to use equality operator. Instead you may use `is_a?`, `zero?`, `nil?`, `=~` etc. <sup>[[link](#equality-operator)]</sup>
```Ruby
# ok
if x == 0 and y == nil
  y = 5
end

# good
if x.zero? and y.nil?
  y = 5
end
```
* <a name="lambda-syntax"></a>Use the new lambda literal syntax for single line body blocks. Use the lambda method for multi-line blocks. <sup>[[link](#lambda-syntax)]</sup>
```Ruby
# bad
l = lambda { |a, b| a + b }
l.call(1, 2)

l = ->(a, b) do
  tmp = a * 7
  tmp * b / 50
end

# good
l = ->(a, b) { a + b }
l.call(1, 2)

l = lambda do |a, b|
  tmp = a * 7
  tmp * b / 50
end
```
* <a name="unused-variables"></a>Prefix with _ unused block parameters and local variables. <sup>[[link](#unused-variables)]</sup>
```Ruby
# bad
items.map { |name, data| data.price }

# good
items.map { |_, data| data.price }
```
* <a name="streams"></a>Use `$stdout`/`$stderr`/`$stdin` instead of `STDOUT`/`STDERR`/`STDIN`. <sup>[[link](#streams)]</sup>
* <a name="single-line-methods"></a>Avoid single-line methods. <sup>[[link](#single-line-methods)]</sup>
```Ruby
# ok
def say; end

# good
def say
end
```
* <a name="operator-space"></a>Do not use spaces around exponent operator. <sup>[[link](#operator-space)]</sup>
```Ruby
# bad
e = M * c ** 2

# good
e = M * c**2
```
* <a name="inline-expression-space"></a>Do not add spaces to inline expression. <sup>[[link](#inline-expression-space)]</sup>
```Ruby
# bad
"My name is #{ name }"

# good
"My name is #{name}"
```
* <a name="bracket-space"></a>No spaces after `[` or before `]`. <sup>[[link](#bracket-space)]</sup>
```Ruby
# bad
fields[ :name ]

# good
fields[:name]
```
* <a name="switch"></a>Add indent to `when` clause when using `case` statement. <sup>[[link](#switch)]</sup>
```Ruby
# bad
case value
when 1
  puts 'It is one'
when 42
  puts 'It is forty two'
else
  puts 'Unknown value'
end

# good
case value
  when 1
    puts 'It is one'
  when 42
    puts 'It is forty two'
  else
    puts 'Unknown value'
end
```
* <a name="continuation"></a>Avoid line continuation `\` where not required. <sup>[[link](#continuation)]</sup>
* <a name="chain-method"></a>When continuing a chained method invocation on another line keep the `.` on the second line. <sup>[[link](#chain-method)]</sup>
```Ruby
# bad
items.last.
  finished.
  count

# good
items.last
  .finished
  .count
```
* <a name="large-numeric-literals"></a>It is preferred to add underscores to large numeric literals to improve their readability. <sup>[[link](#large-numeric-literals)]</sup>
```Ruby
# ok 
number = 20000000

# good
number = 20_000_000
```
