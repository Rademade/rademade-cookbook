# Class Layout
```Ruby
class $ClassName$ < $Ancestor$

    # Extend clause
    extend $ModuleName$
    extend $ModuleName$

    # Include clause
    include $ModuleName$
    include $ModuleName$

    # Constants
    # use freeze as much as you can
    $ConstantName$ = $Value$.freeze

    # Macros
    $Macros$
    $Macros$

    # Instance attribute accessors
    # for attribute name use symbol
    # order them by these rules
    # 1. attr_accessor
    # 2. attr_writer
    # 3. attr_reader
    attr_accessor :$AttrName$
    attr_writer :$AttrName$
    attr_reader :$AttrName$

    # Constructor
    def initialize($Args...$)
    end

    # Methods
    # Put methods in order:
    # 1. abstract class methods
    # 2. abstract instance methods
    # 3. class methods
    # 4. class predicates
    # 5. class overridden, implemented or magic methods
    # 6. instance methods
    # 7. instance predicates
    # 8. instance overridden, implemented or magic methods

    # Methods

    protected

    # Methods

    private

    # Methods

end
```

# Examples
```
# todo examples
```