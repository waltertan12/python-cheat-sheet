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
Tuples are very similar to lists -- they are order collections of items

However, tuples cannot be modified i.e. they are immutable.


```python
# define a tuple by using parenthesis
first_couple = ("Barack", "Michelle")
print(first_couple) # ("Barack", "Michelle")

# access a tuple by using the square brackets
print(first_couple[0]) # "Barack"
print(first_couple[1]) # "Michelle"

# loop through a tuple
for person in first_couple:
	print(person)

# assigning a new item to the list will throw a TypeError
first_couple[0] = "Donny" # will throw a TypeError :(
```

[[Back to top](#table-of-contents)]

## Dictionaries
### Definition
Dictionaries is a collection of data that helps connect pieces of information. 
Dictionaries accomplish this by storing information in key-value pairs.

```python
titles = {
    "Elizabeth" => "Queen of England",
    "Philip" => "Prince, Duke of Edinburgh",
    "Charles" => "Prince of Wales",
    "William" => "Duke of Cambridge",
    "George" => "Prince of Cambridge"
}
```

Notice how each name in the list is associated with a title.

### Accessing items in a dictionary
You can access items in a list by using a key or index

```python
# you can use square brackets
print(titles["Elizabeth"]) # "Queen of England"
print(titles["George"]) # "Prince of Cambridge"


# or you can use the get() method
print(titles.get("Charles")) # "Prince of Wales"

# the get method lets you provide a fallback value if the key/index does not exist
print(titles.get("WaLtEr", "RULER OF THE GALAXY")) # "RULER OF THE GALAXY"
```

### Adding new values
To add new values to the dictionary, simply add more key value pairs!
```python
titles["Charlotte"] = "Princess of Cambridge"
print(titles["Charlotte"]) # "Princess of Cambridge"
```

### Editing values
To edit existing key-value pairs, reassign the key to a new value
```python
titles["George"] = "Great grandson of Elizabeth"
print(titles["George"]) # "Great grandson of Elizabeth"
```

### Removing values
To remove values, use the `del` operator on a key
```python
del titles["Philip"]
print(titles.get("Philip", "Nobody here")) # "Nobody here"
```

### Looping through a dictionary
TODO

[[Back to top](#table-of-contents)]
