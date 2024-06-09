---
layout: post
title:  "Understanding Accessor and Mutator Methods in Python"
date:   2024-06-10 04:10:19 +0600
author: "Mamun"
categories: python
---
When working with objects in Python, you'll often encounter situations where you need to access or modify the internal data of an object. To achieve this, Python provides two types of methods: **accessors** and **mutators**. Let's explore what these methods are and how they differ, along with detailed explanations of the code examples provided.

## Accessor Methods (Read-Only)

### What Are Accessor Methods?
Accessor methods allow you to retrieve information about an object's state without altering that state. They provide read-only access to the internal data of an object. Typically, accessor methods are named with the prefix "get" (e.g., `get_value()`).

### Use Cases for Accessor Methods:
- Retrieving the value of an attribute (e.g., getting the length of a list).
- Calculating derived values (e.g., computing the area of a shape based on its dimensions).

### Example: Accessor Methods
Let's create a `Person` class with accessor methods to get the person's name and age:

```python
class Person:
    def __init__(self, name, age):
        self._name = name
        self._age = age

    def get_name(self):
        return self._name

    def get_age(self):
        return self._age

# Usage
john = Person('John', 30)
print(john.get_name())  # Output: John
print(john.get_age())   # Output: 30
```

#### Detailed Explanation:
1. **Class Definition:**
   - The `Person` class is defined with an `__init__` method, which is the constructor method. This method initializes the instance variables `_name` and `_age` when an object of the class is created.

2. **Accessor Methods:**
   - `get_name` and `get_age` methods are defined to return the values of `_name` and `_age`, respectively. These methods do not modify the state of the object; they only return information about it.

3. **Object Creation and Usage:**
   - An instance of the `Person` class, `john`, is created with the name "John" and age 30.
   - The `get_name` method is called on the `john` object, returning "John".
   - The `get_age` method is called on the `john` object, returning 30.

## Mutator Methods (Update Methods)

### What Are Mutator Methods?
Mutator methods modify an object's state by changing the internal data. They allow you to update the values of attributes. Typically, mutator methods are named with the prefix "set" (e.g., `set_value()`).

### Use Cases for Mutator Methods:
- Changing the value of an attribute (e.g., updating the speed of a car).
- Adding or removing elements from a collection (e.g., appending an item to a list).

### Example: Mutator Methods
Continuing with our `Person` class, let's add mutator methods to set the person's name and age:

```python
class Person:
    def __init__(self, name, age):
        self._name = name
        self._age = age

    def get_name(self):
        return self._name

    def get_age(self):
        return self._age

    def set_name(self, new_name):
        self._name = new_name

    def set_age(self, new_age):
        if new_age >= 0:  # Ensuring the age is non-negative
            self._age = new_age
        else:
            print("Age cannot be negative")

# Usage
john = Person('John', 30)
print(john.get_name())  # Output: John
john.set_name('Johnny')
print(john.get_name())  # Output: Johnny
john.set_age(35)
print(john.get_age())   # Output: 35
john.set_age(-5)        # Output: Age cannot be negative
```

#### Detailed Explanation:
1. **Class Definition:**
   - The `Person` class is expanded to include mutator methods `set_name` and `set_age`.

2. **Accessor Methods:**
   - `get_name` and `get_age` methods remain unchanged and continue to provide read-only access to the object's data.

3. **Mutator Methods:**
   - `set_name` method allows updating the `_name` attribute of the `Person` object.
   - `set_age` method allows updating the `_age` attribute. It includes a check to ensure that the new age is non-negative, maintaining a valid state for the object.

4. **Object Creation and Usage:**
   - The `john` object is created with the initial values "John" and 30.
   - The `set_name` method is called to change the name to "Johnny". The `get_name` method then confirms the change.
   - The `set_age` method is called to change the age to 35. The `get_age` method confirms this change.
   - An attempt to set a negative age results in an error message, demonstrating the validation logic in the `set_age` method.

## Summary
- **Accessor methods** provide read-only access to an object's data.
- **Mutator methods** allow you to modify an object's state.
- Choose the appropriate method based on whether you need to retrieve information or update it.

Accessor and mutator methods help maintain encapsulation by controlling how internal data is accessed and modified. Use them wisely in your Python classes! 🐍🔍

---

### Sources:
1. [Accessor and Mutator Methods in Python - GeeksforGeeks](https://www.geeksforgeeks.org/accessor-and-mutator-methods-in-python/)
2. [Classes and Objects - Florida State University](https://ww2.cs.fsu.edu/~nienaber/teaching/python/lectures/classes.html)
3. [Accessor and Mutator Methods in Python - Online Tutorials Library](https://www.tutorialspoint.com/accessor-and-mutator-methods-in-python)
4. [What is the difference between accessor and mutator methods?](https://stackoverflow.com/questions/9627093/what-is-the-difference-between-accessor-and-mutator-methods)
5. [Accessor & Mutator methods (Python) - Stack Overflow](https://stackoverflow.com/questions/15867664/accessor-mutator-methods-python)
