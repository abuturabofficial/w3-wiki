---
draft: false
date: '2025-02-14T17:57:31+05:00'
title: 'Section 4: Handling Errors With Try/Except'
linkTitle: 'Handling Errors With Try/Except'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 4
---

## Exception Handling

Getting an error or exception in Python program, without any exception handling means entire program will crash.

In real world, this is not the desired behavior, and we want our program to detect errors, handle them, and then continue to run.

```python {linenos=on, hl_lines=[6]}
def spam(divideBy):  
    return 42 / divideBy  
  
print(spam(2))  
print(spam(12))  
print(spam(0))  
print(spam(1))
```

When the program is run we will get `ZeroDivisonError` at **line 6**.

You can put the previous divide-by-zero code in a `try` clause and have an `except` clause contain code to handle what happens when this error occurs.

```python {linenos=on}
def spam(divideBy):
    try:
        return 42 / divideBy
    except ZeroDivisionError:
        return ('Error: I cannot do that.')


print(spam(2))
print(spam(12))
print(spam(0))
print(spam(1))
```

When code in a `try` clause causes an error, the program execution immediately moves to the code in the `except` clause. After running that code, the execution continues as normal.

## **A Short Program: Zigzag**

This program will create a back-and-forth, zigzag pattern until the user stops it by pressing the Mu editor’s Stop button or by pressing <kbd>CTRL-C</kbd>. When you run this program, the output will look something like this:

```python
    ********  
   ********  
  ********  
 ********  
********  
 ********  
  ********  
   ********  
    ********
```

This is how I implemented:

```python {title=zigZag2.py, linenos=on}
# An extra project from book's chapter 3
import sys
import time
def asterisks_pattern(startSpace, pattern):
    print(' ' * startSpace + pattern)
    time.sleep(0.1)
pattern = '******'

while True:
    try:
        for startSpace in range(10):
            asterisks_pattern(startSpace, pattern)

        for startSpace in range(10, 1, -1):
            asterisks_pattern(startSpace, pattern)
    except KeyboardInterrupt:
        print(' Quiting the animation pattern. Goodbye!')
        sys.exit()
```

Here is [Al's implementation](https://github.com/abuturabofficial/python-automation-pg/blob/main/section-4_handling_errors/zigZag_al.py)

## **_The Collatz Sequence_**

Write a function named `collatz()` that has one parameter named number. If number is even, then `collatz()` should print `number // 2` and return this value. If number is odd, then `collatz()` should print and `return 3 * number + 1`.

Then write a program that lets the user type in an integer and that keeps calling `collatz()` on that number until the function returns the value 1. (Amazingly enough, this sequence actually works for any integer—sooner or later, using this sequence, you’ll arrive at 1! Even mathematicians aren’t sure why. Your program is exploring what’s called the _Collatz sequence_, sometimes called “the simplest impossible math problem.”)

Remember to convert the return value from `input()` to an integer with the `int()` function; otherwise, it will be a string value.

Hint: An integer number is even if `number % 2 == 0`, and it’s odd if `number % 2 == 1`.

The output of this program could look something like this:

```python
Enter number:  
3  
10  
5  
16  
8  
4  
2  
1
```

```python {title="collatzSeq_extras.py", linenos=on}
# Extra Project from book's chapter 3
def collatz(number):
    if number % 2 == 0:
        result = int(number / 2)
    else:
        result = int(3 * number + 1)
    print(result)
    return result


try:
    number = int(input("Enter your number:\n"))
    while number != 1:
        number = collatz(number)
except ValueError:
    print('Please enter a valid integer')
```