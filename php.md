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

### Arrays as maps

associative array:
```php
       $assocCar = array(‘year’ => 2012,
                   ‘colour’ => ‘blue’,
                   ‘doors’ => 5,
                   ‘make’ => “BMW”);
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

### While Loop

```php
while(condition) {
    do_something();
}
```

alternate syntax for while:
```php
while(condition):
endwhile;
```

do-while syntax:
```php
do {
somecommand;
} while(condition);
```

## Functions

String functions:
```php
    $length = strlen(“Olivier”);
    print $length;
    $uppercase = strtoupper($myname);
    $lowercase = strtolower($myname);
```

Array functions:
```php
    sort($array);
    rsort($array);
    join(“, “, $array)
```

* ```strpos()```: find dhe position of the forst occurence of a substring in a string.

Function syntax:
```php
    function name(paramenters){
    statement;
    return “somestring”;
    }
```

## Classes

Simple class:
```php
        class Person {
            public $isAlive = true;
            public $firstname;
            public $lastname;
            public $age;
        }
        $teacher = new Person();
        $student = new Person();
        
        # Accessing public elements of the class.
        echo $teacher->$isAlive;
}
```

Same class with constructor:
```php
       class Person {
            public function __construct($firstname, $lastname, $age){
                $this->$firstname = $fistname;
                $this->lastname = $lastname;
                $this->age = $age;
            }
            public $isAlive = true;
            public $firstname;
            public $lastname;
            public $age;
        }
        $teacher = new Person(“boring”,”12345”,12345);
        $student = new Person(“Bla”, “Blub”, 30);
        echo $teacher->$isAlive;
        }
```

Dog class:
```php
        class Dog {
            public $numLegs = 4;
            public $name;

            public function __construct($name){
                $this->name = $name;
            }

            public function bark(){
                return “Woof!”;
            }

            public function greet(){
                return “Hi, I am $this-name”;
            }
        }

        $dog1 = new Dog(“Barker”);
        $dog2 = new Dog(“Amigo”);

        echo $dog1.bark();
        echo $dog2.greet();
```

### Inheritance

```php
    class Shape {
    public $hasSides = true;
    }

    class Square extends Shape {
    }

    if (property_exists($square, “hasSides”)){
        echo “I have sides!”;
    }
```

Overriding Parent Methods:
```php
    class Shape {
        $sides = true;
    }

    class Square extends Shape {
        $sides = 4;
    }
```
* Just overwrite the property in the child class. The child class has precedence over the parent class.
* Methods that start with the ```final``` keyword can not be overwriten by child classes.

### Constants in classes
Constants can not be overwriten:
```php
      class Person {
          
      }
      class Ninja extends Person {
        const stealth = “MAXIMUM”;
        
      }
      // ...and here!
      echo Ninja::stealth;
      
    }
```

### Static Keyword

With the ```static``` keyword a class’s property can be accessed without having to create an instance of the class.

```php
        class King {
          // Modify the code on line 10...
          public static function proclaim() {
            echo “A kingly proclamation!”;
          }
        }
        // ...and call the method below!
        
        echo King::proclaim();
```
