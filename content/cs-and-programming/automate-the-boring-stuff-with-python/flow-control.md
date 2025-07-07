---
draft: false
date: '2025-02-11T10:47:23+05:00'
title: 'Section 2: Flow Control'
linkTitle: 'Flow Control'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 2
---

## Flow Charts and Basic Flow Control Concepts

A flowchart starts at the start box, and you follow the arrow at the other boxes until you reach the end box. You take a different path depending on the conditions.

Based on how expression evaluate, a program can decide to skip instructions, repeat them, or choose one of several instructions to run. In fact, you almost never want your programs to start from the first line of ode and simply execute every line, straight to the end.

Flow control statements can decide which Python instructions to execute under which conditions.

These flow control statements directly correspond to the symbols in a flowchart.

![](/notes/automate-the-boring-stuff-with-python/flow-control.webp)

In a flowchart, there is usually more than one way to go from the start to the end. The same is true for lines of code in a computer program. Flowcharts represent these branching points with diamonds, while the other steps are represented with rectangles. The starting and ending steps are represented with rounded rectangles.

### Boolean Values

Boolean Data Type has only to values **True** and **False**.

How to represent **YES and NO** values:
- Boolean Values
- Comparison Operators
- Boolean Operators
- When entered as Python code, the Boolean always starts with a capital **T** or **F**, with the rest of the word in lowercase.

(Boolean is capitalized because the data type is named after mathematician **George Boole**)

```python
➊ >>> spam = True  
   >>> spam  
   True  
➋ >>> true  
   Traceback (most recent call last):  
     File "<pyshell#2>", line 1, in <module>  
       true  
   NameError: name 'true' is not defined  
➌ >>> True = 2 + 2  
   SyntaxError: can't assign to keyword
```

Like any other value, Boolean values are used in expressions and can be stored in variables ➊. If you don't use the proper case ➋ or you try to use _True_ and _False_ for variable names ➌, Python will give you an error message.

### Comparison Operators

They also called **relational operators**, compare two values and evaluate down to a single Boolean value.

| **Operator** | **Meaning**              |
| ------------ | ------------------------ |
| ==           | Equal to                 |
| !=           | Not equal to             |
| <            | Less than                |
| >            | Greater than             |
| <=           | Less than or equal to    |
| >=           | Greater than or equal to |

- These operators evaluate to **True** or **False** depending on the values you give them.
- The `==` and `!=` operators can actually work with values of any data type.

```python
>>> 'hello' == 'hello'  
   True  
   >>> 'hello' == 'Hello'  
   False  
   >>> 'dog' != 'cat'  
   True  
   >>> True == True  
   True  
   >>> True != False  
   True  
   >>> 42 == 42.0  
   True  
➊ >>> 42 == '42'  
   False
```

An integer or floating point value will always be unequal to a string value. There `42 == '42'`➊ evaluates to **False** because Python considers the integer 42 to be different from the string `'42'`.

The <, >, <=, and >= operators, on the other hand, work properly only with integer and floating-point values.

### Boolean Operators

The three Boolean operators (`and`, `or`, and `not`) are used to compare Boolean values. Like comparison operators, they evaluate these expressions down to a Boolean value.

### Binary Boolean Operators

The `and` and `or` operators always take two Boolean values (or expressions), so they're considered binary operators.

**`and` Operator**: It evaluates to **True** only if both Boolean values are True.

| **Expression**  | **Evaluates to...** | 
| --------------- | ------------------- |
| True and True   | True                |
| True and False  | False               |
| False and True  | False               |
| False and False | False               |

**`or` Operator**: It evaluates to **True** if one of the Boolean values is True.

| **Expression** | **Evaluates to...** | 
| -------------- | ------------------- |
| True or True   | True                |
| True or False  | True                |
| False or True  | True                |
| False or False | False               |

### The `not` Operator

It has only one Boolean value (or expression)

| **Expression** | **Evaluates to...** | 
| -------------- | ------------------- |
| not True       | False               |
| not False      | True                |

### Mixing Boolean and Comparison Operators

Since the comparison operators evaluate to Boolean values, you can use them in expressions with the Boolean operators.

```python
>>> (4 < 5) and (5 < 6)  
True  
>>> (4 < 5) and (9 < 6)  
False  
>>> (1 == 2) or (2 == 2)  
True
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-1.webp)

You can also use multiple Boolean operators in an expression, along with the comparison operators:

```python
>>> 2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2  
True
```

The Boolean operators have an order of operations just like the math operators do. After any math and comparison operators evaluate, Python evaluates the `not` operators first, then the `and` operators, and then the `or` operators.


### Elements of Flow Control

Flow control statements often start with a part called the condition and are always followed by a block of code called the **clause**.

#### Conditions

The Boolean expressions you've seen so far could all be considered conditions, which are the same thing as expressions; condition is just a more specific name in the context of flow control statements.

Conditions always evaluate down to a **Boolean value**, **True** or **False**. A **flow control statement** decides what to do based on whether its condition is **True** or **False**, and almost every flow control statement uses a condition.

#### Blocks of Code

Lines of Python code can be grouped together in blocks.

There are 3 rules for block:
1. Blocks begin when the indentation increases.
2. Blocks can contain other blocks.
3. Blocks end when the indentation decreases to zero or to a containing block's indentation.

```python
  name = 'Mary'  
  password = 'swordfish'  
  if name == 'Mary':  
    ➊ print('Hello, Mary')  
       if password == 'swordfish':  
        ➋ print('Access granted.')  
       else:  
        ➌ print('Wrong password.')
```

You can view the execution of this program at _[https://autbor.com/blocks/](https://autbor.com/blocks/)_. The first block of code ➊ starts at the line print('Hello, Mary') and contains all the lines after it. Inside this block is another block ➋, which has only a single line in it: print('Access Granted.'). The third block ➌ is also one line long: print('Wrong password.').

## If, Else, and Elif Statements

The statements represent the diamonds in the flowchart. They are the actual decisions your programs will make.

### `if` Statements

If this condition is true, execute the code in the clause. `if` statement, consists of the following:
- The `if` keyword
- A condition (that is, an expression that evaluates to **True** or **False**)
- A colon
- Starting on the next line, an indented block of code (called the `if` clause)

![](/notes/automate-the-boring-stuff-with-python/flow-control-2.webp)


### `else` Statements

> An `if` clause can optionally be followed by an else statement. The else clause is executed only when the **if statement’s condition is False**.

An `else` statement doesn't have a condition. In code, an else statement always consists of the following:
- The `else` keyword
- A colon
- Starting on the next line, an indented block of code (called the `else` clause)

![](/notes/automate-the-boring-stuff-with-python/flow-control-3.webp)

### `elif` Statements

While only one of the if or else clauses will execute, you may have a case where you want one of _many_ possible clauses to execute.

> The **elif statement** is an “else if” statement that always follows an if or another elif statement. It provides another condition that is checked only if all the previous conditions were False.

In code, an elif statement always consists of the following:
- The `elif` keyword
- A condition (that is, an expression that evaluates to `True` or `False`)
- A colon
- Starting on the next line, an indented block of code (called the `elif` clause)

```python
if name == 'Alice':  
    print('Hi, Alice.')  
elif age < 12:  
    print('You are not Alice, kiddo.')
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-4.webp)

The elif clause executes if `age < 12` is `True` and `name == 'Alice'` is `False`. However, if both of the conditions are `False`, then both of the clauses are skipped. It is _not_ guaranteed that at least one of the clauses will be executed. When there is a chain of elif statements, **only one or none** of the clauses will be executed. Once one of the statements’ conditions is found to be `True`, the rest of the elif clauses are automatically skipped.

```python {title="vampire.py"}
name = 'Carol'
age = 3000
if name == 'Alice':
    print('Hi, Alice.')
elif age < 12:
    print('You are not Alice, kiddo.')
elif age > 2000:
    print('Unlike you, Alice is not an undead, immortal vampire.')
elif age > 100:
    print('You are not Alice, grannie.')
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-5.webp)

- The program `vampire.py` has 3 elif statements. If any of the three, is found `True` program execution will stop.
- The order of `elif` statements is also important.
- Optionally, you can have an `else` statement after the last `elif` statement. In that case, it _is_ guaranteed that at least one (and only one) of the clauses will be executed. If the conditions in every `if` and `elif` statement are `False`, then the `else` clause is executed. 

For example, let’s re-create the Alice program to use if, elif, and else clauses.

```python{title="littlekid.py"}
age = 3000  
if name == 'Alice':  
    print('Hi, Alice.')  
elif age < 12:  
    print('You are not Alice, kiddo.')  
else:  
    print('You are neither Alice nor a little kid.')
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-6.webp)

When you use `if`, `elif`, and `else` statements together, remember these rules about how to order them to avoid bugs like the one in Figure 2.7. First, there is always exactly one `if` statement. Any `elif` statements you need should follow the `if` statement. Second, if you want to be sure that at least one clause is executed, close the structure with an else statement.

```python {title="vampire2.py"}
name = 'Carol'  
age = 3000  
if name == 'Alice':  
   print('Hi, Alice.')  
elif age < 12:  
   print('You are not Alice, kiddo.')  
elif age > 100:  
   print('You are not Alice, grannie.')  
elif age > 2000:  
   print('Unlike you, Alice is not an undead, immortal vampire.')
```

{{< figure 
    src="/notes/automate-the-boring-stuff-with-python/flow-control-7.png" 
    caption="**Figure 2-7**: The flowchart for the *vampire2.py* program. The X path will logically never happen, because if age were greater than 2000, it would have already been greater than 100."
>}}

## While Loops

The `while` statement always consists of the following:
- The `while` keyword
- A condition (that is, an expression that evaluates to `True` or `False`)
- A colon
- Starting on the next line, an indented block of code (called the `while` **clause**)

You can see that a `while` statement looks similar to an `if` statement. The difference is in how they behave. At the end of an `if` **clause**, the program execution continues after the `if` statement. But at the end of a `while` **clause**, the program execution jumps back to the start of the `while` statement. The **while clause** is often called the **_while loop_** or just the _loop_.

The code with `if` statement:

```python
spam = 0  
if spam < 5:  
    print('Hello, world.')  
    spam = spam + 1
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-8.webp)

The code with `while` statement:

```python
spam = 0
while spam < 5:
    print("Hello, world!")
    spam = spam + 1
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-9.webp)

### An Annoying while Loop

Here is the code, which will keep asking your name until you literally type `your name` in the prompt:

```python {title="yourName.py"}
name = ""
while name != 'your name':
    print("Please type your name.")
    name = input()
print("Thank you!")
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-10.webp)

### `break` Statements

If the execution reaches a `break` statement, it immediately exits the `while` loop's clause.

```python {title=yourName2.py}
➊ while True:  
       print('Please type your name.')  
    ➋ name = input()  
    ➌ if name == 'your name':  
        ➍ break  
➎ print('Thank you!')
```

The first line ➊ creates an _infinite loop_; it is a while loop whose condition is always True. (The expression True, after all, always evaluates down to the value True.) After the program execution enters this loop, it will exit the loop only when a break statement is executed. (An infinite loop that _never_ exits is a common programming bug.)

Just like before, this program asks the user to enter your name ➋. Now, however, while the execution is still inside the while loop, an if statement checks ➌ whether name is equal to 'your name'. If this condition is True, the break statement is run ➍, and the execution moves out of the loop to print('Thank you!') ➎. Otherwise, the if statement’s clause that contains the break statement is skipped, which puts the execution at the end of the while loop. At this point, the program execution jumps back to the start of the while statement ➊ to recheck the condition.

![](/notes/automate-the-boring-stuff-with-python/flow-control-11.webp)

### `continue` Statements

- `continue` Statements are used inside loops
- When the program execution reaches a `continue` statement, the program execution immediately jumps back to the start of the loop and re-evaluates the loop's condition (This is also what happens when the execution reaches the end of the loop).

```python {title="swordfish.py"}
  while True:  
      print('Who are you?')  
      name = input()  
    ➊ if name != 'Joe':  
        ➋ continue  
       print('Hello, Joe. What is the password? (It is a fish.)')  
    ➌ password = input()  
       if password == 'swordfish':  
        ➍ break  
➎ print('Access granted.')
```

If the user enters any name besides Joe ➊, the `continue` statement ➋ causes the program execution to jump back to the start of the loop. When the program reevaluates the condition, the execution will always enter the loop, since the condition is simply the value `True`. Once the user makes it past that `if` statement, they are asked for a password ➌. If the password entered is **swordfish**, then the `break` statement ➍ is run, and the execution jumps out of the while loop to print **Access granted** ➎. Otherwise, the execution continues to the end of the while loop, where it then jumps back to the start of the loop.

![](/notes/automate-the-boring-stuff-with-python/flow-control-12.webp)

> [!INFO]- **Truthy** and **Fasely** Values
> Conditions will consider some values in other data types equivalent to True and False. When used in conditions, 0, 0.0, and '' (the empty string) are considered False, while all other values are considered True. For example, look at the following program:
> ```python
> name = ''
> # `not` is a Boolean operator which flips the `True` or `False` values
> ➊ while not name:  
>     print('Enter your name:')  
>     name = input()  
> print('How many guests will you have?')  
> numOfGuests = int(input())  
> ➋ if numOfGuests:  
>     ➌ print('Be sure to have enough room for all your guests.')  
> print('Done')
> ```
> If the user enters a blank string for name, then the while statement’s condition will be `True` ➊, and the program continues to ask for a name. If the value for numOfGuests is not 0 ➋, then the condition is considered to be True, and the program will print a reminder for the user ➌.
>
> You could have entered not name != '' instead of not name, and numOfGuests != 0 instead of numOfGuests, but using the truthy and falsey values can make your code easier to read.

## For Loops

The `while` loop keeps looping while its condition is `True` (which is the reason for its name), but what if you want to execute a block of code only a certain number of times? You can do this with a `for` loop statement and the `range()` function.

In code, a `for` statement looks something like `for i in range(5)`: and includes the following:
- The `for` keyword
- A variable name
- The `in` keyword
- A call to the `range()` method with up to three integers passed to it
- A colon
- Starting on the next line, an indented block of code (called the `for` clause)

```python {title="fiveTimes.py"}
print("My name is")
for i in range(5):
    print("Alex Five Times (" + str(i) + ")")
```

![](/notes/automate-the-boring-stuff-with-python/flow-control-13.webp)

The code in the `for` loop’s clause is run five times. The first time it is run, the variable `i` is set to 0. The `print()` call in the clause will print Jimmy Five Times (0). After Python finishes an iteration through all the code inside the `for` loop’s clause, the execution goes back to the top of the loop, and the `for` statement increments `i` by one. This is why `range(5)` results in five iterations through the clause, with `i` being set to 0, then 1, then 2, then 3, and then 4. The variable `i` will go up to, but will not include, the integer passed to `range()`.

> [!NOTE]- NOTE
> _You can use `break` and `continue` statements inside `for` loops as well. The `continue` statement will continue to the next value of the `for` loop’s counter, as if the program execution had reached the end of the loop and returned to the start. In fact, you can use `continue` and `break` statements only inside `while` and `for` loops. If you try to use these statements elsewhere, Python will give you an error._

Counting the sums of all the numbers to 100 using both `for` and `while` loops:

```python {title="sumof100.py"}
# For Loop to Count the sums of numbers upto 100
sum = 0
for i in range(101):
    sum = sum + i
    # print(sum, i)
print("The sum of 100 using for loop is: ", sum)
# While Loop
#
sum = 0
i = 0

while i < 101:
    sum = sum + i
    i = i + 1
print("The sum of 100 using while loop is: ", sum)
```

- The use of `for` is more efficient though `while` can also get the job done.

### _The Starting, Stopping, and Stepping Arguments to range()_

Some functions can be called with multiple arguments separated by a comma, and `range()` is one of them. This lets you change the integer passed to `range()` to follow any sequence of integers, including starting at a number other than zero.

```python
for i in range(12, 16):  
    print(i)
```

The first argument will be where the `for` loop’s variable starts, and the second argument will be up to, but not including, the number to stop at.

```terminal
12  
13  
14  
15
```

The `range()` function can also be called with three arguments. The first two arguments will be the start and stop values, and the third will be the _step argument_. The step is the amount that the variable is increased by after each iteration.

```python
for i in range(0, 10, 2):  
    print(i)
```

So calling `range(0, 10, 2)` will count from zero to eight by intervals of two.

```terminal
0  
2  
4  
6  
8
```
The `range()` function is flexible in the sequence of numbers it produces for `for` loops. You can even use a negative number for the step argument to make the for loop count down instead of up.

```python
for i in range(5, -1, -1):  
    print(i)
```

This `for` loop would have the following output:

```terminal
5  
4  
3  
2  
1  
0
```

Running a `for` loop to print i with `range(5, -1, -1)` should print from five down to zero.

## Importing Modules

All Python programs can call a basic set of functions called _built-in functions_, including the `print()`, `input()`, and `len()` functions you’ve seen before. 

Python also comes with a set of modules called the _standard library_.

> Each module is a Python program that contains a related group of functions that can be embedded in your programs. For example, the `math` module has mathematics-related functions, the `random` module has random number-related functions, and so on.

Before you can use the functions in a module, you must import the module with an `import` statement. In code, an `import` statement consists of the following:
- The `import` keyword
- The name of the module
- Optionally, more module names, as long as they are separated by commas.

```python {title="printRandom.py"}
import random  
for i in range(5):  
    print(random.randint(1, 10))
```

> [!WARNING]- DON'T OVERWRITE MODULE NAMES
> When you save your Python scripts, take care not to give them a name that is used by one of Python’s modules, such as _random.py_, _sys.py_, _os.py_, or _math.py_. If you accidentally name one of your programs, say, `random.py`, and use an `import random` statement in another program, your program would import your` random.py` file instead of Python’s `random` module. This can lead to errors such as `AttributeError`: module `random` has no attribute 'randint', since your _random.py_ doesn’t have the functions that the real random module has. Don’t use the names of any built-in Python functions either, such as `print()` or `input()`.
>
> Problems like these are uncommon, but can be tricky to solve. As you gain more programming experience, you’ll become more aware of the standard names used by Python’s modules and functions, and will run into these issues less frequently.

Since `randint()` is in the `random` module, you must first type **random.** in front of the function name to tell Python to look for this function inside the `random` module.

### `from import` Statements

An alternative form of the `import` statement is composed of the `from` keyword, followed by the module name, the `import` keyword, and a star; for example,` from random import *`.

With this form of `import` statement, calls to functions in `random` will not need the `random.` prefix. **However, using the full name makes for more readable code, so it is better to use the `import random` form of the statement.**

## Ending a Program Early with the `sys.exit()` function

Programs always terminate if the program execution reaches the bottom of the instructions. However, you can cause the program to terminate, or exit, before the last instruction by calling the `sys.exit()` function.

Since this function is in the `sys` module, you have to import `sys` before you can use it.

```python {title="exitExample.py"}
import sys
while True:
    print('Type exit to quit.')
    response = input()
    if response == 'exit':
        sys.exit()
    print('You typed ' + "'" + response + "'" + '.')
```

Run this program in IDLE. This program has an infinite loop with no `break` statement inside. The only way this program will end is if the execution reaches the `sys.exit()` call. When response is equal to **exit**, the line containing the `sys.exit()` call is executed. Since the response variable is set by the `input()` function, the user must enter exit in order to stop the program.

## **A Short Program: Guess the Number**

We have a pseudocode like this:
```txt
I am thinking of a number between 1 and 20.  
Take a guess.  
10  
Your guess is too low.  
Take a guess.  
15  
Your guess is too low.  
Take a guess.  
17  
Your guess is too high.  
Take a guess.  
16  
Good job! You guessed my number in 4 guesses!
```

I have implemented this code as:

```python {title="guessTheNumber.py"}
from random import randint

secretNumber = randint(1, 20)
# print(secretNumber)  # Debuging purposes only
print("I am thinking of a number between 1 and 20.")
guess = ''
numberOfGuesses = 0
while guess != secretNumber:
    guess = int(input("Take a Guess: "))
    numberOfGuesses = numberOfGuesses + 1
    if guess < secretNumber:
        print("Your Guess is too low.")
    elif guess > secretNumber:
        print("Your Guess is too high")

print("Good job! You guessed my number in " +
      str(numberOfGuesses) + " guesses!")
```

> [!INFO]- This how **Al** implemented it...
> 
> ```python {title="guessTheNumber.py"}
> # This is a guess the number game.  
> import random  
> secretNumber = random.randint(1, 20)  
> print('I am thinking of a number between 1 and 20.')  
>   
> # Ask the player to guess 6 times.  
> for guessesTaken in range(1, 7):  
>     print('Take a guess.')  
>     guess = int(input())  
>     if guess < secretNumber:  
>         print('Your guess is too low.')  
>     elif guess > secretNumber:  
>         print('Your guess is too high.')  
>     else:  
>         break    # This condition is the correct guess!  
>   
> if guess == secretNumber:  
>     print('Good job! You guessed my number in ' + str(guessesTaken) + '  
> guesses!')  
> else:  
>     print('Nope. The number I was thinking of was ' + str(secretNumber))
> ```

> [!INFO]- Version 2.0 of my implementation of `guessTheNumber2.py` game...
>
> ```python
> from random import randint
> secretNumber = randint(1, 20)
> # print(secretNumber)  # Debuging purposes only
> print("I am thinking of a number between 1 and 20.")
> # guess = ''
> numberOfGuesses = 0
> while True:
>     guess = int(input("Take a Guess: "))
>     numberOfGuesses = numberOfGuesses + 1
>     if guess < secretNumber:
>         print("Your Guess is too low.")
>     elif guess > secretNumber:
>         print("Your Guess is too high")
>     else:
>         break
> 
> print("Good job! You guessed my number in " +
>       str(numberOfGuesses) + " guesses!")
> 
> ```
> I'm still going with the unlimited number of guesses method, but improved the logic.

## **A Short Program: Rock, Paper, Scissors**

We have the Pseudocode for the program:
```txt
ROCK, PAPER, SCISSORS  
0 Wins, 0 Losses, 0 Ties  
Enter your move: (r)ock (p)aper (s)cissors or (q)uit  
p  
PAPER versus...  
PAPER  
It is a tie!  
0 Wins, 1 Losses, 1 Ties  
Enter your move: (r)ock (p)aper (s)cissors or (q)uit  
s  
SCISSORS versus...  
PAPER  
You win!  
1 Wins, 1 Losses, 1 Ties  
Enter your move: (r)ock (p)aper (s)cissors or (q)uit  
q
```

That's how I implemented it:

```python [title="rpsGame5.py"]
##########################################
########  RPS GAME VERSION 5.0  ##########
##########################################

import random
import sys

# Print to the Screen Once
print("ROCK, PAPER, SCISSORS")

# Counting Streaks
wins = 0
losses = 0
ties = 0

while True:
    # Print to the Screen
    print("Enter your move: (r)ock (p)aper (s)cissors or (q)uit")

    # User Input
    userMove = input()
    if userMove == "q":
        print(f"Thank you for playing our Game!\n {
              wins} Wins, {losses} losses, {ties} Ties")
        sys.exit()
    elif userMove != "r" and userMove != "p" and userMove != "s":
        print("Illegal Guess, Try again.")
        continue
    elif userMove == "r":
        userMove = "ROCK"
    elif userMove == "p":
        userMove = "PAPER"
    elif userMove == "s":
        userMove = "SCISSORS"

    # System input
    systemMove = random.randint(1, 3)
    if systemMove == 1:
        systemMove = "ROCK"
    elif systemMove == 2:
        systemMove = "PAPER"
    elif systemMove == 3:
        systemMove = "SCISSORS"

    # Showing the Played Moves
    print(f"{systemMove} vs. {userMove}")

    # Game Logic
    if systemMove == userMove:
        print("It is a tie")
        ties = ties + 1
    elif (
        (systemMove == "ROCK" and userMove == "PAPER")
        or (systemMove == "SCISSORS" and userMove == "ROCK")
        or (systemMove == "PAPER" and userMove == "SCISSORS")
    ):
        print("You win!")
        wins = wins + 1
    elif (
        (systemMove == "ROCK" and userMove == "SCISSORS")
        or (systemMove == "PAPER" and userMove == "ROCK")
        or (systemMove == "SCISSORS" and userMove == "PAPER")
    ):
        print("Loser!")
        losses = losses + 1

```

> [!TIP]-
> Go to my [GitHub](https://github.com/abuturabofficial/python-automation-pg/tree/main/section-2_flow_control) to see other versions of the game, and how I went step by step, implementing the logic and cleaning the code. It still isn't efficient or clean looking code, as we haven't gotten to some advanced lessons, which can help us clean it up further.

> [!INFO]- This how **Al** implemented it...
> ```python {title="rpsGame.py"}
> import random, sys  
>   
> print('ROCK, PAPER, SCISSORS')  
>   
> # These variables keep track of the number of wins, losses, and ties.  
> wins = 0  
> losses = 0  
> ties = 0  
>   
> while True: # The main game loop.  
>     print('%s Wins, %s Losses, %s Ties' % (wins, losses, ties))  
>     while True: # The player input loop.  
>         print('Enter your move: (r)ock (p)aper (s)cissors or (q)uit')  
>         playerMove = input()  
>         if playerMove == 'q':  
>             sys.exit() # Quit the program.  
>         if playerMove == 'r' or playerMove == 'p' or playerMove == 's':  
>             break # Break out of the player input loop.  
>         print('Type one of r, p, s, or q.')  
>   
>     # Display what the player chose:  
>     if playerMove == 'r':  
>         print('ROCK versus...')  
>     elif playerMove == 'p':  
>         print('PAPER versus...')  
>     elif playerMove == 's':  
>         print('SCISSORS versus...')  
>   
>     # Display what the computer chose:  
>     randomNumber = random.randint(1, 3)  
>     if randomNumber == 1:  
>         computerMove = 'r'  
>         print('ROCK')  
>     elif randomNumber == 2:  
>         computerMove = 'p'  
>         print('PAPER')  
>     elif randomNumber == 3:  
>         computerMove = 's'  
>         print('SCISSORS')  
>   
>     # Display and record the win/loss/tie:  
>     if playerMove == computerMove:  
>         print('It is a tie!')  
>         ties = ties + 1  
>     elif playerMove == 'r' and computerMove == 's':  
>         print('You win!')  
>         wins = wins + 1  
>     elif playerMove == 'p' and computerMove == 'r':  
>         print('You win!')  
>         wins = wins + 1  
>     elif playerMove == 's' and computerMove == 'p':  
>         print('You win!')  
>         wins = wins + 1  
>     elif playerMove == 'r' and computerMove == 'p':  
>         print('You lose!')  
>         losses = losses + 1  
>     elif playerMove == 'p' and computerMove == 's':  
>         print('You lose!')  
>         losses = losses + 1  
>     elif playerMove == 's' and computerMove == 'r':  
>         print('You lose!')  
>         losses = losses + 1
> ```

## `abs()` Function (Extras)

The Python `abs()` function return the absolute value. The absolute value of any number is always positive it removes the negative sign of a number in Python.

```python
>>> abs(-10)  
10  
>>> abs(-0.50)  
0.5  
>>> abs(-32.40)  
32.4
```