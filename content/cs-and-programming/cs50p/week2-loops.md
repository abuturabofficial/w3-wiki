---
draft: false
date: "2026-09-12T07:35:11+05:00"
title: "Week2: Loops"
linkTitle: "Loops"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 3
---

| Week 2: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week2-loops) |
| :-------------------: | :----------------------------------------------------------------------------------: |

## Loops

Ability in Python and other programming languages, to do something again and again.

### `while` Loops

- Runs for forever unless certain conditions are met.

An infinite loop (design flaw):

```py{title="cat.py"}
i = 3
while i != 0:
    print('meow')
```

- This code will run for forever unless interrupted by the user (<kbd>Ctrl</kbd> + <kbd>C</kbd>).
- `i != 0` will always remain True, we change the value of i inside the loop on each run.

Well designed `while` loop:

```py {title="cat.py"}
i = 3
while i != 0:
    print('meow')
    i = i - 1
```

- On each run, `i = i - 1` reduces the value of `i` by one digit. Until `i != 0` condition is no longer true, and the loop stops.

### `for` loop

In Python, a for loop is a control flow statement used to iterate over a sequence (such as a list, tuple, string etc.) or any other iterable object.

```py{title="cat.py"}
for i in [0, 2, 3]:
    print("meow")
#OR using range() function
for i in range(3):
    print("meow")
```

We are not using the `i` variable in the code, though it has a use case for holding the range value.

The more Pythonic approach is to use `_`, when you don't care about the variable used or not use it later in the code.

```py{title="cat.py"}
for _ in range(3):
    print("meow")
```

## List `[]`

A list in Python, is a ordered, and mutable data structure used to store a collection of items in a single variable.

- Defined using square brackets `[]`
- Each list element is separated by commas
- Lists are heterogeneous, meaning they can contain elements of different data types (such as integers, strings, booleans or else) within the same structure.
- Each element has an index starting from `[0]`.

### `len()` function

> It returns number of items (length or size) in an object, such as strings, lists, tuples, dictionaries, sets, etc.

```py{title="hogwarts.py"}
students = ["Hermione", "Harry", "Ron"]
for i in range(len(students)):
  print(i + 1, students[i])
```

### List Methods

**To add an item to a list:**

```py
list.append("name")
```

The `list.append()` can also add/append another list to the particular list.

**To add multiple items at once to the list**

```py
list.extend(["Silly", "Donkey King"])
```

The same `list.append(["Silly", "Donkey King"])` would have added them as a list to the existing list.

**Remove an item's first instance from a list:**
For a single item:

```py
list.remove("Silly")
```

You can remove a nested list:

```py
list.remove(["Silly", "Donkey King"])
```

**Add an item at the particular place in the list**

```py
list.insert([index], "Marty")
```

**Reverse the order of a list**

```py
list.reverse()
```

**Remove the last item from a list**

```py
list.pop()
```

**To clear the whole list**

```py
list.clear()
```

### List Comprehension

> List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list. --- W3School

```py
newlist = [expression for item in iterable if condition == True]
```

> [!INFO]
> In Python, An expression is a combination of values, variables, operators, and function calls that evaluates to a single value.

```py
list = []
for i in range(20):
    if i%2 == 0:
        list.append(i)
print(list)
```

Using list comprehension, the whole for loop can be condensed to a single line:

```py
list = []
even_list = [i for i in range(20) if i%2==0]
print(even_list)
```

## Dictionaries `dict`

A dictionary (or `dict`) is a built-in mutable mapping type that stores data as a collection of unique, hashable key-value pairs.

- Since Python 3.7, dictionaries are ordered by insertion, meaning they preserve the sequence in which keys were added.

Key characteristics:

- Keys must be immutable, while values can be any data type.
- Dictionaries are created using curly braces `{}` with colon-separated key-value pairs.

### Dictionary Methods

> Python dictionary methods are built-in functions designed to manipulate, access, and manage the key-value pairs stored in Python dictionaries.

**If you want to get the value of specific key and don't know if that exists:**

```py
dict.get("name", "Unknown")
```

If "name" is not a valid key, it will return "Unknown" instead of throwing error if we have tried to get it via `dict.["name"]`.

**To update the dictionary.**

```py
dict["name"] = "David"
```

Another method to update a dictionary is via `dict.update()`. It takes another dictionary as an arguments adds to the current dictionary.

```py
dic.update({"name": "Dawood", "name": "Amin"})
```

**To return all keys in the dict:**

```py
dict.keys()
```

**To return all values in the dict:**

```py
dict.values()
```

**Delete a particular key from the dictionary:**

```py
dict.pop("key")
```

**To clear the whole dictionary key-value pairs:**

```py
dict.clear()
```

_**Return the key-value pairs as tuples in the dictionary**_

```py
dict.items()
```

It returns the both key and value pairs as tuples, which we can access as:

```py
for key, value in dict.items()
    print(key, value)
```

### Dictionary Comprehension

> Dictionary comprehension is used to create a dictionary in a short and clear way. It allows keys and values to be generated from a loop in one line. This helps in building dictionaries directly without writing multiple statements. --- GeeksforGeeks

```py
dict_comp = {key: value for key, value in iterable if condition}
```

Normal dictionary creation with a starting empty dict.

```py
dict = {}
for i in range(10):
    if i%2 == 0:
        dict[i] = i ** 2
print(dict)
```

The dict comprehension:

```py
dict = {}
dict_comp = {i:i**2 for i in range(10) if i%2==0}
print(dict_comp)
```

## `None`

**None** is special built-in constant that represents the absence of a value or a null value. It's the sole instance of the **NoneType** class and acts as a singleton, meaning there is only one `None` object in any Python interpreter session.

- `None` is distinct from `0`, `False`, or an empty string `""`, though it evaluates to `False` in boolean contexts.
- Functions that don't explicitly return a value automatically return `None`.

## Tuples

Tuples are used to store multiple items in a single variable.

> A tuple is a collection which is ordered and unchangeable. ---W3School

- Tuples are written within parenthesis `()`.
- A tuple can contain different data-types at once
- A one item tuple can be created with `("item1", )`, otherwise Python will not recognize it.
- The `()` will create an empty tuple.
- The `len()` can be used to find out the number of items in the tuple.

### Tuples Items

Tuple items are ordered, unchangeable, and allow duplicate values.

Tuples items are indexed, the first item has index`[0]`, the second item has index`[1]` etc.