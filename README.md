# Python Basics

> A beginner-friendly guide to Python programming fundamentals — from setup to writing your first programs.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Variables and Data Types](#variables-and-data-types)
4. [Operators](#operators)
5. [Control Flow](#control-flow)
6. [Loops](#loops)
7. [Functions](#functions)
8. [Data Structures](#data-structures)
9. [Modules and Imports](#modules-and-imports)
10. [File Handling](#file-handling)
11. [Error Handling](#error-handling)
12. [Object-Oriented Programming](#object-oriented-programming)

---

## Introduction

Python is a high-level, interpreted, general-purpose programming language known for its clean and readable syntax. It is widely used in web development, data science, automation, artificial intelligence, and more.

**Why Python?**

- Easy to read and write
- Large standard library
- Huge community and ecosystem
- Cross-platform (Windows, macOS, Linux)
- Great for beginners and professionals alike

---

## Getting Started

### Installation

Download Python from [https://www.python.org/downloads/](https://www.python.org/downloads/)

Verify installation:

```bash
python --version
```

### Hello World

```python
print("Hello, World!")
```

### Running a Script

```bash
python script.py
```

---

## Variables and Data Types

Variables store data. Python is dynamically typed — no need to declare types.

```python
# Strings
name = "Alice"

# Integers
age = 25

# Floats
height = 5.7

# Booleans
is_student = True

# NoneType
result = None

# Check the type
print(type(name))    # <class 'str'>
print(type(age))     # <class 'int'>
print(type(height))  # <class 'float'>
```

### String Operations

```python
first = "Hello"
last = "World"

# Concatenation
print(first + " " + last)   # Hello World

# Repetition
print(first * 3)             # HelloHelloHello

# f-strings (recommended)
print(f"My name is {name} and I am {age} years old.")

# String methods
print(name.upper())          # ALICE
print(name.lower())          # alice
print(name.replace("A", "E")) # Elice
print(len(name))             # 5
```

---

## Operators

```python
# Arithmetic
print(10 + 3)   # 13
print(10 - 3)   # 7
print(10 * 3)   # 30
print(10 / 3)   # 3.333...
print(10 // 3)  # 3  (floor division)
print(10 % 3)   # 1  (modulus)
print(10 ** 3)  # 1000 (exponent)

# Comparison
print(5 == 5)   # True
print(5 != 4)   # True
print(5 > 3)    # True
print(5 < 3)    # False

# Logical
print(True and False)  # False
print(True or False)   # True
print(not True)        # False
```

---

## Control Flow

### if / elif / else

```python
score = 75

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
else:
    print("Grade: F")
```

### Ternary Expression

```python
status = "Pass" if score >= 60 else "Fail"
print(status)  # Pass
```

---

## Loops

### for Loop

```python
# Iterating over a range
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Iterating over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### while Loop

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

### Loop Control

```python
for i in range(10):
    if i == 3:
        continue   # Skip 3
    if i == 7:
        break      # Stop at 7
    print(i)
```

---

## Functions

```python
# Defining a function
def greet(name):
    return f"Hello, {name}!"

# Calling a function
print(greet("Alice"))   # Hello, Alice!

# Default parameters
def greet(name="World"):
    return f"Hello, {name}!"

print(greet())           # Hello, World!

# Multiple return values
def min_max(numbers):
    return min(numbers), max(numbers)

lo, hi = min_max([3, 1, 4, 1, 5, 9])
print(lo, hi)  # 1 9

# Lambda (anonymous function)
square = lambda x: x ** 2
print(square(4))   # 16
```

---

## Data Structures

### Lists

```python
numbers = [1, 2, 3, 4, 5]

numbers.append(6)       # Add to end
numbers.insert(0, 0)    # Insert at index
numbers.remove(3)       # Remove by value
numbers.pop()           # Remove last item
print(numbers[0])       # Access by index
print(numbers[-1])      # Last element
print(numbers[1:4])     # Slicing
```

### Tuples (immutable)

```python
point = (10, 20)
x, y = point   # Unpacking
print(x, y)    # 10 20
```

### Dictionaries

```python
person = {
    "name": "Alice",
    "age": 25,
    "city": "Lahore"
}

print(person["name"])          # Alice
person["email"] = "a@b.com"   # Add key
del person["city"]             # Delete key

for key, value in person.items():
    print(f"{key}: {value}")
```

### Sets

```python
unique = {1, 2, 3, 3, 4}
print(unique)    # {1, 2, 3, 4} — duplicates removed

unique.add(5)
unique.discard(1)

a = {1, 2, 3}
b = {3, 4, 5}
print(a & b)     # {3}  — intersection
print(a | b)     # {1, 2, 3, 4, 5} — union
```

---

## Modules and Imports

```python
# Built-in modules
import math
print(math.sqrt(16))    # 4.0
print(math.pi)          # 3.14159...

import random
print(random.randint(1, 10))

import datetime
print(datetime.date.today())

# Import specific items
from math import sqrt, pi
print(sqrt(25))

# Alias
import numpy as np   # (third-party, install via pip)
```

### Installing Packages

```bash
pip install requests
pip install numpy
pip install pandas
```

---

## File Handling

```python
# Writing to a file
with open("output.txt", "w") as f:
    f.write("Hello, file!\n")
    f.write("Second line.\n")

# Reading a file
with open("output.txt", "r") as f:
    content = f.read()
    print(content)

# Reading line by line
with open("output.txt", "r") as f:
    for line in f:
        print(line.strip())

# Appending to a file
with open("output.txt", "a") as f:
    f.write("Appended line.\n")
```

---

## Error Handling

```python
# try / except
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")

# Multiple exceptions
try:
    value = int("abc")
except ValueError as e:
    print(f"ValueError: {e}")
except Exception as e:
    print(f"Unexpected error: {e}")

# finally block (always runs)
try:
    f = open("data.txt")
except FileNotFoundError:
    print("File not found.")
finally:
    print("Done.")

# Raising exceptions
def divide(a, b):
    if b == 0:
        raise ValueError("Divisor cannot be zero.")
    return a / b
```

---

## Object-Oriented Programming

```python
# Defining a class
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def speak(self):
        return f"{self.name} makes a sound."

    def __str__(self):
        return f"{self.name} ({self.species})"


# Inheritance
class Dog(Animal):
    def __init__(self, name):
        super().__init__(name, "Dog")

    def speak(self):
        return f"{self.name} says Woof!"


# Using the classes
dog = Dog("Rex")
print(dog)           # Rex (Dog)
print(dog.speak())   # Rex says Woof!
```

---

## Quick Reference

| Concept        | Syntax Example                     |
|----------------|------------------------------------|
| Variable       | `x = 10`                           |
| List           | `items = [1, 2, 3]`                |
| Dictionary     | `d = {"key": "value"}`             |
| Function       | `def func(arg): return arg`        |
| Loop           | `for i in range(n):`               |
| Condition      | `if x > 0: ...`                    |
| Import         | `import math`                      |
| Class          | `class MyClass:`                   |
| Exception      | `try: ... except Error:`           |
| File           | `with open("f.txt") as f:`         |

---

## Resources

- [Official Python Docs](https://docs.python.org/3/)
- [Python Tutorial](https://docs.python.org/3/tutorial/)
- [Real Python](https://realpython.com/)
- [W3Schools Python](https://www.w3schools.com/python/)

---

> Made with love for Python beginners. Happy coding!
