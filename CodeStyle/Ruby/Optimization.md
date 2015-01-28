# Code optimization

- [Tail optimization](http://nithinbekal.com/posts/ruby-tco/)
```ruby
RubyVM::InstructionSequence.compile_option = {
  tailcall_optimization: true,
  trace_instruction: false
}
```

- [Debug software](http://rbkit.codemancers.com/v0.1.10/docs/using-rbkit-desktop-app)
