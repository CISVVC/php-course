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

// test.php
// The following is a php file test.php
// ----------
<?php

echo "A $color $fruit"; // A

include 'vars.php';  // this includes the vars.php file, it is in the same directory/folder

echo "A $color $fruit"; // A green apple

?>
```
