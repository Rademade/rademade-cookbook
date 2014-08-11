```
Class Layout

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
    # Put abstract methods at beginning
    # Put predicate methods before re-declared methods
    # Put re-declared methods at end

    # Public class methods

    # Public instance methods

    # Special magic methods

    protected

    # Protected class methods

    # Protected instance methods

    private

    # Private class methods

    # Private instance methods

end
```

Example

# todo examples