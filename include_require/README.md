# Control Structures -- include and require

## include
The include statement includes and evaluates the specified file.

### Example #1 Basic include example
```php
// The following is a php file vars.php
// ----------
<?php

$color = 'green';
$fruit = 'apple';

?>

// index.php
// The following is a php file index.php
// ----------
<?php

echo "A $color $fruit"; // these variables have not been defined.

include 'vars.php';  // this includes the vars.php file, it is in the same directory/folder

echo "A $color $fruit"; // A green apple

?>
```

### include in functions
If the include occurs inside a function within the calling file, 
then all of the code contained in the called file will behave as though it had been defined inside that function. So, it will follow the variable scope of that function. An exception to this rule are (https://www.php.net/manual/en/language.constants.predefined.php)[magic constants] which are evaluated by the parser before the include occurs.

### Example #2 Including within functions
```php
<?php

function foo()
{
    global $color;

    include 'vars.php';

    echo "A $color $fruit";
}

/* vars.php is in the scope of foo() so     *
* $fruit is NOT available outside of this  *
* scope.  $color is because we declared it *
* as global.                               */

foo();                    // A green apple
echo "A $color $fruit";   // A green

?>

```
