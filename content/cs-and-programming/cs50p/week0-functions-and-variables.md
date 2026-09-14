---
draft: false
date: "2025-02-09T15:47:28+05:00"
title: "Week 0: Functions and Variables"
linkTitle: "Functions and Variables"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
---

| Week 0: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week0-functions) |
| :-------------------: | :--------------------------------------------------------------------------------------: |

## Functions

A small program that allows you to perform some action in the desired Computer Programming Language.

```py
print("Hello, World!")
```

When run, the following text will be printed on the screen:

```text
Hello, World!
```

**The text printed on the screen is termed as a <u>Side Effect</u>. It's the side effect of running the function with the pre-determined input.**

The built-in function `print` allows you to output some text to the screen in Python.

- You can change the underlying implementation of function as long as name and parameters remains same, nobody running the program will notice.

## Bugs

An error/mistake in the code which stops the program from running normally.

- You make mistake while writing the code.
- You may forgot to close parenthesis, or forgot to close a quotation marks, or use some illegal (in-terms of programming of-course) input.

## Comments

A note to yourself about the function of your code, so you don't forget in the future, what's really happening with your code.

```py
# This code prints "Hello, World!" on the screen
print("Hello, World!")
```

If it's a complex function, a comment will immediately remind you what's this piece of code is actually doing inside the program.

## Pseudocode

A plain statement in any human language which methodically and simply outlines what you want to build in the desired programming language. A comment starts with `#` symbol which tells the interpreter to ignore what comes after it.

```text
# A program that asks for user name as an input
# It takes that input, and prints Hello to that user
```

Above lines are simply a pseudocode which explains the outcome we need from the actual code.

- No coding involved on this stage.
- Only plan english is used to list down the desired outcomes.
- It can act as a TODO list inside your code.
- It helps break down complex programs into simple workable chunks.

## Parameters

Following are the types of parameters.

### Positional Parameters

> A parameter passed to the function will be printed at a position it's on i.e., first, seconds etc.

```py
print("Hello,", name)
```

First positional parameter is "Hello,", will be printed first. The name variable is a second positional parameter, printed second.

### Named Parameters

> A named parameter is a built-in optional argument of the given function which is usually provided after the positional parameters.

```py
print("Hello,", name, sep='?' )
#OR
print("Hello,", end="")
print(name)
```

Both `sep=' '` and `end="\n"` (with defaults) are the Named parameters provided by the `print` function.

## Strings `str`

An immutable sequences of Unicode characters used to store and manipulate textual data.

- In Python, anything inside `''` or `""` is called a string.
- The function `input()` only accepts string arguments.

### Python f-string

A special of type string that provides a concise and efficient way to embed expressions inside string literals.

```py
print(f'Hello, {name}')
```

### Strings Methods

> Python string methods are built-in functions attached to string objects that allow for text manipulation, such as changing case, searching, replacing, splitting, and formatting.

Because strings in Python are immutable, these methods don't modify the original string; instead, they return a new string with the requested changes applied.

#### `str.strip()` method

Remove whitespace from around the strings:

```py
str.strip()
```

#### `str.capitalize()` method

Change the first letter of the string to upper case.

```py
str.capitalize()
```

#### `str.title()` method

Capitalize the first letter of all the words in the given string.

```py
str.title()
```

#### `str.join()` method

> The `join()` method takes all items in an iterable and joins them into one string. -- W3School

Syntax = `string.join(iterable)

```py
myDict = {"name": "John", "country": "Norway"}
mySeparator = "TEST"

x = mySeparator.join(myDict)
# OR separator string can be mentioned directly
x = ','.join(myDict)
print(x)
```

> [!NOTE]
> When using a dictionary as an iterable, the returned values are the keys, not the values.

### String Slicing

You can return a range of characters by using the slice syntax

Specify the start index and the end index, separated by a colon, to return a part of the string.

Example:

```py
greet = "Hello, World!"
```

#### Slice From the Start

Get the characters from the start to position 5:

```py
print(greet[0:5])
#OR
print(greet[:5])
```

When starting from index `0`, we don't need to mention it. The character at index `[5]` will not be included.

#### Slice From the End

By leaving out the end index, the range will go to the end:

```py
print(greet[2:])
```

If we want to slice the last 6 characters:

```py
print(greet[-6:])
```

## Python Interactive Mode

The live Python interpreter, where you can write code and get the execution immediately, unlike you write your code in a file and then run that file with Python interpreter.

It removes the friction for some quick Python practice.

## Integers `int()`

Integers are whole numbers without a decimal point i.e., -3, -2, -1, 0, 1, 2, 3 etc.

- In programming, ideal for counting or indexing

## Floats `float()`

Floats (floating-point numbers) represent real numbers with decimal components.

- Ideal for a wider range of values and fractional precision, making them suitable for measurements and continuous data.

## Function `def()`

A small reusable piece of program which can be defined once and used multiple times inside the code to reduce repeatability and increase the readability.

```py
# All the code resides in the main
def main():
    return

# Define as many functions as you want
def func():
   return

# Call main() to start the execution
main()
```

Running without calling on the `main()` function, no execution will happen, as our main code resides in the main function and nobody calling it, when we call on the `main()` function, then the execution starts, and the rest of the user functions will also be executed one by one as they appear in the `main()`.

### Variable Scope

The variable only exists in the scope where you defined it.

- Variable defined inside the function, cannot be called on globally.
- Variable defined in the 2nd user function cannot be called in the first one.
