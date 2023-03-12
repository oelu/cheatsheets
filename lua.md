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
