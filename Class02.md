# Read: Class 02

## Table of Contents

- [In Tests We Trust — TDD with Python](#in-tests-we-trust--tdd-with-python)
- [What does the if __name__ == “__main__”: do?](#second-topic)
- [Introduction to Recursion – Data Structure and Algorithm Tutorials](#introduction-to-recursion--data-structure-and-algorithm-tutorials)
- [Python Modules and Packages: An Introduction](#python-modules-and-packages-an-introduction)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## In Tests We Trust — TDD with Python

The key principles of Test-Driven Development (TDD) in Python are:

1. Writing tests before writing code
2. Writing only enough code to make the tests pass
3. Refactoring the code to improve its design and maintainability

These principles contribute to the overall quality of code in several ways.

Firstly, by writing tests before writing code, developers have a clear understanding of what their code is supposed to do. This helps to prevent bugs and ensures that the code meets the requirements.

Secondly, by writing only enough code to make the tests pass, developers avoid overcomplicating their code and keep it simple. This results in code that is easier to read, maintain, and modify.

Finally, by refactoring the code to improve its design and maintainability, developers ensure that their code is clean, easy to understand, and follows best practices. This reduces technical debt and makes the code easier to maintain over time.

Overall, TDD principles help developers to write code that is reliable, maintainable, and of high quality.

___

## Second Topic

### What does the if __name__ == “__main__”: do?

The if __name__ == "__main__": statement in Python scripts is used to check whether the script is being run as the main program or if it is being imported as a module into another program.

The purpose of using this statement is to ensure that certain code blocks, such as test code or setup code, are only executed when the script is run as the main program. This can help to avoid unexpected side effects when the script is imported into other programs.

Some use cases for including the if __name__ == "__main__": statement in your code include:

Defining and running tests for the module
Setting up the module for use, such as configuring environment variables or initializing data structures
Providing a command-line interface for the module
Overall, the if __name__ == "__main__": statement is a common convention in Python programming that helps to control the behavior of a module depending on whether it is being run as the main program or imported as a module.

In summary, the if __name__ == "__main__": statement in Python scripts is used to check whether the script is being run as the main program or imported as a module. Including this statement in your code can help to ensure that certain code blocks are only executed when the script is run as the main program, and can help to avoid unexpected side effects when the script is imported into other programs. Some use cases for including this statement in your code include defining and running tests, setting up the module, and providing a command-line interface.

___

## Introduction to Recursion – Data Structure and Algorithm Tutorials

Recursion is a programming technique in which a function calls itself in order to solve a problem. The basic idea is to break down a problem into smaller, simpler sub-problems that can be solved recursively. The function continues to call itself with smaller input values until it reaches a base case, which is a condition that does not require further recursive calls. At this point, the function returns a result, which is used to solve the original problem.

In Python, recursion is implemented using a function that calls itself. When the function is called, it checks if the input satisfies the base case. If so, the function returns a result. If not, the function calls itself with a smaller input value, and the process continues until the base case is reached.

The "Introduction to Recursion – Data Structure and Algorithm Tutorials" article from "GeeksforGeeks" provides an introduction to the concept of recursion in computer programming. The article explains the principles of recursion and provides several examples of recursive functions in Python, including the factorial function, the Fibonacci sequence, and the Tower of Hanoi problem. The article also discusses the advantages and disadvantages of recursion, as well as some common mistakes to avoid when writing recursive functions.

In summary, recursion is a programming technique in which a function calls itself in order to solve a problem. It is implemented in Python using a function that checks for a base case and calls itself with smaller input values until the base case is reached. The "Introduction to Recursion – Data Structure and Algorithm Tutorials" article from "GeeksforGeeks" provides a helpful introduction to recursion in Python, including examples of recursive functions and best practices for writing recursive code.

___

## Python Modules and Packages: An Introduction

Python modules and packages are two related but distinct concepts in Python. A module is a single file containing Python code, while a package is a collection of modules that are organized in a hierarchical directory structure.

To create a Python module, you simply create a Python file with the .py extension and include the code you want to reuse in other programs. To use the module in another Python file, you can import it using the import statement and then use the functions, classes, or variables defined in the module.

To create a package, you need to create a directory that contains an empty file named init.py. This file serves as the initialization file for the package and can contain Python code that will be executed when the package is imported. The package directory can then contain one or more Python module files, which can be organized into subdirectories to create a hierarchical structure.

To use a module from a package, you can use the dot notation to specify the path to the module within the package, as in import package.module.

The "Python Modules and Packages: An Introduction" article from Real Python provides a detailed introduction to both modules and packages in Python. It explains the differences between them and provides examples of how to create and use both modules and packages. The article covers advanced topics such as relative imports, namespace packages, and distribution of packages using PyPI.

In summary, Python modules and packages are two important concepts in Python that allow you to organize and reuse your code. Modules are single files containing Python code, while packages are collections of modules organized in a hierarchical directory structure. To create, import, and use them, you need to follow specific syntax and naming conventions, which are explained in the article.

## Things I want to know more about

[Move to SQL Practice](./SQLPractice.md) | [Previous](./Class01.md)
