---
draft: false
date: '2025-02-09T15:47:28+05:00'
title: 'Week 0 - Functions and Variables'
linkTitle: 'Functions'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight:  1
---

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

A plain statement which methodically and simply outlines what you want to build in the desired programming language. A comment starts with `#` symbol which tells the interpreter to ignore what comes after it.

```text
# A program that asks for user name as an input
# It takes that input, and prints Hello to that user
```

Above lines are simply a pseudocode which explains the outcome we need from the actual code.
- No coding involved on this stage.
- Only plan english is used to list down the desired outcomes.
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

## Strings

An immutable sequences of Unicode characters used to store and manipulate textual data.
- In Python, anything inside `''` or `""` is called a string.
- The function `input()` only accepts string arguments.

### Python f-string

A special of type string that provides a concise and efficient way to embed expressions inside string literals.

```py
print(f'Hello, {name}')
```

### Strings Methods

#### `strip()` function

Remove whitespace from around the strings:

```py
str.strip()
```

#### `capitalize()` function

Change the first letter of the string to upper case.

```py
str.capitalize()
```

#### `title()` function

Capitalize the first letter of all the words in the given string.

```py
str.title()
```