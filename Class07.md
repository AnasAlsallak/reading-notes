# Read: Class 07

## Table of Contents

- [Python Scope](#python-scope)
- [Big O notation is simpler than you might think](#big-o-notation-is-simpler-than-you-might-think)
- [Rolling Dice Examples](#rolling-dice-examples)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Python Scope

The topic of variable scope in Python is important in understanding how variables are defined and used in a program. It is particularly relevant to this module as it is fundamental to writing effective and efficient Python code.

In Python, the scope of a variable refers to the part of the program where the variable can be accessed. There are two types of scope in Python: local and global. Local variables are those that are defined within a function or block of code and can only be accessed within that function or block. Global variables, on the other hand, are defined outside of any function or block and can be accessed from any part of the program.

To illustrate the usage of both local and global variables in Python, consider the following example:

    x = 10 # global variable

    def foo():
        y = 5 # local variable
        print(x) # accessing global variable
        print(y) # accessing local variable

    foo() # calling function
    print(x) # accessing global variable

In this example, the global keyword is used to modify the value of the global variable x from within the function foo(). As a result, when foo() is called, x is modified to 5, and when print(x) is called outside of the function, the modified value of x is printed.

The nonlocal keyword in Python is used to access and modify variables defined in the outer scope of a nested function. For example:

    def outer():
        x = 10 # local variable in outer function
        
        def inner():
            nonlocal x
            x = 5 # modifying variable in outer function
            print(x) # accessing variable in outer function
        
        inner() # calling inner function
        print(x) # accessing variable in outer function

    outer() # calling outer function

In this example, the function inner() is nested within the function outer(), and x is defined as a local variable in outer(). The nonlocal keyword is used to modify the value of x from within the nested function inner(). As a result, when inner() is called, x is modified to 5, and when print(x) is called within outer(), the modified value of x is printed.

In summary, variable scope in Python refers to the part of the program where a variable can be accessed. Local variables are defined within a function or block and can only be accessed within that function or block, while global variables are defined outside any function or block and can be accessed from any part of the program. The global and nonlocal keywords are used to access and modify global and non-local variables, respectively, from within a function or nested function.

## Big O notation is simpler than you might think

The video provides an introduction to algorithm analysis and Big O notation. The main topics covered in the video include:

The importance of algorithm efficiency
The basics of algorithm analysis, including time complexity and space complexity
Big O notation and how it measures the worst-case scenario for an algorithm's time complexity
The significance of different orders of growth in Big O notation, including O(1), O(log n), O(n), O(n log n), O(n^2), and O(2^n)
Examples of how to analyze the time complexity of common algorithms, such as linear search and binary search
In my own words, the purpose of Big O notation is to provide a standardized way to measure and compare the efficiency of algorithms. It allows programmers to analyze how the time complexity of an algorithm grows as the size of the input increases, and to identify algorithms that are more efficient for large inputs. This is important because efficient algorithms can save time and resources, and can make programs more scalable and responsive. By using Big O notation, programmers can also communicate about algorithm efficiency in a clear and concise way, and can make informed decisions about which algorithms to use in different contexts.

## Rolling Dice Examples

The webpage provides an introduction to basic programming with Python, including data types, variables, conditional statements, loops, and functions. The program example discussed in section 1.3 is a simple script that generates two random numbers between 1 and 6, representing the roll of two dice, and prints their sum.

To simulate a dice roll using Python, you can use the random module to generate a random integer between 1 and 6, which corresponds to the six possible outcomes of a dice roll. Here is an example code snippet:

    import random

    def roll_dice():
        return random.randint(1, 6)

    # Simulate a dice roll
    dice_roll = roll_dice()

    # Print the result
    print("The dice roll is:", dice_roll)

To calculate the probability of rolling a specific number, such as 6, over a large number of trials, you can use the following code:

import random
import matplotlib.pyplot as plt

def roll_dice():
    return random.randint(1, 6)

    # Initialize the variables
    num_trials = 10000
    num_successes = 0

    # Simulate the dice rolls and count the successes
    for i in range(num_trials):
        if roll_dice() == 6:
            num_successes += 1

    # Calculate the probability
    probability = num_successes / num_trials

    # Print the result
    print("The probability of rolling a 6 is:", probability)

    # Visualize the probabilities
    x_values = [1, 2, 3, 4, 5, 6]
    y_values = [0] * 6
    for i in range(num_trials):
        y_values[roll_dice() - 1] += 1
    plt.bar(x_values, y_values)
    plt.show()

In this example, we use a loop to simulate the dice roll a large number of times (10,000 in this case) and count the number of times a 6 is rolled. We then divide the number of successes by the total number of trials to obtain the probability of rolling a 6. We also use the matplotlib module to visualize the probabilities of all outcomes using a bar chart. This approach can be used to calculate the probability of any other number as well.

## Things I want to know more about

[Move Class 08](./Class08.md) | [Previous](./Class06.md)
