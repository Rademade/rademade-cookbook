# Naming & Comments
- Use snake_case for symbols, methods and variables, files, directories
- Use CamelCase for classes and modules: HtmlRenderer, SqlFormatter
- The names of predicate methods (methods that return a boolean value) should end in a question mark
- The names of potentially dangerous methods (i.e. methods that modify self or the arguments, exit! (doesn't run the finalizers like exit does), etc.) should end with an exclamation mark if there exists a safe version of that dangerous method
- Define the non-bang (safe) method in terms of the bang (dangerous) one if possible

- Prefer short syntax for arrays and hashes
- Prefer declaring arrays of string(words)/symbols with `%w/%i`
- Use symbols instead of strings as hash keys
- Use hash rockets instead semicolons
- Do not mix hash rockets and semicolons
- Prefer string interpolation and string formatting instead of string concatenation
- Prefer single-quoted strings when you don't need string interpolation or special symbols such as `\t`, `\n`, `'`, etc.

- Prefer using `%()`, `%Q()` and `%q()` for escaping
- Avoid the use of `%s`. It seems that the community has decided :`some string` is the preferred way to create a symbol with spaces in it