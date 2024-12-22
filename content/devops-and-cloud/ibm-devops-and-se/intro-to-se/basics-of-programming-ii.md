---
title: Programming Languages and Organization
linkTitle: "Basics of Programming II"
date: 2023-05-22 10:39:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 3
---

## **Interpreted and Compiled Programming Languages**

**Interpreted programming:**

![Basics of Programming](/notes/Basics%20of%20Programming%20II.png)

Interpreted programming examples:

![Basics of Programming](/notes/Basics%20of%20Programming%20II-1.png)
  
  **Compiled programming:**
- Programs that you run on your computer
- Packaged or compiled into one file
- Usually larger programs
- Used to help solve more challenging problems, like interpreting source code
  
![Basics of Programming](/notes/Basics%20of%20Programming%20II-2.png)

Compiled programming examples:
- C, C++, and C# are used in many OSs, like MS Windows, Apple macOS and Linux
- Java works well across platforms, like the Android OS

Compiled programming:

![Basics of Programming](/notes/Basics%20of%20Programming%20II-3.png)

## **Comparing Compiled and Interpreted Programming Languages**

**Choosing a programming language:**
  
  Developers determine what programming language is best to use depending on:
- What they are most experienced with and trust
- What is best for their users
- What is the most efficient to use

**Programming languages:**

![Basics of Programming](/notes/Basics%20of%20Programming%20II-4.png)

**Interpreted vs. compiled**

![Basics of Programming](/notes/Basics%20of%20Programming%20II-5.png)

## **Query and Assembly Programming Languages**
  
**Programming language levels:**
  
  High-level programming languages:
- More sophisticated
- Use common English
- SQL, Pascal, Python
  
  Low-level programming languages:
- Use simple symbols to represent machine code
- ARM, MIPS, X86

### Query languages:

- A query is a request for information from a database
- The database searches its tables for information requested and returns results
- Important that both the user application making the query and the database handling the query are speaking the same language
- Writing a query means using predefined and understandable instructions to make the request to a database
- Achieved using programmatic code (query language/database query language)
- Most prevalent database query language is SQL
- Other query languages available:
  - AQL, CQL, Datalog, and DMX

**SQL vs. NoSQL:**
- NoSQL (Not Only SQL)
- Key difference is data structures
- SQL databases:
  - Relational
  - Use structured, predefined schemas
- NoSQL databases:
  - Non-relational
  - Dynamic schemas for unstructured data

**How does a query language work?**

Query language is predominantly used to:
- Request data from a database
- Create, read, update, and delete data in a database (CRUD)
- Database consists of structured tables with multiple row and columns of data
  
When a user performs a query, the database:
1. retrieve data from the table
2. Arranges data into some sort of order
3. Returns and presents query results

**Query statements:**
- Database queries are either:
  - Select commands
  - Action commands (CREATE, INSERT, UPDATE)
- More common to use the term “statement”
- Select queries request data from a database
- Action queries manipulate data in a database
  
  **Common query statements:**
  
![Basics of Programming](/notes/Basics%20of%20Programming%20II-6.png)

query statement examples:

![Basics of Programming](/notes/Basics%20of%20Programming%20II-7.png)

### Assembly Languages

- Less sophisticated than query languages, structured programming languages, and OOP languages
- Uses simple symbols to represent 0s and 1s
- Closely tied to CPU architecture
- Each CPU type has its own assembly language
  
  Assembly language syntax:
- Simple readable format
- Entered one line at a time
- One statement per line
  
  ```assembly
  {lable} mnemonic {operand list} ;{comment}
  ```
  
  ```assembly
  mov TOTAL, 212 ;Transfer the value in the memory variable TOTAL
  ```
  
  **Assemblers:**
- Assembly languages are translated using an assembler instead of a compiler or interpreter
- One statement translates into just one machine code instruction
- Opposite to high-level languages where one statement can be translated into multiple machine code instructions
  
  Translate using mnemonics:
- Input (INP), Output (OUT), Load (LDA), Store (STA), Add (ADD)
  
  Statements consist of:
- Opcodes that tell the CPU what to do with data
- Operands that tell the CPU where to find the data

## **Understanding Code Organization Methods**
  
**Pseudocode vs. flowcharts:**
  
  | Pseudocode                                                              | Flowcharts                                                                |
  | ----------------------------------------------------------------------- | ------------------------------------------------------------------------- |
  | Informal, high-level algorithm description                              | Pictorial representation of algorithm, displays steps as boxes and arrows |
  | Step-by-step sequence of solving a problem                              | Used in designing or documenting a process or program                     |
  | Bridge to project code, follows logic                                   | Good for smaller concepts and problems                                    |
  | Helps programmers share ideas without extraneous waste of creating code | Provide easy method of communication about logic behind concept           |
  | Provides structure that is not dependent on a programming language      | Offer good starting point for project                                     | 
  
  **Flowcharts:**
- Graphical or pictorial representation of an algorithm
- Symbols, shapes, and arrows in different colors to demo a process or program
- Analyze different methods of solving a problem or completing a process
- Standard symbols to highlight elements and relationships
  
![Basics of Programming](/notes/Basics%20of%20Programming%20II-8.png)

Flowchart software:

![Basics of Programming](/notes/Basics%20of%20Programming%20II-9.png)

**Pseudocode:**

![Basics of Programming](/notes/Basics%20of%20Programming%20II-10.png)
  
  **Pseudocode Advantages:**
- Simply explains each line of code
- Focuses more on logic
- Code development stage is easier
- Word/phrases represent lines of computer operations
- Simplifies translation to code
- Code in different computer languages
- Easier review by development groups
- Translates quickly and easily to any computer language
- More concise, easier to modify
- Easier than developing a flowchart
- Usually less than one page

# **Programming Logic and Concepts**

## **Branching and Looping Programming Logic**
  
**Introduction to programming logic:**

![Basics of Programming](/notes/Basics%20of%20Programming%20II-11.png)

**Boolean expressions and variables:**

![Basics of Programming](/notes/Basics%20of%20Programming%20II-12.png)

**Branching programming logic:**
  
  Branching statements allow program execution flow:
- if
- if-then-else
- Switch
- GoTo
  
![Basics of Programming](/notes/Basics%20of%20Programming%20II-13.png)

**Looping programming logic:**

While loop: Condition is evaluated before processing, if true, then loop is executed

For loop: Initial value performed once, condition tests and compares, if false is returned, loop is stopped

Do-while loop: Condition always executed after the body of a loop

![Basics of Programming](/notes/Basics%20of%20Programming%20II-14.png)

## **Introduction to Programming Concepts**

### What are identifiers?

- Software developers use identifiers to reference program components
  - Stored values
  - Methods
  - Interfaces
  - Classes
- Identifiers store two types of data values:
  - Constants
  - Variables

### What are containers?

- Special type of identifiers to reference multiple program elements
  - No need to create a variable for every element
  - Faster and more efficient
  - Ex:
    - To store six numerical integers – create six variables
    - To store 1,000+ integers – use a container
- Arrays and vectors
  
  **Arrays:**
- Simplest type of container
- Fixed number of elements stored in sequential order, starting at zero
- Declare an array
  - Specify data type (int, bool, str)
  - Specify max number of elements it can contain
- Syntax
  - Data type > array name > array size `[]`

  ```array
  int my_array[50]
  ```

**Vectors:**
- Dynamic size
- Automatically resize as elements are added or removed
  - a.k.a. ‘dynamic arrays’
- Take up more memory space
- Take longer to access as not stored in sequential memory
- Syntax
  - Container type/data type in <>/name of array

```vector
vector <int> my_vector;
```

### What are functions?

- Consequence of modular programming software development methodology
  - Multiple modular components
- Structured, stand-alone, reusable code that performs a single specific action
- Some languages refer to them as subroutines, procedures, methods, or modules
  
  Two types:
- Standard library functions – built-in functions
- User-defined functions – you write yourself

### What are objects?

- Objects are key to understanding object-oriented programming (OOP)
- OOP is a programming methodology focused on objects rather than functions
- Objects contain data in the form of properties (attributes) and code in the form of procedures (methods)
- OOP packages methods with data structures
  - Objects operate on their own data structure

![Basics of Programming](/notes/Basics%20of%20Programming%20II-15.png)

Objects in programming
- Consist of states (properties) and behaviors (methods)
- Store properties in fields (variables)
- Expose their behaviors through methods (functions)
