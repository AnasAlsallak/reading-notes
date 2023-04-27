# Read: Class 08

## Table of Contents

- [List Comprehensions in Python](#list-comprehensions-in-python)
- [Primer on Python Decorators](#primer-on-python-decorators)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## List Comprehensions in Python

List comprehension is a concise way to create lists in Python. It allows us to create a new list by applying an expression to each item in an existing list or sequence. The syntax for list comprehension consists of square brackets enclosing an expression followed by a for clause and zero or more for or if clauses.

The basic syntax for Python list comprehension is as follows:

    new_list = [expression for item in iterable if condition]

Here, expression is the operation that is applied to each item in the iterable based on the condition (if specified).

Using a list comprehension is often more concise and readable than using a for loop to create a list. It eliminates the need to define a new list and append each element to it one by one, which can be more cumbersome and less efficient.

For example, let's say we have a list of integers and we want to create a new list that contains the square of each element. We can achieve this using a list comprehension in the following way:

    original_list = [1, 2, 3, 4, 5]
    squared_list = [x**2 for x in original_list]

This code generates a new list squared_list that contains the square of each element in the original list.

In contrast, using a for loop to achieve the same result would look like this:

    original_list = [1, 2, 3, 4, 5]
    squared_list = []
    for x in original_list:
        squared_list.append(x**2)

This code creates an empty list squared_list, iterates through the original_list, squares each element, and appends the squared value to squared_list.

Overall, list comprehension provides a more concise and readable way to create new lists in Python.

## Primer on Python Decorators

A decorator in Python is a function that takes another function as input and extends or modifies the behavior of the latter function without changing its source code. In other words, a decorator wraps a function in another function and enhances its functionality or behavior. Decorators provide a way to modify or extend the behavior of functions or classes in a flexible and reusable manner, without requiring major changes to their code.

Decorators are commonly used in Python to add new features to existing functions, such as caching, logging, profiling, input validation, authentication, or debugging. They can be applied to single functions or to an entire class, and can be chained together to create complex behaviors. Decorators are also a key concept in many popular Python web frameworks, such as Flask or Django, where they are used to add functionality to views or routes.

Here's an example of a simple decorator in Python:

    def my_decorator(func):
        def wrapper():
            print("Before the function is called.")
            func()
            print("After the function is called.")
        return wrapper

    @my_decorator
    def say_hello():
        print("Hello!")

    say_hello()

In this example, the my_decorator() function is defined to take a function func as input, and return a new function wrapper that adds some extra behavior before and after calling func. The @my_decorator syntax is used to apply the my_decorator() function to the say_hello() function, effectively replacing the latter with the decorated version of itself.

When the say_hello() function is called, the decorator adds the Before the function is called. and After the function is called. messages to the output, surrounding the original Hello! message. This shows how the decorator can modify the behavior of a function without changing its source code.

## Things I want to know more about

[Move Class 09](./Class09.md) | [Previous](./Class07.md)
