---
draft: false
date: "2026-10-19T07:18:40+05:00"
title: "Week 8: Object-Oriented Programming"
linkTitle: "Ojbect-Oriented Programming"
menuPre: ""
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 9
---

| Week 8: Practice Code | [GitHub](https://github.com/abuturabofficial/pythonprac/tree/main/cs50p/week8-oop) |
| :-------------------: | :--------------------------------------------------------------------------------: |

## What is OOP?

> Object-Oriented Programming (OOP) is a programming paradigm that organizes software design around **object** rather than functions and logic.

Let's breakdown the OOP into its reusable building block:

- **Classes**: These are user-defined data types that act as the blueprint for objects, attributes, methods.
- **Objects**: These are instances of a class with specifically defined data. When a class is defined initially, the description is the only object that is defined.
- **Methods**: These are functions that are defined inside a class that describe the behavior of an object. They are useful for re-usability or keeping functionality encapsulated inside one object at a time. Code re-usability is a great benefit when debugging.
- **Attributes**: These are defined in the class template and represent the state of an object. Objects contain data stored in the attribute field.

**OOP** stands for **Object-Oriented Programming**.

Python is an object-oriented language, allowing you to structure your code using classes and objects for better organization and re-usability.

### Principles of OOP

In order for use to write good OOP code, we need to understand the 4 pillars of OOP we should adhere to:

1. **Encapsulation**: Wrapping data and functions into a single unit(object).
2. **Abstraction**: Hiding the implementation details of a class and only showing the essential features to the user.
3. **Inheritance**
4. **Polymorphism**

### Advantages of OOP

- Provides a clear structure to programs
- Makes code easier to maintain, reuse, and debug
- Helps keep your code DRY (Don't Repeat Yourself)
- Allows you to build reusable applications with less code

> [!TIP]
> The DRY principle means you should avoid writing the same code more than once, Move repeated code into functions or classes and reuse it.

### What are Classes and Objects?

Classes and objects are the two core concepts in OOP.

A class defines what an object should look like, and an object si created based on that class. For example:

| Class | Objects              |
| ----- | -------------------- |
| Fruit | Apple, Banana, Mango |
| Car   | Volvo, Audi, Toyota  |

When you create an object from a class, it inherits all the variables and functions defined inside that class.

### Attributes

There are two types of attributes/variable in the classes.

1. **Class Attributes**: Python variables that belong to a class itself, and are shared between all class instances/objects.

2. **Instance Attributes**: Python variables that belong to one object/instance and are only accessible within the object; they are unique to each object and are not shared between class instances.

## Python Classes and Objects

Python is an object-oriented programming language.

Almost everything in Python is an object, with its properties and methods.

A Class is like an object constructor, or a "blueprint" for creating objects.

### Create a Class

To create a class, use the keyword `class`.

Create a class named MyClass, with a property named `x`:

```py
class MyClass:
    x = 5
```

### Create Object

Now we can use the class named `MyClass` to create objects.

Create an object named `p1`, and print the value of x:

```py
p1 = MyClass()
print(p1.x)
```

### Delete Objects

You can delete objects by using the `del` keyword.

Delete the p1 object:

```py
del p1
```

### Multiple Objects

You can create multiple objects from the same class:

Create three objects from the MyClass class:

```py
p1 = MyClass()
p2 = MyClass()
p3 = MyClass()

print(p1.x)
print(p2.x)
print(p3.x)
```

> [!NOTE]
> Each object is independent and has its own copy of the class properties.

### The `pass` Statement

`class` definitions cannot be empty, but if you for some reason have a `class` definition with no content, put in the `pass` statement to avoid getting an error.

```py
class Person:
    pass
```

## Python `__init__()` Method

> [!TIP]
> The functions inside classes are called **Methods**.

### The `__init_()` Method

All classes have a built-in method called `__init__()`, which is always executed when the class is being initiated.

The `__init__()` method is used to assign values to object properties, or to perform operations that are necessary when the object is being created.

#### Example

Create a class named Person, use the `__init__()` method to assign values for name and age:

```py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

p1 = Person("Email", 36)

print(p1.name)
print(p1.age)
```

> [!NOTE]
> The `__init__()` method is called automatically every time the class is being used to create a new object.

### Why Use `__init__()`?

Without the `__init__()` method, you would need to set properties manually for each object:

```py
class Person:
    pass

p1 = Person()
p1.name = "Tobias"
p1.age = 25

print(p1.name)
print(p1.age)
```

Using `__init__()` makes it easier to create object with initial values.

### Default Values in `__init__()`

You can also set default values for parameters in the **init**() method.

```py
class Person:
    def __init__(self, name, age=18):
        self.name = name
        self.age = age

p1 = Person("Emil")
p2 = Person("Tobias", 25)

print(p1.name, p1.age)
print(p2.name, p2.age)
```

### Multiple Parameters

The `__init__()` method can have as many parameters as you need:

```py
class Person:
  def __init__(self, name, age, city, country):
    self.name = name
    self.age = age
    self.city = city
    self.country = country

p1 = Person("Linus", 30, "Oslo", "Norway")

print(p1.name)
print(p1.age)
print(p1.city)
print(p1.country)
```

## Python Self Parameter

The `self` parameter is a reference ot the current instance of the class.

It is used to access properties and methods that belong to the class.

Use `self` to access class properties:

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def greet(self):
    print("Hello, my name is " + self.name)

p1 = Person("Emil", 25)
p1.greet()
```

> [!NOTE]
> The `self` parameter must be the first parameter of any method in the class.

### Why Use `self`?

Without `self`, Python would not know which object's properties you want to access.

The `self` parameter links the method to the specific object:

```py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print("Hello, my name is " + self.name)


p1 = Person("Emil", 25)
p1.greet()
```

### `self` Does Not Have to Be Named "self"

It doesn't have to be named `self`, you can call it whatever you like, but it has to be the first parameter of any method in the class.

> [!NOTE]
> While you can use a different name, it is strongly recommended to use `self` as it is the convention in Python and makes your code more readable to others.

### Calling Methods with `self`

You can also call other methods within the class using `self`.

Call one method from another method using `self`:

```py
class Person:
  def __init__(self, name):
    self.name = name

  def greet(self):
    return "Hello, " + self.name

  def welcome(self):
    message = self.greet()
    print(message + "! Welcome to our website.")

p1 = Person("Tobias")
p1.welcome()
```

## Python Magic Methods

Magic methods are special methods whose names start and end with double underscores, like `__init__()` and `__str__()`. Because of the double underscores, they are also called **Dunder methods** (short for "double underscore").

You don't call magic methods directly. Python calls them for you, automatically, in certain situations - like when an object is created, printed, or compared to another object.

> [!NOTE]
> `__init__()` runs automatically when an object is created, and `__str__()` runs automatically when the object is printed.

#### List of Magic methods

![](/notes/cs50p/week8-oop-3.webp)

### The `__str__()` Method

The `__str__()` method is a special method that controls what is returned when the object is printed.

Without the `__str__()` method, printing an object shows its memory address:

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("Emil", 36)
print(p1)
```

![](/notes/cs50p/week8-oop-1.webp)

With the `__str__()` method, you can control what is shown when an object is printed:

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def __str__(self):
    return f"{self.name} ({self.age})"

p1 = Person("Tobias", 36)
print(p1)
```

![](/notes/cs50p/week8-oop-2.webp)

> [!WARNING]
> `__str__()` must return a `string`. If it returns anything else, Python raises a `TypeError`.

## `@classmethod`

In Python, `@classmethod` is a built-in decorator used to define a method that is bound to the class itself rather than a specific object instance.

Unlike regular instance methods, a class method doesn't have access to `self`(the instance). Instead, it implicitly receives the class object as its first argument, which is conventionally named `cls`.

## Inheritance

Inheritance allows us to define a class that inherits all the methods and properties from another class.

**Parent class** is the class being inherited from, also called base class.

**Child class** is the class that inherits from another class, also called derived class.

Exceptions in Python are an example of class inheritance.
![](/notes/cs50p/week8-oop-4.webp)

## Operator Overloading

Magic methods can control what happens when you use an operator, like `+`, on your own objects. This is called **operator overloading**.

> Operator overloading refers to the ability to redefine the behavior of built-in operators for user-defined classes. In other words, you can "teach" Python how to evaluate expressions like `a+b` when `a` and `b` are instances of a custom class. ---Leapcell.io

Python achieves this by mapping operators to special methods, also known as **dunder methods** (short for "double underscores). For example:

- `+` corresponds to `__add__`
- `-` corresponds to `__sub__`
- `*` corresponds to `__mul__`
- `/` corresponds to `__truediv__`
- `==` corresponds to `__eq__`
- `<` corresponds to `__lt__`

By defining these methods in your class, you can control how objects behave when used with those operators.

### Best Practices

1. **Keep operations intuitive**: Only overload operators where it makes logical sense.
2. **Return new instances**: Avoid mutating existing instances unless that's the intended behavior.
3. **Ensure compatibility**: Always handle edge cases and validate types when performing operations.

### The `__add__()` Method

Use `__add__()` to add the `age` of two `Person` objects together:

```py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __add__(self, other):
        return self.age + other.age

p1 = Person("Emil", 22)
p2 = Person("Tobias", 19)

print(p1+p2)
```

> [!NOTE]
> Without `__add__()`, writing `p1+p2` would raise a `TypeError`, since Python wouldn't know how to add two `Person` objects.

---

# References

- OOP Meaning – What is Object-Oriented Programming? via [freeCodeCamp.org](https://www.freecodecamp.org/news/what-is-object-oriented-programming/)
- Python OOP via [W3School](https://www.w3schools.com/python/python_oop.asp)
- Understanding Operator Overloading in Python via [Leapcell.io](https://leapcell.io/blog/understanding-operator-overloading-in-python)
- Lecture 8 : OOPS in Python | Object Oriented Programming | Classes & Objects | Python Full Course [Urdu/Hindi] via [Shradha Khapra](https://www.youtube.com/watch?v=HeW-D6KpDwY)
- Lecture 9 : OOPS Part 2 | Object Oriented Programming | Python Full Course [Urdu/Hindi] via [Shradha Khapra](https://www.youtube.com/watch?v=bAwmZVJeO5s)
- Python Object Oriented Programming (OOP) - For Beginners [English] via [Tech with Tim](https://www.youtube.com/watch?v=JeznW_7DlB0)
- Python Attributes: Class vs. Instance Explained via [builtin.com](https://builtin.com/software-engineering-perspectives/python-attributes)
