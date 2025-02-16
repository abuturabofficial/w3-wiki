---
draft: false
date: '2025-02-16T12:19:07+05:00'
title: 'Section 5: Writing a Complete Program, Guess the Number'
linkTitle: 'Writing a Complete Program'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 5
math: true
---

## A Guess Game

The output we need:

```txt
Hello, What is your name?
Al
Well, Al, I am thinking of a number between 1 and 20.
Take a guess.
10
Your guess is too low.
Take a guess
5
Your guess is too high.
Take a guess.
6
Good job, Al! You guessed my number in 5 guesses!
```

```python {title="guessGame.py", linenos=on}
import random
# Ask for Player name and greet them
playerName = input('Hello, What is your name?\n')
print(f"Well, {playerName}, I am thinking of a number between 1 and 20.")


secretNumber = random.randint(1, 20)
# print(f"Debug: Secret Number is {secretNumber}")


for numberOFGuesses in range(1, 7):  # Max number of Guesses allowed
    playerGuess = int(input('Take a Guess\n'))
    if playerGuess < secretNumber:
        print('Your Guess is too low.')
    elif playerGuess > secretNumber:
        print('Your Guess is too high')
    else:
        break


if playerGuess == secretNumber:
    print(f'Good job,{playerName}! You guessed my number in {
        numberOFGuesses} guesses!')
else:
    print(f"Nope. The number I was thinking of was {secretNumber}.")

```

###  F-Strings

In this course we were taught about string concatenation using `+` operator. But that is cumbersome, and we need to convert non-strings values to strings values for concatenation to work.

In python 3.6, F-strings were introduced, that makes the strings concatenation a lot easier.

```python
print(f"This is an example of {strings} concatenation.")
```

`{}` We can put our variable name, which will be automatically converted into string type. As you can see, this approach is much more cleaner.

## A Guess Game --- Extended Version

Let's take everything we learned so far, write a guess game which has the following qualities:
- An error checking
- Asking player to choose the lower and higher end of number for guessing game.
- Let player exit the game using `sys.exit()` module or pressing `q(uit)` button on their keyboard. 
- Using built-in function `title()` method, convert a string into title case, where the first letter of each word is capitalized, and the rest are in lowercase.

An extra feature which I want to implement is telling the player, how many guesses they will get. As taught in [Algorithm: Binary Search](/cs-and-programming/computer-science-theory/unit-1/binary-search/) course, offered by **Khan Academy**. We can calculate max number of guesses using this formula:

$$
\text{Maximum number of guesses} = \log_{2}(n) \\
$$

For guess between (1, 20), the n = 20:

$$
\text{Maximum number of guesses} = \log_{2}(20)
$$

$$
\text{Maximum number of guessess} \approx  5
$$

Here is the extended version, I might have gone a bit over the board.

```python {title="guessGameExtended.py", linenos=on}
import random
import math
import sys
import time


def quitGame():
    # Message to print when CTRL+C keys are pressed
    print('\nThanks for Playing, quiting the game...')
    sys.exit()


# Greeting the Player
try:
    print('Welcome to Guess the Number Game. \nYou can Quit the game any time by pressing CTRL+C keys on your keyboard')
    playerName = input('Hello, What is your name?\n').title()
    print(
        f"Well, {playerName}, let's choose our start and end values for the game.")
except KeyboardInterrupt:
    quitGame()


# Asking Player for Guessing Range and Error Checking
while True:
    try:
        lowerEndOfGuess = int(input('Choose your start number: '))
        higherEndOfGuess = int(input('Choose your end number: '))
        if lowerEndOfGuess > higherEndOfGuess:  # Otherwise our random function will fail
            print('Starting number should be less than ending number')
            continue
        break
    except ValueError:
        print('Only Intergers are allowed as a start and end values of a Guessing Game.')
    except KeyboardInterrupt:
        quitGame()


# Haing Fun and choosing the secret number
try:
    print('Wait, a moment, I m gearing up for the battle.')
    time.sleep(2)
    print("Don't be stupid.I'm not stuck., I'm still thinking of what number to choose!")
    time.sleep(3)
    print('Dont dare to Quit on me')
    secretNumber = random.randint(lowerEndOfGuess, higherEndOfGuess)
    time.sleep(2.5)
    print('Shshhhhhhh! I have chosen my MAGIC NUMBER!')
    time.sleep(1.5)
    print("It's your turn")
    time.sleep(1.5)
except KeyboardInterrupt:
    quitGame()
# print(f"Debug: Secret Number is {secretNumber}")


# Calculating maximum number of possible guesses
totalGuesses = higherEndOfGuess - lowerEndOfGuess
maxPossibleGuesses = math.ceil(math.log2(totalGuesses))
print(f"You have {maxPossibleGuesses} guesses to Win the Game.")
time.sleep(1.5)


# Game Logic
for numberOFGuesses in range(1, maxPossibleGuesses+1):
    try:
        playerGuess = int(input('Take a Guess!\n'))
        if playerGuess < secretNumber:
            print('Your Guess is too low!')
        elif playerGuess > secretNumber:
            print('Your Guess is too high!')
        else:
            break
    except ValueError:
        print('Only integers are allowed as valid game guess.')
    except KeyboardInterrupt:
        quitGame()


# Ending the Game
try:
    if playerGuess == secretNumber:
        print(f'Good job,{playerName}! You guessed my number in {
            numberOFGuesses} guesses!')
    else:
        print(f"You lose! Number of guesses are exhausted. The number I was thinking of was {
              secretNumber}.")
except NameError:
    print('Please, try again, something went wrong!')
```