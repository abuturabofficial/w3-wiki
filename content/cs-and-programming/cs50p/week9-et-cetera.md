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

## Constants

One have some constant value somewhere in the code, in Python and other programming languages, a convention is to bring them towards the start.

- Capitalize the whole `CONSTANT=<value>` word, to indicate to other programmers working on the code, they shouldn't touch it.

```py
MEOWS = 3
for _ in range(3):
    print("meow")
```

- But nothing is stopping other programmers to re-assign the constant's value to something else unlike other programming languages, Python operates on "honor" system.
- The same applies to the class variables.

```py
class Cat:
    MEOWS = 3

    def meow(self):
        for _ in range(Cat.MEOWS):
            print("meow")

cat = Cat()
cat.meow()
```

## Type hints

- Python is a dynamically typed language, you don't need to mention if your variable value is str, int, or float. Python figures this out own its own.
- Unlike other languages like C, C++, Java etc., the programmers have to specify sometimes what type of variable you want something to be.
- Type hints help the programmer find out bugs more easily.
- Python has type hints too, but they are not strictly enforced by the language.

```py{title="meows.py"}
def meow(n: int):  # type hint
    for _ in range(n):
        print("meow")

number: int = int(input("Number: "))  # type hint
meow(number)
```

The `mypy` module provides support for type hints in Python code.

```sh
pip install mypy
```

Run the `mypy` on `meows.py`:

```sh
mypy meows.py
```

![](/notes/cs50p/week9-et-cetera-1.webp)

To check, if function returns something:

```py
def meow(n: int) -> str:  # type hint: func should return a str
    return "meow\n" * n

number: int = int(input("Number: "))  # type hint
meows: str = meow(number) # type hint

print(meows, end="")
```

## docstrings

Python provides docstrings to add comments to your code.

- Python has documentation generation tools, which can generate a PDF/md from your docstrings inside your code.

```py
def meow(n: int) -> str:  # type hint
    """
    Meow n times.

    :param n: Number of times to meow
    :type n: int
    :raise TypeError: if n is not int
    :return: A string of n meows, one per line
    :rtype: str
    """
    return "meow\n" * n

number: int = int(input("Number: "))  # type hint
meows: str = meow(number)

print(meows, end="")
```

## The `argparse` module

The `argparse` module makes it easy to build user-friendly command-line interfaces.

It parses arguments and options, generates help and usage messages automatically, and provides errors when users give the program invalid arguments.

| Member                        | Description                                                                    |
| ----------------------------- | ------------------------------------------------------------------------------ |
| Action                        | Base class for how an argument should be handled (store, append, count, etc.). |
| add_argument()                | ArgumentParser method: Define a new positional or optional argument.           |
| add_subparsers()              | ArgumentParser method: Create sub-commands (e.g. git commit, git push).        |
| ArgumentDefaultsHelpFormatter | Help formatter that shows default values next to options.                      |
| ArgumentError                 | Error raised for invalid arguments or combinations.                            |
| ArgumentParser()              | Create a parser; add options/arguments and parse the command line.             |
| ArgumentTypeError             | Error raised when converting a value to the required type fails.               |
| BooleanOptionalAction         | Action that creates --foo / --no-foo style boolean flags.                      |
| error()                       | ArgumentParser method: Raise an error message and exit.                        |
| exit()                        | ArgumentParser method: Exit the program with a status code.                    |
| FileType()                    | Helper for opening files from argument values (e.g. "-" for stdin).            |
| format_help()                 | method: Return the full help text as a string.                                 |
| format_usage()                | ArgumentParser method: Return the short usage message as a string.             |
| HelpFormatter                 | Base class for help text formatting.                                           |
| MetavarTypeHelpFormatter      | Formatter that adds information about argument types.                          |
| Namespace                     | Simple object used to store parsed values (dot-attribute access).              |
| ONE_OR_MORE                   | Marker used in help/usage to indicate one or more values are expected.         |
| OPTIONAL                      | Marker used in help/usage to indicate an optional argument.                    |
| PARSER                        | Marker used internally for sub-parsers in usage strings.                       |
| parse_args()                  | ArgumentParser method: Parse the command line and return a Namespace.          |
| parse_known_args()            | ArgumentParser method: Parse known options and return (namespace, remaining).  |
| PARSER                        | Marker used internally for sub-parsers in usage strings.                       |
| print_help()                  | ArgumentParser method: Print the full help text to stdout.                     |
| print_usage()                 | ArgumentParser method: Print the short usage message to stdout.                |
| RawDescriptionHelpFormatter   | Formatter that preserves whitespace in the description.                        |
| RawTextHelpFormatter          | Formatter that preserves whitespace in both description and epilog.            |
| REMAINDER                     | Collect all remaining command-line parts into a list.                          |
| SUPPRESS                      | Special value to hide a value from the help/usage output.                      |
| ZERO_OR_MORE                  | Marker used in help/usage to indicate zero or more values are accepted.        |

## unpacking

In Python, unpacking lets you assign or pass multiple values at once by expanding an iterable into individual items.

You'll see it in assignments for parallel name binding in expressions and function calls via the iterable unpacking(\*) and dictionary unpacking (\*\*).

**The single asterisk** (\*) in Python is used for two main way:

1. Unpacking Lists (or Tuples)
2. Unpacking in Function calls

**The Double asterisk** (\*\*) is used for unpacking dictionaries as keyword arguments (key-value pairs).

1. This passes the dictionary entries as keyword arguments to the function.
2. You can also use \*\* to combine dictionaries in a clean way.

```py
defaults = {"debug": False}
overrides = {"debug": True, "verbose": True}

final_config = {**defaults, **overrides}
print(final_config)
# Output: {'debug': True, 'verbose': True}
```

In this case:

- The `overrides` dictionary updates values from `defaults`.
- The result is a merged dictionary where later entries take priority.

In assignments, the right-hand side must be an **iterable**, and the left-hand side is a **comma-separated sequence of assignment targets**, often written as a tuple of names. The number of values and targets must match. Alternatively, you can use a single starred target(*rest) to collect multiple values into a list.

In function calls, *iterable expands an iterable into **positional arguments**, while **dictionary expands into **keyword arguments**.

### When to Use \* and \*\*

- \* ---> Capture or expand multiple values (lists, args)
- \*\* ---> Capture or expand keyword pairs(dicts)
- Perfect for flexible functions, cleaner data handling

### Why use `*` and `**`?

- They make your code more flexible by allowing dynamic argument passing.
- They help you avoid repetition and make code more concise and readable.
- Especially useful in functional programming, API calls, and clean config handling.

### Examples

Parallel assignment and value swapping:

```py
>>> a, b = 1, 2
>>> a, b
(1, 2)

>>> a, b = b, a
>>> a, b
(2, 1)
```

Starred targets:

```py
>>> first, *middle, last = [10, 20, 30, 40]
>>> first
10
>>> middle
[20, 30]
>>> last
40
```

You can also use \* in other positions:

```py
>>> *start, end = [1, 2, 3]
>>> start = [1, 2], end = 3

>>> first, *rest = [10, 20, 30]
>>> first = 10, rest = [20, 30]
```

Function calls:

```py
>>> def greet(greeting, name):
...     return f"{greeting}, {name}!"
...
>>> args = ("Hello", "Pythonista")
>>> greet(*args)
'Hello, Pythonista!'

>>> def connect(host, port, timeout=10):
...     return host, port, timeout
...
>>> conn_params = {"host": "localhost", "port": 8000}
>>> connect(**conn_params)
('localhost', 8000, 10)
```

Unpacking in expressions:

```py
>>> numbers = [0, *range(1, 4), 4]
>>> numbers
[0, 1, 2, 3, 4]
```

## *args and **kwargs

By default, a function must be called with the correct number of arguments.

However, sometimes you may not know how many arguments that will be passed into your function.

`*args` and `**kwargs` allow functions to accept an unknown number of arguments.

### Arbitrary Arguments --- *args

If you don't know how many arguments will be passed into your function, add a `*` before the parameter name. This way, the function will receive a tuple of arguments and can access the items accordingly.

<u>Example</u>:

Using *args to accept any number of arguments:

```py
def my_function(*kids):
  print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
```

> [!NOTE]
> Arbitrary Arguments are often shortened to *args in Python documentation.

#### What is *args?

The `*args` parameter allows a function to accept any number of positional arguments.

Inside the function, `args` becomes a tuple containing all the passed arguments.

#### Using *args with Regular Arguments

You can combine regular parameters with *args.

Regular parameters must come before *args:

```py
def my_function(greeting, *names):
  for name in names:
    print(greeting, name)

my_function("Hello", "Emil", "Tobias", "Linus")
```

In this example, `"Hello"` is assigned to `greeting`, and the rest are collected in `names`.

#### Practical Examples with *args

*args is useful when you want to create flexible functions:

```py
def my_function(*numbers):
  total = 0
  for num in numbers:
    total += num
  return total

print(my_function(1, 2, 3)) # Output: 6
print(my_function(10, 20, 30, 40)) # Output: 100
print(my_function(5)) # Output: 5
```

Find the max value:

```py
def my_function(*numbers):
  if len(numbers) == 0:
    return None
  max_num = numbers[0]
  for num in numbers:
    if num > max_num:
      max_num = num
  return max_num

print(my_function(3, 7, 2, 9, 1)) # Output: 9
```

### Arbitrary Keyword Arguments --- **kwargs

If you don't know how many keyword arguments will be passed into your function, add two asterisks `**` before the parameter name.

This way, the function will receive a dictionary of arguments and can access the items accordingly.

<u>Example</u>:

Using **kwargs to accept any number of keyword arguments.

```py
def my_function(**kid):
  print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")
```

> [!NOTE]
> Arbitrary Keyword Arguments are often shortened to **kwargs in Python documentation.

#### What is **kwargs?

The `**kwargs` parameter allows a function to accept any number of keyword arguments.

Inside the function, `kwargs` becomes a dictionary containing all the keyword arguments.

#### Using **kwargs with Regular Arguments

You can combine regular parameters with **kwargs.

Regular parameters must come before **kwargs:

```py
def my_function(username, **details):
  print("Username:", username)
  print("Additional details:")
  for key, value in details.items():
    print(" ", key + ":", value)

my_function("emil123", age = 25, city = "Oslo", hobby = "coding")
```

##### Combining *args and **kwargs

You can use both *args and **kwargs in the same function.

The order must be:

1. Regular parameters
2. *args
3. **kwargs

```py
def my_function(title, *args, **kwargs):
  print("Title:", title)
  print("Positional arguments:", args)
  print("Keyword arguments:", kwargs)

my_function("User Info", "Emil", "Tobias", age = 25, city = "Oslo")
```

> [!TIP]
> Remember: Use `*` and `**` in function definitions to collect arguments, and use them in function calls to unpack arguments.

## map()

The `map()` function executes a specified function for each item in an iterable. The item is sent to the function as a parameter.

<u>Syntax</u>:

```py
map(function, iterable)
```

| Parameter | Description                                                                                                                                                          |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| function  | Required. The function to execute for each item.                                                                                                                     |
| iterable  | Required. A sequence, collection or an iterator object. You can send as many iterables as you like, just make sure the function has one parameter for each iterable. |

<u>Examples</u>:

Make new fruits by sending two iterable objects into the function:

```py
ef myfunc(a, b):
  return a + b

x = map(myfunc, ('apple', 'banana', 'cherry'), ('orange', 'lemon', 'pineapple'))
```

Calculate the length of each word in the tuple:

```py
def myfunc(n):
  return len(n)

x = map(myfunc, ('apple', 'banana', 'cherry'))
```

## List Comprehensions

List comprehension is an easy to read, compact, and elegant way of creating a list from any existing iterable object. Basically, it's a simpler way to create a new list from the values in a list you already have.

It is generally a single line of code enclosed in square brackets. You can use it to filter, format, modify, or do other small tasks on existing iterables such strings, tuples, set, lists, and so on.

Let's see different ways of creating list comprehension and see some of its variants like:

- Simple list comprehension
- List comprehension with single and nested if conditions
- List comprehension with single and multiple if and else conditions
- List comprehension with nested for loops

In Python list comprehension is a single line of code that you write inside the square brackets. It has three components:

1. For loop
2. Condition and expression
3. Output

![](/notes/cs50p/week9-et-cetera-2.webp)

### Examples

Simple list comprehension, taking elements of first list and storing them in the other:

```py
 first = [1, 2, 3, 4, 5]
second = [x for x in first]
```

Above is the simple example, which doesn't do anything to the original data. The point of list comprehension is faster modification to the original data:

```py
first = [1, 2, 3, 4, 5]
second = [x for x in first if x % 2 == 0 ] # filter out only even elements
print(second) # Output: [2, 4]
```

## filter()

The built-in `filter()` function in Python is used to process an iterable and extract items that satisfy a given condition, as determined by a filtering function.

The `filter()` returns an iterator that yields only the elements for which the filtering function returns a truthy value:

```py
numbers = [-2, -1, 0, 1, 2]
positive_numbers = list(filter(lambda n: n > 0, numbers))
list(positive_numbers) # Output: [1, 2]
```

How the above example run:
![](/notes/cs50p/week9-et-cetera-3.webp)

<u>Syntax</u>:

```py
filter(function, iterable)
```

| Argument | Description                                                                             |
| -------- | --------------------------------------------------------------------------------------- |
| function | A function that returns a truthy or falsy value and determines which elements are kept. |
| iterable | An iterable to be filtered, such as a list, tuple, set, generator, or iterator.         |

### filter() Common Use Cases

The most common use cases for the filter() function include the following:

- Extracting specific elements from an iterable based on a condition
- Removing unwanted elements(e.g., None, empty strings) from an iterable
- Processing data collections to retain only items of interest

## Lambda function

Lambda functions are similar to user-defined functions but without a name. They're commonly referred to as **anonymous functions**.

Lambda functions are efficient whenever you want to create a function that will only contain simple expressions --- that is, expressions that are usually a single line of a statement. They are also useful when you want to use the function once.

### How to Define a Lambda Function

You can define a lambda function like this:

```py
lambda argument(s) : expression
```

- `lambda` is a keyword in Python for defining the anonymous function.
- `argument(s)` is a placeholder, that is a variable that will be used to hold the value you want to pass into the function expression. A lambda function can have multiple variables depending on what you want to achieve.
- `expression` is the code you want to execute in the lambda function.

Notice that the anonymous functions doesn't have a return keyword. This is because the anonymous function will automatically return the result of the expression in the function once it is executed.

<u>Examples</u>:

Assume you want to write a function that returns twice the number you pass it:

```py
def f(x):
    return x * 2

f(3)
>> 6
```

Lambda function will look like this:

```py
lambda x : x * 2
```

As mentioned above, the lambda function doesn't have a return keyword. As a result, it will return the result of the expression on its own. The `x` is a place holder, you can use whatever you want.

Now if you want to call a lambda function, you will use an approach known as immediately invoking the function. That looks like this:

```py
(lambda x : x * 2)(3)

>> 6
```

The reason for this is that since the lambda function doesn't have a name you can invoke(it's anonymous), you need to enclose the entire statement when you want to call it.

### Lambda with Built-in Functions

Lambda functions are commonly used with built-in functions like `map()`, `filter()`, and `sorted()`.

## Dictionary Comprehensions

Dictionary comprehension is a feature in Python that allows us to build dictionaries in a single, elegant line of code. It is a similar concept to [list comprehension](#list-comprehensions). The key difference is that instead of generating lists, dictionary comprehension generates key-value pairs.

### Syntax

```py
{key_expression: value_expression for item in iterable if condition}
```

### Examples

<u>Let's create a dictionary where the keys are number from 1 to 5 and the values are their square</u>:

```py
num = [1, 2, 3, 4, 5]
sq = {n: n**2 for n in num}
print(sq) # Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

<u>Let's create a dictionary where the keys are even numbers from 0 to 9, and the values are their squares. We achieve this by adding a condition to filter out odd numbers</u>:

```py
num = range(10)
even_sq={n: n ** 2 for n in num if n % 2 == 0}
print(even_sq) # Output: {0: 0, 2: 4, 4: 16, 6: 36, 8: 64}
```

<u>We can use dictionary comprehension to modify the values in an existing dictionary. For instance, let's double all the values in a dictionary of key-value pairs</u>:

```py
original = {"a": 1, "b": 2, "c": 3}
doubled = {k: v * 2 for k, v in original.items()}
print(doubled)
```

Here, `original.item()` loops through each key-value pair, multiplies each value by 2, and creates a new dictionary with the same keys but updated values. This approach is great for making quick transformations.

## `enumerate()` Function

The `enumerate()` function takes a collection (e.g. tuple) and returns it as an enumerate object.

It adds a counter as the key of the enumerate object.

<u>Syntax</u>:

```py
enumerate(iterable, start=0)
```

| Parameter | Description                                                           |
| --------- | --------------------------------------------------------------------- |
| iterable  | An iterable object                                                    |
| start     | A Number. Defining the start number of the numerate object. Deafult 0 |

<u>Example</u>:

```py
fruits = ['apple', 'banana', 'cherry']

# Rank the fruits in the list
for i, fruit in enumerate(fruits):
	print(i + 1, fruit)
```

## Generators

Generators are functions that can pause and resume their execution.

When a generator function is called, it returns a generator object, which is an iterator.

The code inside the function is not executed yet, it is only compiled. The function only executes when you iterate over the generator.

> [!INFO]
> Generators allow you to iterate over data without storing the entire dataset in memory.
>
> Instead of using `return`, generators use the `yield` keyword.

### The yield keyword

The `yield` keyword is what makes a function a generator.

When `yield` is encountered, the function's state is saved, and the value is returned. The next time the generator is called, it continues from where it left off.

```py
def main():
    n = int(input("What's n? "))
    for s in sheep(n):
        print(s)


def sheep(n):
    for i in range(n):
        yield "🐑" * i

main()
```

> [!INFO]
> Unlike `return`, which terminates the function, `yield` pauses it and can be called multiple times.

### Generators Saves Memory

Generators are memory efficient because they generate values on-the-fly instead of storing everything in memory. For large datasets, generators save memory.

## Recursion

Recursion is when a function calls itself.

Recursion is a common mathematical and programming concept. It means that a function calls itself. This has the benefit of meaning that you can loop through data to reach a result.

The developer should be very careful with recursion as it can be quite easy to slip into writing a function which never terminates, or one that uses excess amounts of memory or processor power. However, when written correctly recursion can be a very efficient and mathematically elegant approach to programming.

<u>Example</u>:

A simple recursive function that counts down from 5:

```py
def countdown(n):
  if n <= 0:
    print("Done!")
  else:
    print(n)
    countdown(n - 1)

countdown(5)
```

### Base Case and Recursive Case

Every recursive function must have two parts:

- A **base case** --- A condition that stops the recursion
- A **recursive case** --- The function calling itself with a modified argument.

Without a base case, the function would call itself forever, causing a stack overflow error.

<u>Example</u>:

Identifying base case and recursive case:

```py
def factorial(n):
  # Base case
  if n == 0 or n == 1:
    return 1
  # Recursive case
  else:
    return n * factorial(n - 1)

print(factorial(5))
```

> [!IMPORTANT]
> The base case is crucial. Always make sure your recursive function has a condition that willl eventually be met.

### Recursion Depth Limit

Python has a limit on how deep recursion can go. The default limit is usually around 1000 recursive calls.

```py
import sys
print(sys.getrecursionlimit())
```

If you need deeper recursion, you can increase the limit, but be careful as this can cause crashes:

```py
import sys
sys.setrecursionlimit(2000)
print(sys.getrecursionlimit())
```

> [!WARNING]
> Increasing the recursion limit should be done with caution. For very deep recursion. consider using iteration instead.

---

# References

- Python Sets via [W3Schools](https://www.w3schools.com/python/python_sets.asp)
- Python --- Global Variables via [W3Schools](https://www.w3schools.com/python/python_variables_global.asp)
- Python `argparse` Module via [W3Schools](https://www.w3schools.com/python/ref_module_argparse.asp)
- Python --- unpacking via [Real Python](https://realpython.com/ref/glossary/unpacking/)
- Unpacking in Python, Simply Explained via [Ivan R | Medium.com](https://medium.com/@irbbb/unpacking-in-python-simply-explained-92dc53841ba0)
- Python --- *args and **kwargs via [W3Schools](https://www.w3schools.com/python/python_args_kwargs.asp)
- Python --- map() Function via [W3Schools](https://www.w3schools.com/python/ref_func_map.asp)
- List Comprehension in Python Explained for Beginners via [freeCodeCamp](https://www.freecodecamp.org/news/list-comprehension-in-python/)
- filter() via [Real Python](https://realpython.com/ref/builtin-functions/filter/)
- How the Python Lambda Function Works – Explained with Examples via [freeCodeCamp](https://www.freecodecamp.org/news/python-lambda-function-explained/)
- What is Dictionary Comprehension in Python? via [codecademy](https://www.codecademy.com/article/what-is-dictionary-comprehension-in-python)
- Python enumerate() Function via [W3Schools](https://www.w3schools.com/python/ref_func_enumerate.asp)
- Python Generators via [W3Schools](https://www.w3schools.com/python/python_generators.asp)
- Lecture 6: Functions & Recursion in Python | Python Full Course \[Urdu/Hindi] via [Shradha Khapra](https://www.youtube.com/watch?v=OvTH-7ESoRA)
- Python Recursion via [W3Schools](https://www.w3schools.com/python/python_recursion.asp)
