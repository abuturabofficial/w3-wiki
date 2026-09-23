---
draft: false
date: "2026-09-22T07:14:47+05:00"
title: "Week 5: Unit Tests"
linkTitle: "Unit Tests"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 6
---

| Week 5: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week5-unit-tests) |
| :-------------------: | :---------------------------------------------------------------------------------------: |

## Unit Tests

> Unit testing is a software testing technique in which individual components or units of a software application are tested independently from the rest of the application. ---freeCodeCamp.org

### `assert`

The `assert` keyword is used when debugging code.

The `assert` keyword lets you test if a condition in your code returns True, if not, the program will raise an **AssertionError**.

You can write a message to be written if the code returns **False**:

```py
x = "welcome"
#if condition returns False, AssertionError is raised:
assert x != "welcome", "x should not be 'welcome'"
```

## `pytest` module

> The `pytest` is popular testing framework for Python that makes it easy to write and run tests. Unlike `unittest`, pytest's simple syntax allows developers to write tests directly as functions or within classes. This lets you write clean, readable code without complexities. ---freeCodecCamp.org

The benefits of using `pytest` ([REF: freeCodeCamp](https://www.freecodecamp.org/news/how-to-use-pytest-a-guide-to-testing-in-python/)):

- **Flexibility**: It provides flexibility in test structure by supporting tests for functions, classes, and modules.
- **Detailed test output**: It provides a detailed and readable test output, making it easy to understand test failures and errors.
- **Automatic test discovery**: It automatically discovers tests by looking for files that start with "`test_`" or end with "`_test.py`". This eliminates the need for manually specifying test files.
- **Parameterization**: It supports parameterized tests, which allow you to run a single test functions with multiple sets of inputs.
- **Fixtures**: It provide `setup` and `tearDown` methods that help prevent code repetition. This enables you to set up baseline conditions for your tests and also delete them after each test.
- **Plugins and extension**: It has a rich set of plugins and extensions to add extra functionalities.
- **Compatibility**: It's compatible with other testing frameworks like `unittest`, allowing you to migrate tests from different testing frameworks and run them seamlessly on it.

> [!INFO]
> Unit tests cannot run on the function which doesn't return any value, and just prints something (side effect). So, it's always a good idea to return values in the functions instead of the side effects(text printed on the screen).

### Tests Folder

Make folder name test inside your project directory:

```sh
mkdir test
```

Create an empty file named `__init__.py`:

```sh
touch __init__.py
```

Create the test files like `test_[PROGRAM-NAME]` inside the test folder.

An empty `__init__.py` will tell the `pytest` module that `test/` is a package. A `package` is a python module or multiple modules organized inside a folder.

Now run the `pytest` module on the whole folder:

```sh
pytest test/
```

> [!NOTE]
> Each function name inside `test_name.py` must be prefixed with the word `test_` for pytest to discover and run these tests automatically.
>
> ```py
>  def test_addition():
>      assert 1 + 1 == 2
> ```

### Raise an Error

If your function raises an error like **ZeroDivisionError** when some condition is met, you want to make sure your unit test, catches that:

```py
import pytest

def test_zero_division:
    with pytest.raises(ZeroDivisionError):
        my_func(1/0)
```

Here `my_func()` should raise a `ZeroDivisionError` and crash the unit test, but `with pytest.raises(ZeroDivisionError)` tells pytest, "I expect this block of code to through exactly this error".

This test only passes if this error actually happens when `my_func(1/0)` runs, if no error occurs, the test fails.

So, it confirms, the `my_func()` correctly propagates the error instead of silently failing and returning something wrong.