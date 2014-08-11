# Exceptions
- Use `raise` keyword
- Don't specify `RuntimeError` explicitly in the two argument version of `raise`
- Prefer supplying an exception class and a message as two separate arguments to `raise`, instead of an exception instance
- Try to separate exception handler into method that takes yield and runs in inside
