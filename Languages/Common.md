# Common
- Use UTF-8 as the source file encoding
- Use system dependent line break
- Name identifiers in English
- Aim to have just a single class/module per source file. Associate filename with its contents
- Use SCREAMING_SNAKE_CASE for constants

- Prefer to write comments in English
- Use one space between the leading `#`, `//` or language specific single-line comment character of the comment and the text of the comment
- You can comment in same line where code is only if comment is very short, otherwise write immediately above the line. See example below
```Ruby
throw new Exception('I will crash your app!'); // exception thrown here
```
- You can have multiline comments. Start first comment with capitalized letter. See example below
```Ruby
# This thing is doing one, two, three
# four and five
# The first thing is implemented like so:
# join seven, nine and return it
thing.do();
```
- Use RM_TODO or rm_todo to note missing features or functionality that should be added at a later date # todo upper or lower case??
- Use RM_FIXME to note broken code that needs to be fixed
- Use RM_OPTIMIZE to note slow or inefficient code that may cause performance problems
- Use RM_HACK to note code smells where questionable coding practices were used and should be refactored away
- Use RM_REVIEW to note anything that should be looked at to confirm it is working as intended. See example below
```Ruby
# RM_REVIEW: Are we sure this is how the client does X currently?
```
- Put more specific exceptions higher up the rescue chain, otherwise they'll never be rescued from
- Avoid needless metaprogramming
- Avoid more than three levels of block nesting
- Do not use global variables, put them in namespace
- Maximum blank lines - 1