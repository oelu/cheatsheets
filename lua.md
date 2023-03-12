# LUA
* Some Notes from the crash course at: http://luatut.com/crash_course.html

<!-- toc -->
* [Function Definition](#function-definition)
* [Comments](#comments)
  * [Block Comments](#block-comments)
  * [Single and multi line comments](#single-and-multi-line-comments)
* [Variables](#variables)
* [For Loops](#for-loops)
* [Conditional Statements](#conditional-statements)
  * [IF Condition](#if-condition)
  * [Else](#else)
* [Operators](#operators)
* [Strings](#strings)
* [Tables](#tables)

<!-- toc stop -->

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

* Concatenation ``..``, use ``”str1”..”str2”``

```lua
> print(“string1”..” “..”string2”)
string1 string2
```

* Length is shown with ``#`` as a prefix operator.

```lua
string = “this is a string”
> print (#string)
16
```

* Multiline strings need to be enclosed in ``[[ string ]]``

* Print each line in multiline string
```lua
for line in lines:gmatch("[^\n]+") do
    print(line)
end
```

## Tables

``table.insert(table, element)`` : insert ``element`` in table ``table``
``table.sort()`` : sort a table in ascending order

Printing out a table. Elements in the table will be passed to the function (eg. ``print``) as argument: 

```lua
table.foreach(table, print)
```

## Modules 

Modules can be imported with: 

```lua
require “util”
```
This searches the lua search path for the file ``util.lua``

