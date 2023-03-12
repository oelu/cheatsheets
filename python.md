# Python Notes

## Arithmetic

- `+`
- `-`
- `*`
- `/`
- `%` modulo

- `myvar *= 0.9` 90% of myvar
- `myvar -= 3` subtract 3 from myvar


## Variables

- `mynum = 1234`
- `int` integer
- `float` float
- `type` check type of object
- `mynum = 1.3` creates a float variable
- `bol` True or False
- types can be converted
	- `str()` convert to string
	- `float()` convert to float
	- ...

## Strings

- `mystring = "Test String"`
- `len(mystring)` length of string
- `mystring[0]` - python uses indexing for string [0] returns the first character
- `print("var1 = {} and var2 = {}".format(var1,var2))` print format strint
- `split` can be used to split strings into lists

# Tipps and Tricks

- Use `bpython` to test out little snippets of code. In comparison to python's standard interactive shell it offers command completion and function parameter view.
- Use <https://www.hackerrank.com/> for coding challenges

## Lists

- Sample liste: `list_of_random_things = [1, 3.4, 'a string', True]`
- Lists can be accessed with `list[0]` up until `list[len(list)-1]`

- When using slicing, it is important to remember that the lower index is inclusive and the upper index is exclusive.

Therefore, this:
>>> list_of_random_things = [1, 3.4, 'a string', True]
>>> list_of_random_things[1:2]
[3.4]
- Lists are mutable
- `len()` length of list
- `max()` max element of list
- `min()` smallest element of list
- `sorted()` sorted list
- `join()` join list elemnts to string
- `append()` add something to a list

## Tuples

- Store related types of information
- Ordered collection of objects
- Immutable (no adding or removing items)
- Saves processing power

```python
dimensions = 10, 20, 30 			# assigning a tuple
length, width, height = dimensions 	# unpacking

```

## Sets

- Sets contain *unique* elemnts
- `add` adds elements to a list
- Sets are unordered
- `pop()` removes one random element from the set
- Sets are like mathematical sets. They support fast intersect, union operators. 

## Dictionaries
- Store pairs
- key and value store
- keys do not need to be from the same datatype
- lookup of values can be done using `dict["lookupval"]` or dict.get["lookupval"]. Get returns `None` if the lookup failes, a lookup with [] returns an error.

```python
fruit_weight = {"apple": 5, "banana": 6}
fruit_weight["apple"]
```