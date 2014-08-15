# Naming & Comments

- Use camelCase for methods and variables

- Use CamelCase for classes, traits, interfaces, directories and files: HtmlRenderer, SqlFormatter

- Start private or protected class attribute's name with underscore

- Start private class method's name with underscore

- Start protected class method's name with two underscores

- Start attribute reader methods with get and attribute writer with set

- Prefer single-quoted strings when you don't need string interpolation or special symbols such as `\t`, `\n`, `'`, etc.

- Do not duplicate name of namespace in class methods or variables
```PHP
<?php
class Item {

    // bad

    public function getItemName() {}

    // good

    public function getName() {}

}
```
- Use PHP_EOL instead of `\n` //RM_TODO location

- Use PHPDoc

- Use single-line variable annotation when you want to document only type
```PHP
$doc = new Document();
/* @var Document $doc */
```

- Use multi-line variable annotation when you want to document number of things (@link, @comment)
```PHP
/**
 * @var Document $doc
 * @link http://api.reference.com/Document
 */
$doc = new Document();
```

- Always use multi-line annotation for classes and methods
```PHP
<?php

/**
 * @class Item
 * @link http://api.reference.com/Item
 */
class Item {

	/**
	 * @return string
	 */
    public function getName() {
        return 'Jacob';
    }

}
```

- When using annotation place it near annotation object

- Prefer to place annotation above of annotation object