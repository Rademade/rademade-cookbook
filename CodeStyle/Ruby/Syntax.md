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
* <a name="double-colon"></a>Use `::` only to reference constants(this includes classes and modules) and constructors. Never use `::` for regular method invocation. <sup>[[link](#double-colon)]</sup>
* <a name="method-parentheses"></a>Use def with parentheses when there are arguments. Omit the parentheses when the method doesn't accept any arguments. <sup>[[link](#method-parentheses)]</sup>
* <a name="iterator"></a>Prefer iterators to `for`. <sup>[[link](#iterator)]</sup>
* <a name="ternary-operator"></a>For short conditions use ternary operator. <sup>[[link](#ternary-operator)]</sup>
* <a name="unless"></a>Use `unless` instead of `if not`. <sup>[[link](#unless)]</sup>
* <a name="untill"></a>Use `until` instead of `while not`. <sup>[[link](#untill)]</sup>
* <a name="unless-else"></a>Do not use `unless` with `else`. <sup>[[link](#unless-else)]</sup>
* <a name="embedded-ternary-operator"></a>Do not include ternary operator in other ternary operator. <sup>[[link](#embedded-ternary-operator)]</sup>
* <a name="not-assignment"></a>Avoid of using `not` in assignment. Use `!` instead. <sup>[[link](#not-assignment)]</sup>
* <a name="conditional-statements"></a>In conditional statements use `and`, `or`, `not`. <sup>[[link](#conditional-statements)]</sup>
* <a name="reversed-modifiers"></a>Use reversed `if`/`unless`/`while`/`until` modifiers for single-line body. <sup>[[link](#reversed-modifiers)]</sup>
* <a name="condition-parentheses"></a>Don't use parentheses around the condition of an `if`/`unless`/`while`/`until`. <sup>[[link](#condition-parentheses)]</sup>
* <a name="while-do"></a>Keep `do` clause when using `while`/`until` for multi-line body. <sup>[[link](#while-do)]</sup>
* <a name="infinite-loop"></a>Use `loop` instead of `while`/`until` when you need an infinite loop. <sup>[[link](#infinite-loop)]</sup>
* <a name="native-parentheses"></a>Omit parentheses when using Ruby native functions like `p`, `puts`, `attr_reader` etc. <sup>[[link](#native-parentheses)]</sup>
* <a name="implicit-hash"></a>Omit the outer braces around an implicit options hash. <sup>[[link](#implicit-hash)]</sup>
* <a name="parentheses-without-arguments"></a>Omit parentheses for method calls with no arguments. <sup>[[link](#parentheses-without-arguments)]</sup>
* <a name="single-line-blocks"></a>Prefer `{...}` over `do...end` for single-line blocks. <sup>[[link](#single-line-blocks)]</sup>
* <a name="redundant-return"></a>Avoid return where not required for flow of control. <sup>[[link](#redundant-return)]</sup>
* <a name="redundant-self"></a>Avoid `self` where not required. Omit this rule only when calling custom attribute writer inside class. <sup>[[link](#redundant-self)]</sup>
* <a name="shadowing-variables"></a>Avoid shadowing variables with local variables unless they are both equivalent. <sup>[[link](#shadowing-variables)]</sup>
* <a name="conditional-assignment"></a>Add parentheses in conditional statement when you are using assignment operator inside. <sup>[[link](#conditional-assignment)]</sup>
* <a name="attr-accessors"></a>Use shorthand self assignment operators whenever applicable. <sup>[[link](#attr-accessors)]</sup>
* <a name="memoization"></a>Use `||=` to initialize variables only if they're not already initialized, except boolean variables. <sup>[[link](#memoization)]</sup>
* <a name="preprocess-variables"></a>Use `&&=` to preprocess variables that may or may not exist. <sup>[[link](#preprocess-variables)]</sup>
* <a name="equality-operator"></a>Try not to use equality operator. Instead you may use `is_a?`, `zero?`, `nil?`, `=~` etc. <sup>[[link](#equality-operator)]</sup>
* <a name="method-space-parenthesis"></a>Never put a space between a method name and the opening parenthesis. <sup>[[link](#method-space-parenthesis)]</sup>
* <a name="lambda-syntax"></a>Use the new lambda literal syntax for single line body blocks. Use the lambda method for multi-line blocks. <sup>[[link](#lambda-syntax)]</sup>
* <a name="unused-variables"></a>Prefix with _ unused block parameters and local variables. <sup>[[link](#unused-variables)]</sup>
* <a name="streams"></a>Use `$stdout`/`$stderr`/`$stdin` instead of `STDOUT`/`STDERR`/`STDIN`. <sup>[[link](#streams)]</sup>
* <a name="single-line-methods"></a>Avoid single-line methods. <sup>[[link](#single-line-methods)]</sup>
* <a name="operator-space"></a>Use spaces around operators, except exponent operator. <sup>[[link](#operator-space)]</sup>
* <a name="hash-space"></a>Open and close hash body with spaces. <sup>[[link](#hash-space)]</sup>
* <a name="inline-expression-space"></a>Do not add spaces to inline expression, eg `My name is #{name}`. <sup>[[link](#inline-expression-space)]</sup>
* <a name="bracket-space"></a>No spaces after `(`, `[`, `!` or before `]`, `)`. <sup>[[link](#bracket-space)]</sup>
* <a name="switch"></a>Add indent to `when` clause when using `case` statement. <sup>[[link](#switch)]</sup>
* <a name="assignment"></a>Keep assignment easy and readable. <sup>[[link](#assignment)]</sup>
* <a name="method-definitions"></a>Put end of line around method definitions and class definition blocks. <sup>[[link](#method-definitions)]</sup>
* <a name="continuation"></a>Avoid line continuation `\` where not required. <sup>[[link](#continuation)]</sup>
* <a name="chain-method"></a>When continuing a chained method invocation on another line keep the . on the second line. <sup>[[link](#chain-method)]</sup>
* <a name="long-arguments"></a>Align big chunk of method arguments, big hash or array in multiline. Put end of line around body. <sup>[[link](#long-arguments)]</sup>
* <a name="large-numeric-literals"></a>It is preferred to add underscores to large numeric literals to improve their readability. <sup>[[link](#large-numeric-literals)]</sup>
* <a name="block-comments"></a>Don't use block comments. <sup>[[link](#block-comments)]</sup>