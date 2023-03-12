# LUA CheatSheet
* Some Notes from the crash course at: http://luatut.com/crash_course.html and http://www.lua.org

<!-- toc -->
* [Function Definition](#function-definition)
  * [Default arguments](#default-arguments)
  * [Multiple return values](#multiple-return-values)
  * [Variable number of arguments](#variable-number-of-arguments)
  * [Named Arguments](#named-arguments)
  * [Define a function like a variable](#define-a-function-like-a-variable)
  * [Higher order function](#higher-order-function)
  * [Closures](#closures)
  * [Non-Global Functions](#non-global-functions)
* [Comments](#comments)
  * [Block Comments](#block-comments)
  * [Single and multi line comments](#single-and-multi-line-comments)
* [Variables](#variables)
* [For Loops](#for-loops)
  * [Numeric For](#numeric-for)
  * [Generic For](#generic-for)
* [Conditional Statements](#conditional-statements)
  * [IF Condition](#if-condition)
  * [Else](#else)
  * [While](#while)
* [Operators](#operators)
* [Strings](#strings)
  * [Standard String Library](#standard-string-library)
  * [Patterm-Matching Functions](#patterm-matching-functions)
    * [string.find() and string.gsub()](#stringfind-and-stringgsub)
    * [string.match()](#stringmatch)
    * [string.gsub()](#stringgsub)
    * [string.gmatch()](#stringgmatch)
* [Tables](#tables)
* [Modules](#modules)
* [Files](#files)
* [Errors](#errors)

<!-- toc stop -->

## Function Definition
* Functions are first class elements in lua. Therefore variables can store functions. 
* Any numbers of arguments can be passed to a number, arguments that are not a parameter will evaluate to ``nil``.

```lua
function get_all_factors(number)
    ...
end
```

### Default arguments
Default arguments can be set in the function body: 
```lua
function incrementcounter (n)
    n = n or 1 -- assign default value to n if n evaluates to nil
    count = count + n 
end
```

### Multiple return values
Return Statements can return more than one value: 

```lua
function multireturn()
    return 1, 2
end
```

### Variable number of arguments

``...`` (vararg expression) can be used to pass a variable number of arguments to a function:

```lua
function add(...)
    local s = 0
    for i, v in ipairs(...) do -- evaluate ... and return position (i) and value (v)
        s = s + v   -- add v to sum of s 
        end
    return s
end
```

### Named Arguments
Named arguments can be passed to a function via a table. This is useful
if the function receives many optional parameters.

```lua
args{old=”temp.lua”, new=”temp1.lua”}

function rename(arg)    --> this is the function definition

rename(args) --> uses the argument table args
```

### Define a function like a variable

```lua
function foo(x) return 2*x  end

foo = function (x) return 2*x   end     --> is equal to the statement above
```

Functions can also be assigned to tables: 
```lua
-- example, to show that tables can be used as function store

foo = {} --> create new table
foo.bar = function () print("foo bar!") end --> assign function to key bar of table foo

foo.bar() --> produces output "foo bar!"
```

```bash
$ lua function_table.lua
foo bar!
```

### Higher order function
Functions can receive other functions as arguments. These type of functions are
called higher order functions: 

```lua
table.sort(something, function (a,b) return (a.name > b.name) end)
--> sort receives the sorting algorithm for two values and will expand it to all values in the list
```

### Closures
Functions can contain other functions. So, we can embed function b in function a. This mechanism
can be used to overwrite luas default functions. 

```lua
local oldSin = math.sin  --> assign the math.sin function to oldSin for further access

math.sin = function (x)     --> overwrite original function
    return oldSin(x*math.pi/180)
end
```

### Non-Global Functions
* Tables can contain functions. 

```lua
LIB = {}
LIB.foo = function (x,y) return x + y end
LIB.goo = function (x,y) return x - y end
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

### Numeric For

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

### Generic For

Generic for uses an ``iterator function`` to iterate over all elements in a data structure.

```lua
t = {1, 2, 3}
for k in pairs(t) do print(k) end --> only stored value will be printed
for k,v in pairs(t) do print(k,v) end --> key and value pair will be printed
```

``k`` and ``v`` are used for key and value pairs. 

The standard library provides iterators: 
* ``io.lines``: iterate over lines in file
* ``pairs``: iterate over ``key`` and ``value`` pairs in tables. 
* ``string.gmatch`: iterate over words in strings. 

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

```lua
if a == 0 then a = 1 end
```

### Else

```lua
if name then
print (“Hello”,name)
else
print(“Hello Stranger”)
end
```

### While

Print as long as a[i] does contain values, eg. does not evaluate to ´´nil´´ does contain values, eg. does not evaluate to ``nil``
```lua
while a[i] do
    print (a[i])
    i = i + 1
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

* Multi line strings need to be enclosed in ``[[ string ]]``

* Print each line in multi line string
```lua
for line in lines:gmatch("[^\n]+") do
    print(line)
end
```

### Standard String Library
* Is available with ``string.functionname``.

Common functions:
* ``string.len(string)``: returns length of string
* ``string.rep(s, n)`` or ``s:rep(n)`` returns the string ``s`` ``n``-times
* ``string.lower(s)`` returns lowercase version of string ``s``
* ``string.upper(s)``returns uppercase version of string ``s``
* ``string.sub(s, i, j)`` returns substring of ``s`` ``i``-th to ``j``-th character
* ``string.format()`` used to print string, has similar format options as C function ``printf()``

### Patterm-Matching Functions
``find``, ``match``and ``gsub``

#### string.find() and string.gsub()
``string.find(string, “pattern”)``: searches for a pattern inside a string. Returns ``i``and ``j`` (i=start j=end position of substring in string).
``string.gsub(string, i, j)``: returns string from i-th to j-th character. 

Can be chained together with string.gsub to return matching string: 
```lua
> s = “hello world!”
> print(string.sub(s, string.find(s, “hello”)))
hello
```

#### string.match()
``string.match(string, “pattern”)``: prints out matching pattern.

```lua
> print(string.match(“hello world!”, “hello”))
hello
```

#### string.gsub()
``string.gsub(string, pattern, replacementstring)``: replaces ``pattern`` in string with ``replacementstring``

```lua
> s = “lua is cute”
> s2 = string.gsub(s, “cute”, “great”)
> print(s2)
lua is great
```

#### string.gmatch()
* To be done

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

## Files

* Common Idiom to read files:

```lua
-- prints out error messages
local f = assert(io.open("lua.md", "r"))
local content = f:read("*all")
f:close()
print(content)
```

## Errors

Explicit errors can be called with the ``error()`` function. ``assert()`` 
checks if an error has occurred and prints the ``error message`` given as argument.

```lua
n = assert(io.read(“*number”), “invalid input”)
````
