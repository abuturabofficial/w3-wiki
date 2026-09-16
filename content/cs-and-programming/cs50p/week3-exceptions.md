---
draft: false
date: "2026-09-16T08:35:18+05:00"
title: "Week 3: Exceptions"
linkTitle: "Exceptions"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 4
---

| Week 3: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week3-exceptions) |
| :-------------------: | :---------------------------------------------------------------------------------------: |

## Python Exceptions

> Exceptions are the problems in the Python or any other programming language code, that the programmer has to solve.

### SyntaxError

> A SyntaxError in Python occurs when code violates the grammatical rules of the language, making it impossible for the interpreter to parse and understand the structure. ---TutorialsPoint.com

Common causes include:

- Missing punctuation
- Incorrect indentation
- Misspelled keywords
- Invalid string delimiters, such as mixing single and double quotes improperly

### Value Error

> A ValueError in Python is a built-in exception raised when a function or operation receives an argument of the correct data type but an inappropriate or invalid value. ---RealPython.com

Unlike a TypeError, which occurs when the wrong data type is provided, a ValueError indicates that while the input is the right kind of object, its specific content is unsuitable for the operating being performed.

Common scenarios that trigger a ValueError include:

- **Invalid Type Conversion:** Attempting to convert a string that doesn't represent a valid number into an integer or float
- **Mathematical Constraints:** Performing an operation that requires a specific range of values, such as taking the square root of a negative number or calculating the factorial of a negative integer
- **List Operations:** Trying to remove a value from a list that doesn't exist within it.
- **Unpacking Mismatches:** Attempting to unpack a list or iterable into a different number of variables than there are items

### NameError

> The NameError exception occurs if you use a variable that is not defined. ---W3School

You can handle the `NameError` in a `try..except` statement.

## `try` and `except`

The `try` block lets you test a block of code for error.

The `except` block lets you handle the error.

The `else` block lets you execute code when there is no error.

The `finally` block lets you execute code, regardless of the result of the try and except blocks.

The `raise` keyword is used to raise an exception.

Let's see a code:

```py
try:
    x = int(input("What's the value of x: "))
except ValueError:
    print("x is not an integer.")
else:
    print(f"The value of x is: {x}")
```

The `else` part will only be executed if there are no error.

If you don't want to print anything in the `except` block write `pass`, it will not raise/print anything to the user.

### MemoryError

> In Python, a MemoryError is a built-in exception that occurs when the interpreter cannot allocate enough memory for an operation, such as creating a large list, loading a huge file, or executing a recursive function without a base case.

This error signals that the program has attempted to use more memory (RAM or virtual address space) that the system can provide.

Common causes include:

- **Unbounded Data Growth:** Accumulating data in lists or dictionaries within infinite or large loops.
- **Large Object Allocation:** Attempting to create data structures (like NumPy arrays or Pandas DataFrames) that exceed available system memory.
- **Excessive Recursion:** Recursive functions that consume excessive stack space before hitting the recursion limit.
- **Memory Leaks:** Although less common as a direct cause, failing to release references to large objects can lead to exhaustion.

### KeyError

> A KeyError is an exception raised when you try to access a value in a dictionary (or other mapping) using a key that doesn't exist within that collection.

It is a subclass of LookupError and serves as Python's signal that the requested key cannot be found among existing keys.

### Raise an Exception

As a programmer, you can choose to throw an exception if a condition occurs.

To throw an exception, use the `raise` keyword.

```py
x = -1
if x < 0:
    raise Exception("Sorry, no numbers below zero")
```

You can define what kind of error to raise, and the text to print to the user.

```py
x = "hello"
if not type(x) is int:
    raise TypeError("Only integers are allowed")
```

## Debugging

> Debugging is the process of identifying, analyzing, and resolving errors or bugs in code to ensure it runs correctly and produces expected results.

It involves detecting syntax errors (structural issues like typos) and semantic errors (logical issues where code runs but yields incorrect outputs).

The primary goal is to locate the root cause of unexpected behavior by examining the program's state during execution. This is achieved through various techniques, including:

- **Using Tracebacks:** Analyzing error messages to pinpoint where exceptions occur.
- **Print Statements:** Inserting `print()` calls to track variable values and code flow.
- **BreakPoints:** Pausing execution at specific lines to inspect variables and state.
- **Debuggers:** Using tools like built-in `pdb` module or IDE debuggers (e.g., in Zed or VS Code) to step through code line-by-line and interactively inspect the execution environment.
