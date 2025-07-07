---
draft: false
date: '2025-01-31T11:07:49+05:00'
title: 'Introduction to Algorithms'
linkTitle: 'Intro to Algorithms'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
math: true
---

## What is an algorithm, and why should you care?

In computer science, an algorithm is a set of setups for a computer to accomplish a task.

![](/notes/computer-science-theory/intro-to-algorithms.webp)

Algorithm are reason why there is a science in a computer science.

Examples:

- YouTube use compression algorithms to store and deliver videos efficiently in less cost
- Google Maps use routing finding algorithms to find the shortest possible route between point A and point B

### Why to use algorithms?

- To perform the task faster
- To reduce cost by eliminating the unnecessary steps

Computer scientists have written an algorithm for a checker game, where the computer never lose.

![](/notes/computer-science-theory/intro-to-algorithms-1.webp)

### What makes a good algorithm?

- Correctness
- Efficiency

Sometimes we need the algorithm to give us efficient but not necessarily the 100% accurate answer. For example, a truck needs to find a route between two locations, algorithm may take a lot of time to calculate the correct and the most efficient route. We will be okay for the program to calculate the good but maybe not the best route in the matter of seconds.

#### How to measure the efficiency?

Computer Scientists use **Asymptotic Analysis** to find out the efficiency of an algorithm.

> Asymptotic analysis is a method used in mathematical analysis and computer science to describe the limiting behavior of functions, particularly focusing on the performance of algorithms. It helps in understanding how an algorithm's resource requirements, such as time and space, grow as the input size increases.

![](/notes/computer-science-theory/intro-to-algorithms-2.webp)

## Guessing Game

If we have to guess the number between **1 and 15**, how and every time we guess, we are told, if our guessed number is lower or higher the actual number.

- [Guessing Game 1](https://www.khanacademy.org/computer-programming/guess-my-number/4863148342902784)
- [Guessing Game 2](https://www.khanacademy.org/computer-programming/program/6095780544249856)

How to approach?

### Linear Search

  We will start from either **1** to keep increasing one digit until we reach the correct number, or start from **15** and keep decreasing 1 until the guess is right.

The method we use here is called a **linear search**.

> Linear search, also known as sequential search, is a simple searching algorithm used to find an element within a list. It sequentially checks each element of the list until it finds a match or reaches the end of the list.
>
> --- Wikipedia

This is the inefficient way of finding the right number. If computer has selection 15, we will need to 15 guesses to reach the correct digit. If we are lucky and computer has selected 1, we can reach it in a single guess.

### Binary Search

Another approach we can use is by taking average before each. First guess will be **8**, if the guess is lower, we can eliminate all the numbers before 8, if the guess is higher, we can eliminate all the numbers from 8 to 15 and so on.

This approach is called **Halving method**. And in computer terms, it's called **Binary Search**.

Using this technique maximum number of guesses needed can be found:

$$
\text{Maximum number of guesses} = \log_{2}(n)
$$

Where **n = Maximum Possible Guess**

> **Binary search** is a fast search algorithm used in computer science to find a specific element in a sorted array. It works on the principle of divide and conquer, reducing the search space by half with each step. The algorithm starts by comparing the target value with the middle element of the array. If the target value matches the middle element, the search is complete. If the target value is less or greater than the middle element, the search continues in the lower or upper half of the array, respectively. This process repeats until the target value is found, or the search space is exhausted.
> 
> --- Wikipedia