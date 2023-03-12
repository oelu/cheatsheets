# LUA
* Some Notes from the crash course at: http://luatut.com/crash_course.html

## Function Definition

    function get_all_factors(number)
        ...
    end

## Comments

### Block Comments

    --[[--
        block comment

        @Parameters: number
    
        @Returns: return value
    --]]--

### Single and multi line comments

    -- Single Line Comment

    --[[ multi line
    comment ]]

## Variables

    number = 1000
    string = “some text”
    Nothing = nil

Local variables: 

    local num = 1000

## For Loops

    > for i = 1, 10, 1 do
    print("number is", i)
    end
    number is       1
    number is       2
    number is       3
    ...
    number is       10
    >

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

    if name then
        print (“Hello”, name)
    end

### Else

    if name then
        print (“Hello”,name)
    else
        print(“Hello Stranger”)
    end

## Operators

``%``:
    Modulus Operator (remainder division)

``+``, ``-``, ``*``, ``/`` and ``^``: 
    Common Operators such as the ones above are also present

## Strings

