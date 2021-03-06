Common
======

* <a name="encoding"></a>Use UTF-8 as the source file encoding. <sup>[[link](#encoding)]</sup>
* <a name="line-break"></a>Use system dependent line break. <sup>[[link](#line-break)]</sup>
* <a name="identifiers-naming"></a>Name identifiers in English. <sup>[[link](#identifiers-naming)]</sup>
* <a name="modularity"></a>Aim to have just a single class/module per source file. Associate filename with its contents. <sup>[[link](#modularity)]</sup>
* <a name="constants-naming"></a>Use SCREAMING_SNAKE_CASE for constants. <sup>[[link](#constants-naming)]</sup>
```PHP
# bad
const value_of_one = 1;
const ValueOfTwo = 2;

# good
const VALUE_OF_THREE = 3;
```
* <a name="magic-variables"></a>Do not use magic variables. Exceptions: `0`, `1`, `''`. <sup>[[link](#magic-variables)]</sup>
```PHP
# bad
if ($secondsPath == 86400) {
    echo 'It is a new day!';
}

if ($month == 'april') {
    echo 'It is april!';
}

# good
if ($secondsPath == SECONDS_IN_DAY) {
    echo 'It is a new day!';
}

if ($month == MONTH_APRIL) {
    echo 'It is april!';
}

# still good
if ($secondsPath == 0) {
    echo 'Your clock is broken';
}

if ($month == '') {
    echo 'Your calendar is broken too';
}

if ($count == 1) {
    echo 'First!';
}

```
* <a name="commenting"></a>Prefer to write comments in English. <sup>[[link](#commenting)]</sup>
* <a name="comment-sign"></a>Use one space between the leading `#`, `//` or language specific single-line comment character of the comment and the text of the comment. <sup>[[link](#comment-sign)]</sup>
* <a name="comment-place"></a>You can comment in same line where code is only if comment is very short, otherwise write immediately above the line. See example below. <sup>[[link](#comment-place)]</sup>
```Ruby
# bad
throw new Exception('I will crash your app!'); // this line of code throws exception with message 'I will crash your app!'

# good
throw new Exception('I will crash your app!'); // exception thrown here

// this line of code throws exception with message 'I will crash your app!'
throw new Exception('I will crash your app!');
```
* <a name="multiline-comments"></a>You can have multiline comments. Start first comment with capitalized letter. See example below. <sup>[[link](#multiline-comments)]</sup>
```PHP
# This thing is doing one, two, three
# four and five
# The first thing is implemented like so:
# join seven, nine and return it
thing.do();
```
* <a name="annotation-todo"></a>Use RM_TODO or rm_todo to note missing features or functionality that should be added at a later date. <sup>[[link](#annotation-todo)]</sup>
```PHP
# RM_TODO: clear image
```
* <a name="annotation-fixme"></a>Use RM_FIXME to note broken code that needs to be fixed. <sup>[[link](#annotation-fixme)]</sup>
```PHP
# RM_FIXME: add check for zero division
```
* <a name="annotation-optimize"></a>Use RM_OPTIMIZE to note slow or inefficient code that may cause performance problems. <sup>[[link](#annotation-optimize)]</sup>
* <a name="annotation-hack"></a>Use RM_HACK to note code smells where questionable coding practices were used and should be refactored away. <sup>[[link](#annotation-hack)]</sup>
* <a name="annotation-review"></a>Use RM_REVIEW to note anything that should be looked at to confirm it is working as intended. See example below. <sup>[[link](#annotation-review)]</sup>
```Ruby
# RM_REVIEW: Are we sure this is how the client does X currently?
```
* <a name="exceptions-order"></a>Put more specific exceptions higher up the rescue chain, otherwise they'll never be rescued from. <sup>[[link](#exceptions-order)]</sup>
```PHP
# bad
try {
    $file->remove();
} catch (Exception $e) {
    $this->showMessage($e);
} catch (FileException $fe) {
    $file->fix();
}

# good
try {
    $file->remove();
} catch (FileException $fe) {
    $file->fix();
} catch (Exception $e) {
    $this->showMessage($e);
}
```
* <a name="metaprogramming"></a>Avoid needless metaprogramming. <sup>[[link](#metaprogramming)]</sup>
* <a name="nesting-level"></a>Avoid more than three levels of block nesting. <sup>[[link](#nesting-level)]</sup>
```PHP
# bad
if ($year == 2012) {
    if ($month == 12) {
        if ($day == 21) {
            if ($date->isToday()) {
                echo 'Doom!';
            }
        } else if ($date->isTommorow()) {
            echo 'Pray!';
        }
    }
}
```
* <a name="global-variables"></a>Do not use global variables, put them in namespace. <sup>[[link](#global-variables)]</sup>
* <a name="blank-lines"></a>Maximum blank lines - 1. <sup>[[link](#blank-lines)]</sup>
```PHP
# bad
if ($isGoodDay) {


    echo 'Good day';

}
```
* <a name="short-array"></a>Prefer short syntax for arrays and hashes. <sup>[[link](#short-array)]</sup>
* <a name="method-grouping"></a>Try to collect class methods in groups by purpose.<sup>[[link](#method-grouping)]</sup>
* <a name="ternary-operator"></a>For short conditions use ternary operator. <sup>[[link](#ternary-operator)]</sup>
```PHP
# bad
if ($isGood) {
    $color = 'green';
} else {
    $color = 'red';
}

# good
$color = $isGood ? 'green' : 'red';
```
* <a name="iterator"></a>Prefer iterators to `for`. <sup>[[link](#iterator)]</sup>
* <a name="embedded-ternary-operator"></a>Do not include ternary operator in other ternary operator. <sup>[[link](#embedded-ternary-operator)]</sup>
```PHP
# bad
$color = $previous == 'red' ? $isGood ? 'green' : 'yellow' : 'orange';
```
* <a name="shadowing-variables"></a>Avoid shadowing variables with local variables unless they are both equivalent. <sup>[[link](#shadowing-variables)]</sup>
```Ruby
# ok
def initialize(options)
  self.options = options
  # both options and self.options are equivalent here
end

# bad
def do_something(options = {})
  unless options[:when] == :later
    output(self.options[:message])
  end
end

# good
def do_something(params = {})
  unless params[:when] == :later
    output(options[:message])
  end
end
```
* <a name="method-space-parenthesis"></a>Never put a space between a method name and the opening parenthesis. <sup>[[link](#method-space-parenthesis)]</sup>
```PHP
# bad
public function getName () { ... }

# good
public function getName() { ... }
```
* <a name="operator-space"></a>Use spaces around operators. <sup>[[link](#operator-space)]</sup>
```PHP
# bad
$day = 60*60*24;

# good
$day = 60 * 60 * 24;
```
* <a name="hash-space"></a>Open and close single-line hash body with spaces. <sup>[[link](#hash-space)]</sup>
```PHP
# bad
[$key => $value]

# good
[ $key => $value ]
```
* <a name="bracket-space"></a>No spaces after `(`, `!` or before `)`. <sup>[[link](#bracket-space)]</sup>
```PHP
# bad
$entity = $this->find( $value );
if ( $entity ) {
    $found = ! $entity; 
}

# good
$entity = $this->find($value);
if ($entity) {
    $found = !$entity; 
}
```
* <a name="assignment"></a>Keep assignment easy and readable. <sup>[[link](#assignment)]</sup>
* <a name="method-definitions"></a>Put end of line around method definitions and class definition blocks. <sup>[[link](#method-definitions)]</sup>
```PHP
# bad
class Dog {
    public function say() {
        echo 'Bow-wow-wow';
    }
    public function getName() {
        return 'Bobik';
    }
}

# good
class Dog {

    public function say() {
        echo 'Bow-wow-wow';
    }
    
    public function getName() {
        return 'Bobik';
    }
    
}
```
* <a name="long-arguments"></a>Align big chunk of method arguments, big hash or array in multiline. Put end of line around body. <sup>[[link](#long-arguments)]</sup>
```PHP
# bad
$months = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december'];

# good
$months = [
    'january', 
    'february', 
    'march', 
    'april', 
    'may', 
    'june', 
    'july', 
    'august', 
    'september', 
    'october', 
    'november', 
    'december'
];

# still good
$months = [
    'january', 'february', 'march', 
    'april', 'may', 'june', 
    'july', 'august', 'september', 
    'october', 'november', 'december'
];
```