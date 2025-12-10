# Object Oriented Programming (Overview)

Object Oriented Programming (OOP) is a way of structuring programs around **objects**: bundles of data *and* the functions (methods) that work specifically with that data. Instead of keeping related pieces of data in separate variables, OOP lets you combine them. This makes programs easier to organize, extend, and cooperate on with others.

This page gives an overview of the most universal ideas behind classes and objects in Python, and shows you how to implement the very basics.

## Terminology

Before working with classes, it helps to know the terminology that Python (and most other languages) use when talking about objects. The list below summarizes the essential ideas:

- **Class**: a detailed description (a blueprint) of a specific type of object. A class contains the code that defines what that type of object looks like and how it behaves. You can create multiple separate objects from the same class.

- **Object** or **Instance**: a specific realization of a class. An object contains its own data and methods, and has its own internal state.

- **Attribute** or **Field**: a value stored within an object. Objects often contain several attributes that together describe their state.

- **Self**: an internal reference to the current instance of the class. When you write methods inside a class, `self` allows those methods to access or modify *that specific object’s* own attributes.

- **Method**: a function defined inside a class. Methods operate on individual instances of that class and can use `self` to read or update attributes.

- **Initializer**: a special method that runs automatically when creating a new object. In Python this method is called `__init__`. It can receive parameters so that new objects start with specific attribute values.

- **Data class**: a class that only stores attributes, with an initializer that fills them in when creating a new object.

## Classes in Python

To define a class, use the `class` keyword, followed by an initializer and any methods you want the object to have.

    class Example:
        def __init__(self, a, b):
            # usually, we use the same names for values and attributes
            self.a = a
            self.b = b

            # but feel free to do something completely different!
            self.dinosaur = a + b

        def describe(self):
            """
            This method accesses attributes using self,
            and then returns a formatted string.
            """
            return f"a = {self.a}, b = {self.b}"

To then use a class, first create an instance

    x = Example(10, 20)

The `__init__()` method is called automatically when you create an instance of a class. Its first parameter, `self`, refers to the newly created object. You can then store data inside the object by assigning values to a named attribute within `self`. Inside any method of the class, we can then access the values stored within that attribute for a specific object using `self.<attribute_name>`. You can even access this data outside the class.

    print(x.dinosaur)   # accessing an attribute outside the class
    print(x.describe()) # calls the method on the instance x
