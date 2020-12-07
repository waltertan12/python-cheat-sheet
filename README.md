# Python Cheat Sheet
Quick cheat sheet for basic Python operations

## Table of Contents
- [Variables](#variables)
    - [Definition](#definition)
- [Files](#files)
	- [How to open files](#how-to-open-files)
	- [How to read files](#how-to-read-files)
- [Lists](#lists)
    - [Definition](#definition-1)
    - [Accessing Items in a List](#accessing-items-in-a-list)
    - [Looping through a list](#looping-through-a-list)
    - [Adding to a list](#adding-to-a-list)
    - [Copying a list](#copying-a-list)
- [Tuples](#tuples)
    - [Definition](#definition-2)
- [Dictionaries](#dictionaries)

## Variables
### Definition
Variables are used to store values. Values can be strings, numbers, lists, dictionaries, etc.

```python
greeting = "hello!"
print(greeting) # "hello!"
```

[[Back to top](#table-of-contents)]

## Files
### How to open files
To open a file, use the Python function `open`

```python
filename = "secret.txt"
file_object = open(filename)
```

### How to read files
To read lines in the fall, call `readlines` on the file object
```python
lines = file_object.readlines()
for line in lines:
    print(line)
```

[[Back to top](#table-of-contents)]

## Lists
### Definition
A list is a collection of items stored in a particular order

```python
names = ["Elizabeth", "Philip", "Charles", "William", "George"]
```

### Accessing items in a list
You can access items in a list by using an index i.e. the position of the item in the list
```python
# Python is zero indexed which means the first item in the list is 0
print(names[0]) # "Elizabeth"
print(names[3]) # "William"
```

You can even use negative indexes to look backwards
```python
print(names[-1]) # "George"
print(names[-2]) # "William"
```

However, you'll get in trouble if you access an index that doesn't exist
```python
print(names[10]) # will throw an IndexError :(
print(names[-6]) # will also throw an IndexError :(
```

### Looping through a list
You can also loop through lists
```python
# Most straightforward way to iterate through a list
for name in names:
    print(name)

# Using range is useful if you also need the index of the item
for index in range(len(names)):
    name = names[index]
    print(index, name)
```

### Adding to a list
To add items to a list, use the `append` function
```python
names.append("Charlotte")
print(names) # ["Elizabeth", "Philip", "Charles", "William", "George", "Charlotte"]
```

### Copying a list
To copy a list, you can use this special colon syntax `[:]`
```python
copy_of_names = names[:]
print(copy_of_names) # ["Elizabeth", "Philip", "Charles", "William", "George", "Charlotte"]
```

You can also specify specific parts of the list to copy
```python
# copy items from index 1 until index 3 (not inclusive)
partial_copy_of_names = names[1:3]
print(partial_copy_of_names) # ["Philip", "Charles"]
```

[[Back to top](#table-of-contents)]

## Tuples
### Definition
Tuples are very similar to lists. However, tuples cannot be modified i.e. they are immutable.

```python
first_couple = ("Barack", "Michelle")
print(first_couple) # ("Barack", "Michelle")
first_couple[0] = "Donny" # will throw a TypeError :(
```

[[Back to top](#table-of-contents)]

## Dictionaries
TODO

[[Back to top](#table-of-contents)]
