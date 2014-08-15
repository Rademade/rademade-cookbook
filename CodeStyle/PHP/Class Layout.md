# Class Layout

```PHP
<?php
require_once '$PathToFile$';

use $OtherClassName$ as $ShortOtherClassName$;

/**
 * ...
 */
abstract class|trait|interface $ClassName$
    // Parent class
    extends
        $Ancestor$
    // Implemented interfaces
    implements
        $Interface$,
        $Interface$ {

    // Used traits
    use $Trait$;

    // Constants
    const $CONST_NAME$ = $VALUE$;

    // Public static attributes
    public static $attribute$;

    // Protected static attributes
    protected static $attribute$;

    // Private static attributes
    private static $attribute$;

    // Public attributes
    public $attribute$;

    // Protected attributes
    protected $attribute$;

    // Private attributes
    private $attribute$;

    // Constructor
    $access$ function __construct($Args...$) {
    }

    // Abstract methods with any access in order: public, protected // RM_TODO before constructor or after ???
    abstract $access$ function $method$();

    // Static methods
    $access$ static function $method$() {
    }

    // Overridden, implemented static methods
    $access$ static function $method$() {
    }

    // Instance methods
    $access$ function $method$() {
    }

    // Overridden, implemented or magic instance methods
    $access$ function $method$() {
    }

}

```