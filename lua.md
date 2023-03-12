# LUA
* Some Notes from the crash course at: http://luatut.com/crash_course.html

## Function Definition

    ```lua
    function get_all_factors(number)
        ...
    end
    ```

## Comments

### Block Comments

    ```lua
    --[[--
        block comment

        @Parameters: number
    
        @Returns: return value
    --]]--
    ```

### Single and multi line comments

    ```lua
    -- Single Line Comment

    --[[ multi line
    comment ]]
    ```

## Variables

    ```lua
    number = 1000
    string = “some text”
    Nothing = nil
    ```

Local variables: 

    ```lua
    local num = 1000
    ```

## For Loops

    ```lua
    > for i = 1, 10, 1 do
    print("number is", i)
    end
    number is       1
    number is       2
    number is       3
    ...
    number is       10
    >
    ```

Syntax is ``for the_number = 1, MAXIMUM, STEP do``

## Conditional Statements 
* Evaluates to ``true`` or ``false``
* Statements can be neglected with ``not``
* Equality ``a == b`` tests if two variables are equal
* Inequality ``~=``evaluates to ``true`` if two variables are not equal

### IF Condition
Note: undeclared variables evaluate to ``nil``and nil is evaluated as ``false`` in if statements.
Therefore the following snippet checks if the variable ``name`` exists and then prints a greeting
for that name. 

    ```lua
    if name then
        print (“Hello”, name)
    end
    ```

### Else

    ```lua
    if name then
        print (“Hello”,name)
    else
        print(“Hello Stranger”)
    end
    ```

## Operators

``%``:
    Modulus Operator (remainder division)

``+``, ``-``, ``*``, ``/`` and ``^``: 
    Common Operators such as the ones above are also present

## Strings

