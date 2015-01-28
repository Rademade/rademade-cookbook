# Code optimization

1. [Tail optimization](http://nithinbekal.com/posts/ruby-tco/)
```ruby
RubyVM::InstructionSequence.compile_option = {
  tailcall_optimization: true,
  trace_instruction: false
}
```

2. [Debug software](http://rbkit.codemancers.com/v0.1.10/docs/using-rbkit-desktop-app)
