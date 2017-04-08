# Console Table

Library that makes it easy to build console style tables, inspired by PEAR package Console_Table of Jan Schneider.

## Usage

```php
require_once __DIR__.'/vendor/autoload.php';

use debussa\ConsoleTable\ConsoleTable;

// Set everything with constructor
$console_table = new ConsoleTable(
    ['#', 'Transportation', 'Speed (Km/h)'],
    [
        [1, 'Plane', 880],
        [2, 'Train', 300],
        [3, 'Car', 150],
        [4, 'Bike', 30]
    ]
);

// Or later
$console_table->setHeader(['#', 'Transportation', 'Speed (Km/h)']);
$console_table->setRows([
    [1, 'Plane', 880],
    [2, 'Train', 300],
    [3, 'Car', 150],
    [4, 'Bike', 30]
]);

// Add a new row
$console_table->addRow([5, 'Skateboard', 8]);

//== Display with HTML
$display_as_html = true;
echo '<pre>'.$console_table->fetch($display_as_html).'</pre>';

// OR
echo '<pre>';
$console_table->display($display_as_html);
echo '</pre>';

//== Display in cli
$display_as_html = false;
$console_table->display($display_as_html);
```

## Result

```
+----+----------------+--------------+
| #  | Transportation | Speed (Km/h) |
+----+----------------+--------------+
| 1  | Plane          | 880          |
| 2  | Train          | 300          |
| 3  | Car            | 150          |
| 4  | Bike           | 30           |
| 5  | Skateboard     | 8            |
+----+----------------+--------------+
```