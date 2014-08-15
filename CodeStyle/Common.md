Common
======

- Use UTF-8 as the source file encoding
- Use system dependent line break
- Name identifiers in English
- Aim to have just a single class/module per source file. Associate filename with its contents
- Use SCREAMING_SNAKE_CASE for constants
```PHP
# bad
const value_of_one = 1;
const ValueOfTwo = 2;

# good
const VALUE_OF_THREE = 3;
```
- Do not use magic variables. Exceptions: `0`, `1`, `''`
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
- Prefer to write comments in English
- Use one space between the leading `#`, `//` or language specific single-line comment character of the comment and the text of the comment
- You can comment in same line where code is only if comment is very short, otherwise write immediately above the line. See example below
```Ruby
# bad
throw new Exception('I will crash your app!'); // this line of code throws exception with message 'I will crash your app!'

# good
throw new Exception('I will crash your app!'); // exception thrown here

// this line of code throws exception with message 'I will crash your app!'
throw new Exception('I will crash your app!');
```
- You can have multiline comments. Start first comment with capitalized letter. See example below
```PHP
# This thing is doing one, two, three
# four and five
# The first thing is implemented like so:
# join seven, nine and return it
thing.do();
```
- Use RM_TODO or rm_todo to note missing features or functionality that should be added at a later date
```PHP
# RM_TODO: clear image
```
- Use RM_FIXME to note broken code that needs to be fixed
```PHP
# RM_FIXME: add check for zero division
```
- Use RM_OPTIMIZE to note slow or inefficient code that may cause performance problems
- Use RM_HACK to note code smells where questionable coding practices were used and should be refactored away
- Use RM_REVIEW to note anything that should be looked at to confirm it is working as intended. See example below
```Ruby
# RM_REVIEW: Are we sure this is how the client does X currently?
```
- Put more specific exceptions higher up the rescue chain, otherwise they'll never be rescued from
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
- Avoid needless metaprogramming
- Avoid more than three levels of block nesting
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
- Do not use global variables, put them in namespace
- Maximum blank lines - 1
