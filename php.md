# PHP
Some notes on PHP syntax.

## Embed PHP in html

```php
<?php
?>
```

## Control Structure

### Conditions
* > Greater than
* < Less than
* <= Less than or equal to
* >= Greater than or equal to
* == Equal to
* != Not equal to

### If / Else
```php
        if (True) {
            echo “hello”;
        }
        else if (False) {
            echo “this is False”;
        }
        else {
            echo “test”;
        }
```
### Switch Statement
```php
    switch (2) {
        case 0:
            echo ‘The value is 0’;
            break;
        case 1:
            echo ‘The value is 1’;
            break;
        case 2:
            echo ‘The value is 2’;
            break;
        default:
            echo “The value isn’t 0, 1 or 2”;
    }
}>
```

The switch statement does have an alternative syntax for better readability.
```php
    switch ($variable):
        case 0:
            echo “The value is 0”;
            break;
    endswitch;
```

## Data Structures

### Array

```php
<?php
      $array = array(“Egg”, “Tomato”, “Beans”);
?>
```

Accessing elements by offset: 
```php
        $tens = array(10, 20, 30, 40, 50);
        echo $tens[2];
```

Values can be deleted with ```unset```:
```php
    unset($languages[0]);
```

## Loops

### For Loop
```php
        // Echoes the first five even numbers
        for ($i = 2; $i < 11; $i = $i + 2 ){
          echo $i;
        }
```

### Foreach Loop

```php
          $langs = array(“JavaScript”,
          “HTML/CSS”, “PHP”,
          “Python”, “Ruby”);
        
          foreach ($langs as $lang) {
              echo “<li>$lang</li>”;
          }
        
          unset($lang);
```
