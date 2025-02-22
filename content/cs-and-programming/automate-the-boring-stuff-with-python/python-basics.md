---
draft: false
date: '2025-02-09T16:54:34+05:00'
title: 'Section 1: Python Basics'
linkTitle: 'Python Basics'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
---

Everyone in their life, spent a lot of time on repetitive tasks, which can be automated through a simple script.

Automate the boring stuff with Python uses **Python 3**.

## How to get help?

Being stuck while coding is a normal happening, but not asking for help isn't.

When you go online to ask for help, make sure:
- Explain what you are trying to do, not just what you did.
- If you get an error message, specify the point at which the error happens.
- Copy and paste the entire body of the error message and your code to a Pastebin site like [Pastebin.com](pastebin.com) or [GitHub Gist](gist.github.com).
- Explain what you've already tried to do to solve your problem.
- List the version of Python you're using.
- Say whether you're able to reproduce the error every time you run the program or whether it happens only after you perform certain actions. If the latter, then explain what those actions are.
- Specify what Operating System you're on, what version of that OS you're using.

## Basic Terminology and using an IDLE

IDLE stands for Integrated Development and Learning Environment.

There are different programming text editors available:
- Visual Studio Code
- Sublime Text
- PyCharm

- Expressions = Values + Operators

In python, these expressions always evaluate to a single result. Arithmetic Operators are:

| **Operator** | **Operation**                     | **Example** | **Evaluates to . . .** |
| ------------ | --------------------------------- | ----------- | ---------------------- |
| **           | Exponent                          | 2 ** 3      | 8                      |
| %            | Modulus/remainder                 | 22 % 8      | 6                      |
| //           | Integer division/floored quotient | 22 // 8     | 2                      |
| /            | Division                          | 22 / 8      | 2.75                   |
| *            | Multiplication                    | 3 * 5       | 15                     |
| -            | Subtraction                       | 5 - 2       | 3                      |
| +            | Addition                          | 2 + 2       | 4                      |

### Data Types

- Integers --- “ints” (1,2,3…)
- Floating point --- “floats” (1.0, 1.1...)
- Strings ("Hello World")
    - **Strings Concatenation**: When two strings are joined together using a `+` symbol. ("Hello " + "World")
    - **String Replication**: A string can be replicated by using `*` operator. (3 * "Hello World!")
    - Both These operations can be combined like this `"Hello World" + "!" * 5`
    - Both concatenation and replication accepts **strings values** only.

### Variables

Variable can store different values, like a box:

<div style='text-align: center;'> spam = 42 </div>

![](/notes/automate-the-boring-stuff-with-python/python-basics.webp)

A too generic name given to a variable is a bad practice, which can create headache down the line while interacting with your code.

![](/notes/automate-the-boring-stuff-with-python/python-basics-1.webp)

- If a python instruction evaluates to a single value, it's called an **expression**.
- If it doesn't evaluate to a single value, it's called a **statement**.

We can update the variable value by calling it down the line in the program:

```python
>>> spam = 'Hello'  
>>> spam  
'Hello'  
>>> spam = 'Goodbye'  
>>> spam  
'Goodbye'
```

Just like the box, we can remove the old item with the new one.

![](/notes/automate-the-boring-stuff-with-python/python-basics-2.webp)

### Variable Names

You can name your variable anything, but Python does have some restrictions too:
- It can be only one word with no spaces.
- It can use only letters, numbers, and the underscores (_) character.
- It can't begin with a number.
- Var names are case-sensitive too.

Though `Spam` is a valid var, but it is a Python convention to start var name with a lowercase letter.

**camelCase** for variables can be used though **Python PEP8** style guide instead recommends the use of underscores like this **camel_case**.

Though PEP8 guide itself says:
> Consistency with the style guide is important. But most importantly: know when to be inconsistent—sometimes the style guide just doesn’t apply. When in doubt, use your best judgment.

## Writing Our First Program

- Python ignore comments starting with `#`.
- It also skips the blank lines.
- **Functions** — They are like mini-programs in Python.

```python {title = "hello.py"}
print("Hello World!")

# Ask for their name
yourName = input("Type your name: ")
print("It is good to meet you, " + str(yourName))
print("Your name length is: " + str(len(yourName)))

# Ask for their age
print("What is your age?")
yourAge = input("Type your age: ")
print("You will be " + str(int(yourAge) + 1) + " in a year.")
```

- **len()**: It prints out the total number of characters in a string.
- **input()** function always returns a string value, so you may have to convert it according to your need to **float()**, **int()** etc.
- You can not concatenate **str()** and **int()** together, you will need to convert **int()** to **str(int())**, to concatenate them.

`hello.py` Evaluation steps look like this:

![](/notes/automate-the-boring-stuff-with-python/python-basics-3.webp)

## Extras (BOOK)

### Python `round(number, ndigits=None)` Function

Return number rounded to ndigits precision after the decimal point. If ndigits is omitted or is `None`, it returns the nearest integer to its input.

```python
>>> round(23)  
23  
>>> round(23.0)  
23  
>>> round(23.3)  
23  
>>> round(23.345)  
23  
>>> round(23.5)  
24  
>>> round(23.49)  
23
>>> round(32.35, 1)  
32.4  
>>> round(32.355, 2)  
32.35
```

> [!INFO]
>
> The behavior of [`round()`](https://docs.python.org/3/library/functions.html#round "round") for floats can be surprising: for example, `round(2.675, 2)` gives `2.67` instead of the expected `2.68`. This is not a bug: it’s a result of the fact that most decimal fractions can’t be represented exactly as a float. See [Floating-Point Arithmetic: Issues and Limitations](https://docs.python.org/3/tutorial/floatingpoint.html#tut-fp-issues) for more information.