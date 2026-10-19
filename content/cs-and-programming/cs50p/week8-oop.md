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

**OOP** stands for **Object-Oriented Programming**.

Python is an object-oriented language, allowing you to structure your code using classes and objects for better organization and re-usability.

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

---

- REF: Python OOP via [W3School](https://www.w3schools.com/python/python_oop.asp)
