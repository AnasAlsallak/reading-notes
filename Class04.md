# Read: Class 04

## Table of Contents

- [Question one](#question-one)
- [Question two](#question-two)
- [Question three](#question-three)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Question one

What are the key differences between classes and objects in Python, and how are they used to create and manage instances of a class?

In Python, classes and objects are fundamental concepts in object-oriented programming (OOP). Classes are basically blueprints for creating objects, whereas objects are instances of those classes.

The key difference between classes and objects is in their attributes and methods. Classes define the attributes and methods that are mutual to all instances created of that class. Whereas, objects are instances of those classes that have their own unique attributes and methods.

If you want to create an instance of a class, use the class constructor, that is a special method called __init__() that initializes the attributes of the object. We can then access and modify the attributes of the object using the dot notation.

Classes and objects are used to encapsulate related data and functions into a single entity, making it easier to manage and organize code and reuse it. They are especially useful in bigger projects where it is important to maintain code structure and modularity.

## Question two

Explain the concept of recursion and provide an example of how it can be used to solve a problem in Python. What are some best practices following when implementing a recursive function?

Recursion is a powerful problem-solving technique in computer programming that involves a function calling itself repeatedly until a certain base case is reached. This approach breaks complex problems down into simpler subproblems, making it easier to solve them.

For example, in Python, we can use recursion to find the factorial of a number. The factorial of a number is the product of all integers starting from 1 up to the number itself. We can create a recursive function that calls itself with the argument being one less than the previous argument until it reaches the base case of 1.

When implementing a recursive function, there are some best practices to keep in mind. It's essential to include a base case that will end the recursion and ensure that the recursion is making progress towards the base case. It's also important to have a clear understanding of the problem and how the recursive solution will be implemented. Additionally, it's critical to ensure that the recursive call is correctly structured, and return values are appropriately utilized.

Overall, recursion is a valuable technique for solving complex problems, and following these best practices can help ensure that our code is efficient and effective. As software development students, we should be familiar with these concepts and use them to write robust and maintainable code.

## Question three

What is the purpose of pytest fixtures and code coverage in testing Python code? Explain how they can be used together to improve the quality and maintainability of a project.

In software development, testing is an essential part of the development process. It helps ensure that the code is functional and meets the requirements. Two important concepts in Python testing are pytest fixtures and code coverage.

Pytest fixtures are functions that provide a fixed baseline for a test. They are used to setting up and tear down test fixtures and provide a way to share objects between tests. Fixtures can be used for various purposes such as creating test data, initializing database connections, and configuring application settings.

Code coverage, on the other hand, is a metric used to measure the percentage of code that is executed during testing. It helps identify untested code and areas of the codebase that require more tests.

Using pytest fixtures and code coverage together can improve the quality and maintainability of a project. Fixtures ensure that tests are repeatable and reduce duplication of code. Code coverage provides visibility into untested code, allowing developers to identify and address gaps in testing. By writing tests that cover a significant portion of the codebase, developers can ensure that the code is well-tested and less likely to have bugs or regressions.

In conclusion, pytest fixtures and code coverage are powerful tools that can help improve the quality and maintainability of a project. They provide a way to set up and tear down test fixtures, share objects between tests, and measure the percentage of code executed during testing. By using these concepts together, developers can ensure that their code is well-tested and less likely to have bugs or regressions.

## Things I want to know more about

[Move Class 05](./Class05.md) | [Previous](./Class04.md)