# Code optimization

1. [Tail optimization](http://nithinbekal.com/posts/ruby-tco/)
```ruby
RubyVM::InstructionSequence.compile_option = {
  tailcall_optimization: true,
  trace_instruction: false
}
```
