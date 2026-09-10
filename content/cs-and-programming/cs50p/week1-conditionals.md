---
draft: false
date: "2026-09-09T10:24:13+05:00"
title: "Week 1: Conditionals"
linkTitle: "Conditionals"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 2
---

| Week 1: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week1-conditionals) |
| :-------------------: | :-----------------------------------------------------------------------------------------: |

## Conditionals

Ability to ask questions and answer those questions, in order to decide which line of code will be executed.

- To write conditional statements in Python, we can use `if` statement.
- The `elif` statement, ask a question, taking into account whether or not a previous question had a true or false answer.
- The `else` statement, used when the all the other options has bee exhausted and only logical answer is the last one. So, we don't need to compare anything for it, because it's the only answer left. It's catch all statement, if everything else isn't proved right, let's assume this is the answer.

Some symbols used in Python, are:

| Symbol |      Representation      |
| :----: | :----------------------: |
|   >    |       Greater than       |
|   >=   | Greater than or Equal to |
|   <    |        Less than         |
|   <=   |  Less than or Equal to   |
|   ==   |         Equal to         |
|   !=   |       Not equal to       |

**Not better design** (See `compare.py`)
![](/notes/cs50p/week1-conditionals-1.webp)

**A better designed program:**
![](/notes/cs50p/week1-conditionals-2.webp)

**The final design:**
![](/notes/cs50p/week1-conditionals-3.webp)

- In the first version, program goes through all the code despite finding the correction answer earlier.
- In the second iteration, program will immediately terminate as it gets its answer.

### Boolean Expression

A question that gives Yes or No answer, or simply True or False answer.

`OR` Returns True if at least one operand is `True`; it only returns `False` if both operands are false.

`AND` Returns `True` if both operands are true; otherwise, it returns `False`. It's uses short-circuit evaluation, meaning if the first operand is false, the second is not evaluated.

## Python Operators

| Operator |     Meaning     |
| :------: | :-------------: |
|    +     |    Addition     |
|    -     |  Substraction   |
|    *     | Multiplication  |
|    **    | Exponentiation  |
|    /     |    Division     |
|    %     | Modulo operator |

## `match`...`case` Statement

Provides structural pattern matching as a more readable and powerful alternative to `if-elif-else` chains. It evaluates an expression against successive patterns and executes the corresponding code block for the first match.

```py
match name:
    case 'Harry':
        print('Gryffindor')
    case 'Hermione':
        print('Gryffindor')
    case 'Ron':
        print('Gryffindor')
    case 'Draco':
        print('Slytherin')
    case _: # Handle edge cases
        print('Who?')
```

More legible or better version:
```py
match name:
  case 'Harry' | 'Hermione' | 'Ron':
    print('Gryffindor')
  case 'Draco':
    print('Slytherin')
  case _:
    print('Who?')
```