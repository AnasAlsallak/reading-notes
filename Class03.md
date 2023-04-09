# Read: Class 03: FileIO & Exceptions

## Table of Contents

- [Read & Write Files in Python](#read-and-write-files-in-python)
- [Exceptions in Python](#exceptions-in-python)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Read and Write Files in Python

1. What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?

2. Explain the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. Provide examples of when to use each method.

As a software development student, it is crucial to understand file handling in Python. Reading and writing files is a common task in programming, and Python provides several methods for handling files.

When opening a file, it's important to manage resources efficiently to avoid any issues with data integrity or resource leaks. The with statement in Python is used to simplify this process. It creates a context in which the file is opened, and after the block of code is executed, the file is automatically closed. This helps ensure that resources are properly managed and avoids any issues with resource leaks.

Python provides several methods for reading the contents of a file, including read() and readline(). The read() method reads the entire contents of the file and returns it as a string. On the other hand, the readline() method reads one line at a time and returns it as a string.

Here are some examples of when to use each method:

        # Using read()
        with open('example.txt', 'r') as f:
            content = f.read()
            print(content)

        # Using readline()
        with open('example.txt', 'r') as f:
            line = f.readline()
            while line:
                print(line)
                line = f.readline()

In the first example, we use the read() method to read the entire contents of the file and print it to the console. In the second example, we use the readline() method to read one line at a time and print each line to the console.

In conclusion, managing file resources and understanding file handling methods such as read() and readline() is crucial in software development. The with statement is a convenient way to manage file resources while reading and writing files, and using the appropriate method for reading file contents can make your code more efficient and easier to read.
___

## Exceptions in Python

As a software developer, it's essential to understand how to handle exceptions in your Python code. An exception is an error that occurs during the execution of a program, and Python provides a way to handle these exceptions gracefully using the try, except, and finally blocks.

The try block is used to enclose the code that might raise an exception. If an exception occurs, the code inside the try block will be stopped, and the code inside the except block will be executed instead. The except block can handle specific exceptions by specifying the type of exception it should catch.

The finally block is optional and is used to specify code that should be executed regardless of whether an exception was raised or not. It is often used to close files, databases, or other resources that were opened in the try block.

In conclusion, exception handling is an important concept in Python, and using the try, except, and finally blocks can help you handle exceptions gracefully and ensure proper execution of your code. By properly handling exceptions, you can write more robust and reliable software.

## Things I want to know more about

[Move Class 04](./Class04.md) | [Previous](./EngineeringReadings.md)
