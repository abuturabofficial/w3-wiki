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

## `dict` Dictionaries

A dictionary (or `dict`) is a built-in mutable mapping type that stores data as a collection of unique, hashable key-value pairs.

- Since Python 3.7, dictionaries are ordered by insertion, meaning they preserve the sequence in which keys were added.

Key characteristics:
- Keys must be immutable, while values can be any data type.
- Dictionaries are created using curly braces `{}` with colon-separated key-value pairs.