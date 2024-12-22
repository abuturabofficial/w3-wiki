---
title: "Python Data Structures"
date: 2023-09-23 09:49:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 2
---

## Tuples

- Tuples are an ordered sequence
- Here is a Tuple “Ratings”
- Tuples are written as comma-separated elements within parentheses
- Tuples concatenation is possible
- Tuple slicing is also possible
- Tuples are immutable
- If one want to manipulate tuples, they have to create a new tuple with the desired values
- **Tuples nesting** (tuple containing another tuple) is also possible
  
  ```py
  Ratings = (10, 9, 6, 5, 10, 8, 9, 6, 2)
  ```
  
  ![Python data Structures](/notes/Python%20Data%20Structures.png)
  
  ![Python data Structures](/notes/Python%20Data%20Structures-1.png)
  
  ![Python data Structures](/notes/Python%20Data%20Structures-2.png)
  
  ![Python data Structures](/notes/Python%20Data%20Structures-3.png)
  
  ![Python data Structures](/notes/Python%20Data%20Structures-4.png)
  
  ![Python data Structures](/notes/Python%20Data%20Structures-5.png)

## Lists

- Lists are also ordered in sequence
- Here is a List “L”
  
  ```py
  L = ["Michael Jackson", 10.1, 1982]
  ```

- A List is represented with square brackets
- List is **mutable**
- List can nest other lists and tuples
- We can combine lists
- List can be extended with `extend()` method
- `append.()` adds only one element to the List, if we append `L.append([1,2,3,4])`, the List “L” will be:
  
  ```py
  L = ["Michael Jackson", 10.1, 1982,[1,2,3,4]]
  ```

- The method `split()` can convert the string into the List
  
  ```py
  "Hello, World!".split()
  ```

- The `split()` can be used with a delimiter we would like to split on as an argument
  
  ```py
  "A,B,C,D".split(",")
  ```

- Multiple names referring to the same object is known as **aliasing**
  
![Python data Structures](/notes/Python%20Data%20Structures-6.png)

- We can clone the list, where both lists will be of their independent copies
- So changing List “A”, will not change List “B”
  
![Python data Structures](/notes/Python%20Data%20Structures-7.png)

## Dictionaries
  
![Python data Structures](/notes/Python%20Data%20Structures-8.png)

- Dictionaries are denoted with curly Brackets {}
- The keys have to be immutable and unique
- The values can be immutable, mutable and duplicates
- Each key and value pair is separated by a comma
  
![Python data Structures](/notes/Python%20Data%20Structures-9.png)

## Sets

- Sets are a type of collection
  - This means that like lists and tuples you can input different python types
- Unlike lists and tuples they are unordered
  - This means sets don’t record element position
- Sets only have unique elements
  - This means there is only one of a particular element in a set

### Sets: Creating a Set
  
![Python data Structures](/notes/Python%20Data%20Structures-10.png)

- You can convert a list into set
  
  ```py
  List = ['foo']
  set(List)
  ```

- To add elements to the set, `set.add('foo')`
- To remove an element, `set.remove(‘foo’)`
- To check if an element is present in the set:
  
  ```py
  'foo' in set
  True/False
  ```

### Sets: Mathematical Expression

- To find the intersection of the sets elements present in the both sets), `set1 & set2` or `set1.intersection(set2)`
  
![Python data Structures](/notes/Python%20Data%20Structures-11.png)

- Union of the sets, contain elements of both the sets combined, `set1.union(set2)`
- To find the difference of sets:
  
  ```py
  #set1 difference from set2
  set1.difference(set2)
  #set2 difference from set 1
  set2.difference(set1)
  ```
  
![Python data Structures](/notes/Python%20Data%20Structures-12.png)

- To find is a set is a subset/superset (have all the elements of other set), `set1.issubset/issuperset(set2)
