---
draft: false
date: "2026-10-29T08:25:34+05:00"
title: "Week 9: Et Cetera"
linkTitle: "Et Cetera"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 10
---

| Week 9: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week9-et-cetera) |
| :-------------------: | :--------------------------------------------------------------------------------------: |

## Set `set()`

Sets are used to store multiple items in a single variable.

Set is one of 4 built-in data types in Python used to store collections of data, the other 3 are `list()`, `tuple()`, and `dict()`, all with different qualities and usage.

> A set is a collection which is unordered, unchangeable, and unindexed.

- Sets are written with curly brackets.
- They don't allow duplicate values.
- Set items can appear in a different order every time, and cannot be referred to by index or key.
- The values `True` and `1` are considered the same value in sets, and are treated as duplicates.
- The values `False` and `0` are considered the same value in sets, and are treated as duplicates.

> [!NOTE]
> Set items are unchangeable, but you can remove items and add new items

### Get the Length of a Set

To determine how many items a set has, use `len()` func.

```py
fruits = {"Apple", "Kiwi", "Banana"}
print(len(fruits))
```

### Set Items --- Data Types

Set items can be of any data type.

String, int, and boolean data types:

```py
fruits = {"Apple", "Kiwi", "Banana"}
nums = {1, 2, 3, 4}
bool = {True, False, True, False}
```

A set can contain different data types.

### The `set()` Constructor

It is also possible to use the `set()` constructor to make a set.

```py
fruits = set(("apple", "banana", "kiwi"))
print(fruits)
```

### Remove Item

To remove an item in a set, use the `remove()` or the `discard()` method.

- You can also use the `pop()` method to remove an item, but this method will remove a random item, so you cannot be sure what item gets removed.
- The `clear()` method empties the set.
- The `del` keyword will delete the set completely.

```py
fruits = {"Apple", "Kiwi", "Banana"}
fruits.remove("Kiwi")
print(fruits)
```

> [!NOTE]
> If the item to remove doesn't exist, `remove()` will raise an error.
> Meanwhile, it the item to remove doesn't exist, `discard()` will raise no error.

## The `global` Variable

Variables that are created outside of a function are known as global variables

Global variables can be used by everyone, both inside of functions and outside.

- If you create a variable with the same name inside a function, this variable will be local, and can only be used inside the func. The global variable with the same name will remain as it was, global and with original value.

```py
balance = 0 #global var

def current_balance():
    balance = 1000 #func local var
    print("Balance:", balance)

current_balance()
print("Balance:", balance)
```

### The `global` keyword

Normally, when you create a var inside a func, that var is local, and can only be used inside that func.

To create a global var inside a function, you can use `global` keyword

To change a value of a global variable inside a func, refer to the variable by using `global` keyword.

```py
balance = 0 #global var

def current_balance():
    global balance
    balance = 1000 #changes global var value to 1000
    print("Balance:", balance)

current_balance()
print("Balance:", balance)
```

---

# References

- Python Sets via [W3Schools](https://www.w3schools.com/python/python_sets.asp)
- Python --- Global Variables via [W3Schools](https://www.w3schools.com/python/python_variables_global.asp)