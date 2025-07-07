---
draft: false
date: '2025-02-15T15:55:35+05:00'
title: 'Section 6: Lists'
linkTitle: 'Lists'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 6
---

- A list is a value that contains multiple values.
- The values in a list are also called item.
- You can access items in a list with its integer index.
- The indexes start at `0`, not `1`.
- You can also use negative indexes. `-1` refers to the last item, `-2` refers to the second to last item, and so on.
- You can get multiple items from the list using a slice.
- The slice has two indexes. The new list's items start at the first index and go up to, but doesn't include, the second index.
- The len() function, concatenation, and replication work the same way with lists that they do with strings.
- You can convert a value into a list by passing it to the first() function.

## The list Data Type

A list is a value that contains multiple values in an ordered sequence. The term list value refers to the list itself (which is a value that can be stored in a variable or passed to a function like any other value), not the values inside the list value.

```python
   >>> [1, 2, 3]  
   [1, 2, 3]  
   >>> ['cat', 'bat', 'rat', 'elephant']  
   ['cat', 'bat', 'rat', 'elephant']  
   >>> ['hello', 3.1415, True, None, 42]  
   ['hello', 3.1415, True, None, 42]  
➊ >>> spam = ['cat', 'bat', 'rat', 'elephant']  
   >>> spam  
   ['cat', 'bat', 'rat', 'elephant']
```

The `spam` variable ➊ is still assigned only one value: the list value. But the list value itself contains other values. The value `[]` is an empty list that contains no values, similar to `''`, the empty string.

### Getting Individual Values in a List with Indexes

![](/notes/automate-the-boring-stuff-with-python/lists.webp)

Lists can also contain other list values. The values in these lists of lists can be accessed using multiple indexes, like so:

```python
>>> spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]  
>>> spam[0]  
['cat', 'bat']  
>>> spam[0][1]  
'bat'  
>>> spam[1][4]  
50
```

The first index dictates which list value to use, and the second indicates the value within the list value.

### Negative Indexes

The integer value `-1` refers to the last index in a list, the value `-2` refers to the second-to-last index in a list, and so on.

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[-1]  
'elephant'  
>>> spam[-3]  
'bat'  
>>> 'The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.'  
'The elephant is afraid of the bat.'
```

### Getting a List from Another List with Slices

Just as an index can get a single value from a list, a slice can get several values from a list, in the form of a new list. A slice goes up to, but will not include, the value at the second index.

- `spam[2]` is a list with an index (one integer).
- `spam[1:4]` is a list with a slice (two integers)

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[0:4]  
['cat', 'bat', 'rat', 'elephant']  
>>> spam[1:3]  
['bat', 'rat']  
>>> spam[0:-1]  
['cat', 'bat', 'rat']
```

As a shortcut, you can leave out one or both of the indexes on either side of the colon in the slice. Leaving out the first index is the same as using 0, or the beginning of the list. Leaving out the second index is the same as using the length of the list, which will slice to the end of the list. Enter the following into the interactive shell:

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[:2]  
['cat', 'bat']  
>>> spam[1:]  
['bat', 'rat', 'elephant']  
>>> spam[:]  
['cat', 'bat', 'rat', 'elephant']
```

### Getting a List's Length with the `len()` Function

The `len()` function will return the number of values that are in a list value passed to it, just like it can count the number of characters in a string value.

```python
>>> spam = ['cat', 'dog', 'moose']  
>>> len(spam)  
3
```

### Changing Values in a List with Indexes

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam[1] = 'aardvark'  
>>> spam  
['cat', 'aardvark', 'rat', 'elephant']  
>>> spam[2] = spam[1]  
>>> spam  
['cat', 'aardvark', 'aardvark', 'elephant']  
>>> spam[-1] = 12345  
>>> spam  
['cat', 'aardvark', 'aardvark', 12345]
```

### List Concatenation and List Replication

```python
>>> [1, 2, 3] + ['A', 'B', 'C']  
[1, 2, 3, 'A', 'B', 'C']  
>>> ['X', 'Y', 'Z'] * 3  
['X', 'Y', 'Z', 'X', 'Y', 'Z', 'X', 'Y', 'Z']  
>>> spam = [1, 2, 3]  
>>> spam = spam + ['A', 'B', 'C']  
>>> spam  
[1, 2, 3, 'A', 'B', 'C']
```

### Removing Values from Lists with `del` Statements

The `del` statement will delete values at an index in a list. All the values in the list after the deleted value will be moved up one index.

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> del spam[2]  
>>> spam  
['cat', 'bat', 'elephant']  
>>> del spam[2]  
>>> spam  
['cat', 'bat']
```


The `del` statement can also be used on a simple variable to delete it, as if it were an "un-assignment" statement. If you try to use the variable after deleting it, you will get a `NameError` error because the variable no longer exists. In practice, you almost never need to delete simple variables. The `del` statement is mostly used to delete values from lists.

### Working with Lists

- It's tempting to create many individual variables to store a group of similar values.
- It's a bad way to write a program.
- Down the line, when you will need to store more values, you won't be able, if you run out of variables.

Let's look at the example of bad code using a lot of variables to store a group of similar values:

```python {title="allMyCats.py"}
print('Enter the name of cat 1:')  
catName1 = input()  
print('Enter the name of cat 2:')  
catName2 = input()  
print('Enter the name of cat 3:')  
catName3 = input()  
print('Enter the name of cat 4:')  
catName4 = input()  
print('Enter the name of cat 5:')  
catName5 = input()  
print('Enter the name of cat 6:')  
catName6 = input()  
print('The cat names are:')  
print(catName1 + ' ' + catName2 + ' ' + catName3 + ' ' + catName4 + ' ' +  
catName5 + ' ' + catName6)
```

Improved version:

```python {title="allMyCats2.py"}
catName = []

while True:
    print(f"Enter your cat name: {
          len(catName) + 1} (Or Enter nothing to stop.)")
    name = input()
    if name == '':
        break
    catName = catName + [name]


print("The cat names are: ")
for name in catName:
    print(f"  {name}")

```

## `for` Loops with Lists, Multiple Assignment, and Augmented Operators

- For loops technically iterate over the values in a list.
- The `range()` function returns a list-like value, which can be passed to the `list()` function if you need an actual list value.
- Variables can swap their values using multiple assignment.
- Augmented assignment operators like `+=` are used as shortcuts.

### Using `for` Loops with Lists

`for` Loops execute a block of code a certain number of times. Technically, a `for` loop repeats the code block once for each item in a list value. 

```python
#input
for i in range(4):  
    print(i)
#output
0  
1  
2  
3
```

This is because the return value from `range(4)` is a sequence value that Python considers similar to `[0,1,2,3]` ([Sequence Data Types](#sequence-data-types)).

The following program has same output as the previous one:

```python
for i in [0, 1, 2, 3]:  
    print(i)
```

A common Python technique is to use `range(len(someList))` with a `for` loop to iterate over the indexes of a list.

```python
supplies = ['pens', 'staplers', 'printers', 'binders']
for i in range(len(supplies)):
    print(f"Index of {i} in supplies is: {supplies[i]}")
  
Index 0 in supplies is: pens  
Index 1 in supplies is: staplers  
Index 2 in supplies is: printers  
Index 3 in supplies is: binders
```

### The `in` and `not in` Operators

The `in` and `not in` operators are used to determine whether a value is or isn't in a list.

```python
>>> 'howdy' in ['hello', 'hi', 'howdy', 'heyas']  
True  
>>> spam = ['hello', 'hi', 'howdy', 'heyas']  
>>> 'cat' in spam  
False  
>>> 'howdy' not in spam  
False  
>>> 'cat' not in spam  
True
```

**Program**: Write a program that lets the user type in a pet name and then checks to see whether the name is in a list of pets.

### The Multiple Assignment Trick

The multiple assignment trick (technically called **tuple unpacking**) is a shortcut that lets you assign multiple variables with the values in a list in one line of code. So instead of doing this:

```python
>>> cat = ['fat', 'gray', 'loud']  
>>> size = cat[0]  
>>> color = cat[1]  
>>> disposition = cat[2]
```

you could write code like this:

```python
>>> cat = ['fat', 'gray', 'loud']  
>>> size, color, disposition = cat
```

The number of variables and the length of the list must be exactly equal, or Python will give you a `ValueError`.

### Using the `enumerate()` Function with Lists

Instead of using `range(len(someList))` technique, `enumerate()` returns both list item, and its index, when called upon a list.

```python
>>> supplies = ['pens', 'staplers', 'flamethrowers', 'binders']  
>>> for index, item in enumerate(supplies):  
...     print('Index ' + str(index) + ' in supplies is: ' + item)  
  
Index 0 in supplies is: pens  
Index 1 in supplies is: staplers  
Index 2 in supplies is: flamethrowers  
Index 3 in supplies is: binders
```

The `enumerate()` function is useful if you need both the item and the item's index in the loop's block.

### Using the `random.choice()` and `random.shuffle()` Functions with Lists

The `random` module has a couple of functions that accept lists for arguments. The `random.choice()` function will return a randomly selected item from the list.

```python
>>> import random  
>>> pets = ['Dog', 'Cat', 'Moose']  
>>> random.choice(pets)  
'Dog'  
>>> random.choice(pets)  
'Cat'  
>>> random.choice(pets)  
'Cat'
```

Consider `random.choice(someList)` to be a shorter form of `someList[random.randint(0, len(someList) - 1]`.

The `random.shuffle()` function will reorder the items in the list, without need to return a new list.

```python
>>> import random  
>>> people = ['Alice', 'Bob', 'Carol', 'David']  
>>> random.shuffle(people)  
>>> people  
['Carol', 'David', 'Alice', 'Bob']  
>>> random.shuffle(people)  
>>> people  
['Alice', 'David', 'Bob', 'Carol']
```

### Augmented Assignment Operators

| **Augmented assignment statement** | **Equivalent assignment statement** |
| ---------------------------------- | ----------------------------------- |
| spam += 1                          | spam = spam + 1                     |
| spam -= 1                          | spam = spam - 1                     |
| spam *= 1                          | spam = spam * 1                     |
| spam /= 1                          | spam = spam / 1                     |
| spam %= 1                          | spam = spam % 1                     |

The `+=` operator can also do string and list concatenation, and the `*=` operator can do string and list replication.

```python
>>> spam = 'Hello,'  
>>> spam += ' world!'  
>>> spam  
'Hello world!'  
>>> bacon = ['Zophie']  
>>> bacon *= 3  
>>> bacon  
['Zophie', 'Zophie', 'Zophie']
```

## List Methods

- Methods are functions that are "called on" values.
- The `index()` list method returns the index of an item in the list.
- The `append()` list method adds a value to the end of the list.
- The `insert()` list method adds a value anywhere inside a list.
- The `remove()` list method removes an item, specified by the value, from a list.
- The `sort()` list method sorts the items in a list.
- The `sort()` method's **reverse=True keyword** argument can sort in reverse order.
- Sorting happens in "ASCII-betical" order. To sort normally, pass **key=str.lower**.
- These list methods operate on the list "in place", rather than returning a new list value.
- Methods belong to a single data type. The `append()` and `insert()` methods are list methods and can be only called on list values, not on other values such as strings or integers.
- Calling list methods on `str` or `inte` will give the error `AttributeError`.

Each data type has its own set of methods. This list data type, for example, has several useful methods for finding, adding, removing, and other manipulating values in a list.

### Finding a Value in a List with the `index()` Method

```python
>>> spam = ['hello', 'hi', 'howdy', 'heyas']  
>>> spam.index('hello')  
0  
>>> spam.index('heyas')  
3  
>>> spam.index('howdy howdy howdy')  
Traceback (most recent call last):  
  File "<pyshell#31>", line 1, in <module>  
    spam.index('howdy howdy howdy')  
ValueError: 'howdy howdy howdy' is not in list
```

### Adding Values to Lists with the `append()` and `insert()` Methods

```python
>>> spam = ['cat', 'dog', 'bat']  
>>> spam.append('moose')  
>>> spam  
['cat', 'dog', 'bat', 'moose']
```

The `append()` methods adds item to the end of the list, `insert()` method can insert a value at any index in the list.

```python
>>> spam = ['cat', 'dog', 'bat']  
>>> spam.insert(1, 'chicken')  
>>> spam  
['cat', 'chicken', 'dog', 'bat']
```

Notice that the code is `spam.append('moose')` and `spam.insert(1, 'chicken')`, not `spam = spam.append('moose')` and `spam = spam.insert(1, 'chicken')`. Neither `append()` nor `insert()` gives the new value of spam as its return value. (In fact, the return value of `append()` and `insert()` is `None`, so you definitely wouldn’t want to store this as the new variable value.) Rather, the list is modified _in place_. Modifying a list in place is covered in more detail later in [Mutable and Immutable Data Types](#mutable-and-immutable-data-types).

### Removing Values from Lists with `remove()` Method

```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']  
>>> spam.remove('bat')  
>>> spam  
['cat', 'rat', 'elephant']
```

- Attempting to delete a value that doesn't exist in the list will result in a `ValueError` error.
- If the value appears multiple times in the list, only the first instance of the value will be removed.
- The `del` statement is good to use when you know the index of the value, you want to remove from the list.
- The `remove()` method is useful when you know the value you want to remove from list.

### Sorting the Values in a List with the sort() Method

```python
>>> spam = [2, 5, 3.14, 1, -7]  
>>> spam.sort()  
>>> spam  
[-7, 1, 2, 3.14, 5]  
>>> spam = ['ants', 'cats', 'dogs', 'badgers', 'elephants']  
>>> spam.sort()  
>>> spam  
['ants', 'badgers', 'cats', 'dogs', 'elephants']
```

You can also pass `True` for the `reverse` keyword argument to have `sort()` sort the values in reverse order.

```python
>>> spam.sort(reverse=True)  
>>> spam  
['elephants', 'dogs', 'cats', 'badgers', 'ants']
```

- The `sort()` method sorts the list in place, don't try to capture the return value writing code like `spam = spam.sort()`.
- You cannot sort lists that have both number values and string values. Since Python doesn't know what to do with them.
- The `sort()` uses **ASCII-betical order** rather than actual alphabetical order for sorting strings. This means uppercase letters come before lowercase letters.

```python
>>> spam = ['Alice', 'ants', 'Bob', 'badgers', 'Carol', 'cats']  
>>> spam.sort()  
>>> spam  
['Alice', 'Bob', 'Carol', 'ants', 'badgers', 'cats']
```

For regular alphabetical order:

```python
>>> spam = ['a', 'z', 'A', 'Z']  
>>> spam.sort(key=str.lower)  
>>> spam  
['a', 'A', 'z', 'Z']
```

### Reversing the Values in a List with `reverse()` Method

- Like the `sort()` list method, `reverse()` doesn't return a list.

```python
>>> spam = ['cat', 'dog', 'moose']  
>>> spam.reverse()  
>>> spam  
['moose', 'dog', 'cat']
```

> [!TIP]- Exceptions to Indentation Rules in Python
>
> In most cases, the amount of indentation for a line of code tells Python what block it is in. There are some exceptions to this rule, however. For example, lists can actually span several lines in the source code file. The indentation of these lines does not matter; Python knows that the list is not finished until it sees the ending square bracket. For example, you can have code that looks like this:
>
> ```python
> spam = ['apples',  
>     'oranges',  
>                     'bananas',  
> 'cats']  
> print(spam)
> ```
> Of course, practically speaking, most people use Python’s behavior to make their lists look pretty and readable.

## Similarities Between Lists and Strings

- Strings can do a lot of the same things lists can do, but strings are immutable.
- Mutable values like lists can be modified in place.
- Variables don't contain lists, they contain references to lists.
- When passing a list argument to a function, you are actually passing a list reference.
- Changes made to a list in a function will affect the list outside the function.
- The `\` line continuation character can be used to stretch Python instructions across multiple lines.

### Sequence Data Types

Lists aren't the only data types that represent ordered sequences of values.

- Strings and lists are actually similar if you consider a string to be a "list" of single text characters.
- The Python sequence data types include lists, strings, range object returned by `range()`, and [tuples](#the-tuple-data-type).
- Many things you can do with lists can also be done with strings and other values of sequence types: indexing; slicing; and using them with for loops, with `len()`, and with `in` and `not in` operators.

```python
>>> name = 'Zophie'  
>>> name[0]  
'Z'  
>>> name[-2]  
'i'  
>>> name[0:4]  
'Zoph'  
>>> 'Zo' in name  
True  
>>> 'z' in name  
False  
>>> 'p' not in name  
False  
>>> for i in name:  
...     print('* * * ' + i + ' * * *')  
  
* * * Z * * *  
* * * o * * *  
* * * p * * *  
* * * h * * *  
* * * i * * *  
* * * e * * *
```


### Mutable and Immutable Data Types

A list value:
- Mutable data type
- It can have values added, removed, or changed.

A string value is:
- Immutable data type
- It cannot be changed

Trying to reassign a single character in a string results in a `TypeError` error:

```python
>>> name = 'Zophie a cat'  
>>> name[7] = 'the'  
Traceback (most recent call last):  
  File "<pyshell#50>", line 1, in <module>  
    name[7] = 'the'  
TypeError: 'str' object does not support item assignment
```

The proper way to "mutate" a string is to use slicing and concatenation to build a new string by copying from parts of the old string.

```python
>>> name = 'Zophie a cat'  
>>> newName = name[0:7] + 'the' + name[8:12]  
>>> name  
'Zophie a cat'  
>>> newName  
'Zophie the cat'
```

Although a list value is mutable:

```python
>>> eggs = [1, 2, 3]  
>>> eggs = [4, 5, 6]  
>>> eggs  
[4, 5, 6]
```

The list value in `eggs` isn't being changed here; rather, an entirely new and different list value `[4, 5, 6]` is overwriting the old list.

![](/notes/automate-the-boring-stuff-with-python/lists-1.webp)

For actually modifying the list:

```python
>>> eggs = [1, 2, 3]  
>>> del eggs[2]  
>>> del eggs[1]  
>>> del eggs[0]  
>>> eggs.append(4)  
>>> eggs.append(5)  
>>> eggs.append(6)  
>>> eggs  
[4, 5, 6]
```

![](/notes/automate-the-boring-stuff-with-python/lists-2.webp)

### The Tuple Data Type

The tuple data type is almost identical to the list data type, except in two ways:
- Unlike lists, they are immutable.
- They are represented by parentheses `()`.

```python
>>> eggs = ('hello', 42, 0.5)  
>>> eggs[0]  
'hello'  
>>> eggs[1:3]  
(42, 0.5)  
>>> len(eggs)  
3
```

If you have only one value in your tuple, you cna indicate this by placing a trailing comma after the value inside the parentheses. Otherwise, Python will think you've just typed a value inside regular parentheses.

```python
>>> type(('hello',))  
<class 'tuple'>  
>>> type(('hello'))  
<class 'str'>
```

You can use tuples to convey to anyone reading your code that you don’t intend for that sequence of values to change. If you need an ordered sequence of values that never changes, use a tuple. A second benefit of using tuples instead of lists is that, because they are immutable, and their contents don’t change, Python can implement some optimizations.

### Converting Types with the `list()` and `tuple()` Functions

Just like how `str(42)` will return `'42'`, the string representation of the integer `42`, the functions `list()` and `tuple()` will return list and tuple versions of the values passed to them:

```python
>>> tuple(['cat', 'dog', 5])  
('cat', 'dog', 5)  
>>> list(('cat', 'dog', 5))  
['cat', 'dog', 5]  
>>> list('hello')  
['h', 'e', 'l', 'l', 'o']
```

Converting a tuple to a list is handy if you need a mutable version of a tuple value.

## Reference Types

As you’ve seen, variables “store” strings and integer values. However, this explanation is a simplification of what Python is actually doing. Technically, variables are storing references to the computer memory locations where the values are stored.

```python
>>> spam = 42  
>>> cheese = spam  
>>> spam = 100  
>>> spam  
100  
>>> cheese  
42
```

When you assign `42` to the spam variable, you are actually creating the `42` value in the computer’s memory and storing a _reference_ to it in the spam variable. When you copy the value in `spam` and assign it to the variable `cheese`, you are actually copying the reference. Both the `spam` and `cheese` variables refer to the `42` value in the computer’s memory. When you later change the value in `spam` to `100`, you’re creating a new `100` value and storing a reference to it in `spam`. This doesn’t affect the value in `cheese`. Integers are _immutable_ values that don’t change; changing the _spam_ variable is actually making it refer to a completely different value in memory.

But lists don’t work this way, because list values can change; that is, lists are _mutable_. Here is some code that will make this distinction easier to understand.

```python
➊ >>> spam = [0, 1, 2, 3, 4, 5]  
➋ >>> cheese = spam # The reference is being copied, not the list.  
➌ >>> cheese[1] = 'Hello!' # This changes the list value.  
   >>> spam  
   [0, 'Hello!', 2, 3, 4, 5]  
   >>> cheese # The cheese variable refers to the same list.  
   [0, 'Hello!', 2, 3, 4, 5]
```

This might look odd to you. The code touched only the `cheese` list, but it seems that both the `cheese` and `spam` lists have changed.

When you create the list ➊, you assign a reference to it in the `spam` variable. But the next line ➋ copies only the list reference in `spam` to cheese, not the list value itself. This means the values stored in `spam` and `cheese` now both refer to the same list. There is only one underlying list because the list itself was never actually copied. So when you modify the first element of `cheese` ➌, you are modifying the same list that `spam` refers to.

What happens when a list is assigned to the `spam` variable.

![](/notes/automate-the-boring-stuff-with-python/lists-3.webp)

Then, the reference in `spam` is copied to `cheese`. Only a new reference was created and stored in `cheese`, not a new list. Note how both references refer to the same list.

![](/notes/automate-the-boring-stuff-with-python/lists-4.webp)

When you alter the list that `cheese` refers to, the list that `spam` refers to is also changed, because both `cheese` and `spam` refer to the same list.

![](/notes/automate-the-boring-stuff-with-python/lists-5.webp)

### Identity and the `id()` Function

Why the weird behavior with mutable lists in the previous section doesn't happen with immutable values like integers or strings.

We can use Python's `id()` function to understand this. All values in Python have a unique identity that can be obtained with the `id()` function.

```python
> id('Howdy') # The returned number will be different on your machine.  
139789342729024
```

When Python runs `id('Howdy')`, it creates the `'Howdy'` string in the computer’s memory. The numeric memory address where the string is stored is returned by the `id()` function. Python picks this address based on which memory bytes happen to be free on your computer at the time, so it’ll be different each time you run this code.

Like all strings, `'Howdy'` is immutable and cannot be changed. If you “change” the string in a variable, a new string object is being made at a different place in memory, and the variable refers to this new string. For example, enter the following into the interactive shell and see how the identity of the string referred to by `bacon` changes:

```python
>>> bacon = 'Hello'  
>>> id(bacon)  
139789339474704  
>>> bacon += ' world!' # A new string is made from 'Hello' and ' world!'.  
>>> id(bacon) # bacon now refers to a completely different string.  
139789337326704
```

However, lists can be modified because they are mutable objects. The `append()` method doesn't create a new list object; it changes the existing list object. We call this **modifying the object in-place.**

```python
>>> eggs = ['cat', 'dog'] # This creates a new list.  
>>> id(eggs)  
139789337916608 
>>> eggs.append('moose') # append() modifies the list "in place".  
>>> id(eggs) # eggs still refers to the same list as before.  
139789337916608  
>>> eggs = ['bat', 'rat', 'cow'] # This creates a new list, which has a new identity.  
>>> id(eggs) # eggs now refers to a completely different list.  
139789337915136
```

### Passing References

References are particularly important for understanding how arguments get passed to functions. When a function is called, the values of the arguments are copied to the parameter variables. For lists (and dictionaries, which I’ll describe in the next chapter), this means a copy of the reference is used for the parameter.

```python
def eggs(someParameter):  
    someParameter.append('Hello')  
  
spam = [1, 2, 3]  
eggs(spam)  
print(spam)
```

Notice that when `eggs()` is called, a return value is not used to assign a new value to `spam`. Instead, it modifies the list in place, directly. When run, this program produces the following output:

```txt
[1, 2, 3, 'Hello']
```

Even though `spam` and `someParameter` contain separate references, they both refer to the same list. This is why the `append('Hello')` method call inside the function affects the list even after the function call has returned.

Keep this behavior in mind: forgetting that Python handles list and dictionary variables this way can lead to confusing bugs.


### The copy Module's `copy()` and `deepcopy()` Functions

Although passing around references is often the handiest way to deal with lists and dictionaries, if the function modifies the list or dictionary that is passed, you may not want these changes in the original list or dictionary value. For this, Python provides a module named copy that provides both the `copy()` and `deepcopy()` functions. The first of these, `copy.copy()`, can be used to make a duplicate copy of a mutable value like a list or dictionary, not just a copy of a reference.

```python
>>> import copy  
>>> spam = ['A', 'B', 'C', 'D']  
>>> id(spam)  
139789337916608  
>>> cheese = copy.copy(spam)  
>>> id(cheese) # cheese is a different list with different identity.  
139789337915776  
>>> cheese[1] = 42  
>>> spam  
['A', 'B', 'C', 'D']  
>>> cheese  
['A', 42, 'C', 'D']
```

Now the `spam` and `cheese` variables refer to separate lists, which is why only the list in `cheese` is modified when you assign `42` at index `1`.

![](/notes/automate-the-boring-stuff-with-python/lists-6.webp)

**If the list you need to copy contains lists, then use the `copy.deepcopy()` function instead of `copy.copy()` The `deepcopy()` function will these inner lists as well.**

## Projects

There are following project given in the book. Check their code at my [GitHub](https://github.com/abuturabofficial/python-automation-pg/tree/main/section-6-lists).

### A Short Program: Conway's Game of Life

Conway’s Game of Life is an example of cellular automata: a set of rules governing the behavior of a field made up of discrete cells. In practice, it creates a pretty animation to look at. You can draw out each step on graph paper, using the squares as cells. A filled-in square will be “alive” and an empty square will be “dead.” If a living square has two or three living neighbors, it continues to live on the next step. If a dead square has exactly three living neighbors, it comes alive on the next step. Every other square dies or remains dead on the next step.

{{< figure
    src= "/notes/automate-the-boring-stuff-with-python/lists-7.webp"
    caption= "Four steps in a Conway's Game of Life Simulation"
>}}

Even though the rules are simple, there are many surprising behaviors that emerge. Patterns in Conway’s Game of Life can move, self-replicate, or even mimic CPUs. But at the foundation of all of this complex, advanced behavior is a rather simple program.

We can use a list of lists to represent the two-dimensional field. The inner list represents each column of squares and stores a `'#'` hash string for living squares and a `' '` space string for dead squares.

### Comma Code

Say you have a list value like this:

```python
spam = ['apples', 'bananas', 'tofu', 'cats']
```

Write a function that takes a list value as an argument and returns a string with all the items separated by a comma and a space, with `and` inserted before the last item. For example, passing the previous spam list to the function would return `'apples, bananas, tofu, and cats'`. But your function should be able to work with any list value passed to it. Be sure to test the case where an empty list `[]` is passed to your function.

### Coin Flip Streaks

For this exercise, we’ll try doing an experiment. If you flip a coin 100 times and write down an “H” for each heads and “T” for each tails, you’ll create a list that looks like **“T T T T H H H H T T.”** If you ask a human to make up 100 random coin flips, you’ll probably end up with alternating head-tail results like **“H T H T H H T H T T,”** which looks random (to humans), but isn’t mathematically random. A human will almost never write down a streak of six heads or six tails in a row, even though it is highly likely to happen in truly random coin flips. Humans are predictably bad at being random.

Write a program to find out how often a streak of six heads or a streak of six tails comes up in a randomly generated list of heads and tails. Your program breaks up the experiment into two parts: the first part generates a list of randomly selected 'heads' and 'tails' values, and the second part checks if there is a streak in it. Put all of this code in a loop that repeats the experiment 10,000 times so we can find out what percentage of the coin flips contains a streak of six heads or tails in a row. As a hint, the function call `random.randint(0, 1)` will return a `0` value 50% of the time and a `1` value the other 50% of the time.

You can start with the following template:

```python
import random  
numberOfStreaks = 0  
for experimentNumber in range(10000):  
    # Code that creates a list of 100 'heads' or 'tails' values.  
  
    # Code that checks if there is a streak of 6 heads or tails in a row.  
print('Chance of streak: %s%%' % (numberOfStreaks / 100))
```

Of course, this is only an estimate, but 10,000 is a decent sample size. Some knowledge of mathematics could give you the exact answer and save you the trouble of writing a program, but programmers are notoriously bad at math.

### Character Picture Grid

Say you have a list of lists where each value in the inner lists is a one-character string, like this:

```python
grid = [['.', '.', '.', '.', '.', '.'],  
        ['.', 'O', 'O', '.', '.', '.'],  
        ['O', 'O', 'O', 'O', '.', '.'],  
        ['O', 'O', 'O', 'O', 'O', '.'],  
        ['.', 'O', 'O', 'O', 'O', 'O'],  
        ['O', 'O', 'O', 'O', 'O', '.'],  
        ['O', 'O', 'O', 'O', '.', '.'],  
        ['.', 'O', 'O', '.', '.', '.'],  
        ['.', '.', '.', '.', '.', '.']]
```

Think of `grid[x][y]` as being the character at the x- and y-coordinates of a “picture” drawn with text characters. The `(0, 0)` origin is in the upper-left corner, the x-coordinates increase going right, and the y-coordinates increase going down.

Copy the previous grid value, and write code that uses it to print the image.

```txt
..OO.OO..  
.OOOOOOO.  
.OOOOOOO.  
..OOOOO..  
...OOO...  
....O....
```

**Hint**: You will need to use a loop in a loop in order to print `grid[0][0]`, then `grid[1][0]`, then `grid[2][0]`, and so on, up to `grid[8][0]`. This will finish the first row, so then print a newline. Then your program should print `grid[0][1]`, then `grid[1][1]`, then gr`id[2][1]`, and so on. The last thing your program will print is `grid[8][5]`.

Also, remember to pass the `end` keyword argument to `print()` if you don’t want a newline printed automatically after each `print()` call.