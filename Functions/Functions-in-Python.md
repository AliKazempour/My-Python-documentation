# Functions in Python

Functions are fundamental building blocks in Python, allowing for code modularity, reuse, and organization. This document provides a detailed overview of functions in Python, covering definitions, types, usage, and examples.

## Table of Contents

1. [What is a Function?](#what-is-a-function)
2. [Defining a Function](#defining-a-function)
3. [Function Arguments](#function-arguments)
    - [Positional Arguments](#positional-arguments)
    - [Keyword Arguments](#keyword-arguments)
    - [Default Arguments](#default-arguments)
    - [Arbitrary Arguments](#arbitrary-arguments)
4. [Return Values](#return-values)
5. [Variable Scope](#variable-scope)
6. [Higher-Order Functions](#higher-order-functions)
7. [Lambda Functions](#lambda-functions)
8. [Recursion](#recursion)
9. [Best Practices](#best-practices)

## What is a Function?

A function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusability.

## Defining a Function

In Python, a function is defined using the `def` keyword, followed by the function name and parentheses `()`. Here is a simple example:

```python
def greet(name):
    """Display a greeting message."""
    print(f"Hello, {name}!")

greet("Ali")
```

### Syntax

```python
def function_name(parameters):
    """Docstring"""
    # function body
    return value
```

- `function_name`: A valid identifier for the function.
- `parameters`: Optional; a comma-separated list of parameters.
- `docstring`: Optional; a string that describes the function.
- `return`: Optional; exits the function and optionally passes back a value.

## Function Arguments

Python functions can have various types of arguments, allowing flexibility in how they are called.

### Positional Arguments

Positional arguments are the most straightforward. The order of the arguments passed in the function call must match the order of parameters in the function definition.

```python
def add(x, y):
    return x + y

result = add(2, 3)  # 5
```

### Keyword Arguments

Keyword arguments are specified by the parameter name. This allows you to pass arguments in any order.

```python
def introduce(name, age):
    print(f"My name is {name} and I am {age} years old.")

introduce(age=30, name="Bob")
```

### Default Arguments

Default arguments allow you to specify default values for parameters, which are used if no value is provided.

```python
def greet(name, message="Hello"):
    print(f"{message}, {name}!")

greet("Ali")        # Hello, Ali!
greet("Zahra", "Hi")    # Hi, Zahra!
```

### Arbitrary Arguments

Arbitrary arguments allow you to pass a variable number of arguments to a function. Use `*args` for non-keyword arguments and `**kwargs` for keyword arguments.

```python
def list_friends(*friends):
    print("My friends are:", friends)

list_friends("Alice", "Bob", "Charlie")

def student_info(**info):
    print("Student info:", info)

student_info(name="Alice", age=21, course="Physics")
```

## Return Values

Functions can return values using the `return` statement. If a function does not have a `return` statement, it returns `None` by default.

```python
def square(x):
    return x * x

result = square(4)  # 16
```

## Variable Scope

The scope of a variable determines its visibility within a program. Python has different types of variable scope:

- **Local Scope**: Variables declared inside a function are local to that function.
- **Global Scope**: Variables declared outside of all functions are global and can be accessed anywhere in the file.
- **Nonlocal Scope**: Variables declared inside a nested function but not global or local to the outer function.

```python
x = "global"

def outer():
    x = "local"

    def inner():
        nonlocal x
        x = "nonlocal"
        print("inner:", x)

    inner()
    print("outer:", x)

outer()
print("global:", x)
```

## Higher-Order Functions

A higher-order function is a function that can take another function as an argument or return a function as a result.

### Example with `map()`

```python
def square(x):
    return x * x

numbers = [1, 2, 3, 4]
squared_numbers = map(square, numbers)
print(list(squared_numbers))  # [1, 4, 9, 16]
```

### Example with `filter()`

```python
def is_even(x):
    return x % 2 == 0

numbers = [1, 2, 3, 4, 5, 6]
even_numbers = filter(is_even, numbers)
print(list(even_numbers))  # [2, 4, 6]
```
## Lambda Functions

Lambda functions are small anonymous functions defined with the `lambda` keyword. They can have any number of arguments but only one expression. The expression is evaluated and returned. Lambda functions are often used for short operations or as arguments to higher-order functions.

### Syntax

```python
lambda arguments: expression
```

### Examples

1. **Square a Number**: A simple lambda function to square a number.

    ```python
    square = lambda x: x * x
    print(square(5))  # Output: 25
    ```

2. **Addition**: A lambda function to add two numbers.

    ```python
    add = lambda x, y: x + y
    print(add(3, 4))  # Output: 7
    ```

3. **Filtering with Lambda**: Use a lambda function with `filter()` to extract even numbers from a list.

    ```python
    numbers = [1, 2, 3, 4, 5, 6]
    even_numbers = filter(lambda x: x % 2 == 0, numbers)
    print(list(even_numbers))  # Output: [2, 4, 6]
    ```
4. **Mapping with Lambda**: Use a lambda function with `map()` to double the values in a list.

    ```python
    numbers = [1, 2, 3, 4, 5]
    doubled_numbers = map(lambda x: x * 2, numbers)
    print(list(doubled_numbers))  # Output: [2, 4, 6, 8, 10]
    ```
Lambda functions are useful for short operations and can make your code more concise, especially when used with functions like `map()`, `filter()`, and `sorted()`.

## Recursion

Recursion is a programming technique where a function calls itself. It is often used to solve problems that can be broken down into smaller, similar problems.

Recursion consists of two main parts: the base case and the recursive case. The base case is a condition that is always true, and it is used to terminate the recursion. The recursive case is a condition that is used to solve the problem recursively by calling itself with a smaller input.

Recursion can be used to solve a wide range of problems, such as calculating the factorial of a number, finding the greatest common divisor of two numbers, and traversing a tree.

### Examples

1. **Factorial**: Calculate the factorial of a number using recursion.

    ```python
    def factorial(n):
        if n == 0:
            return 1
        else:
            return n * factorial(n - 1)

    print(factorial(5))  # Output: 120
    ```

2. **Fibonacci Sequence**: Generate the Fibonacci sequence using recursion.

    ```python
    def fibonacci(n):
        if n <= 1:
            return n
        else:
            return fibonacci(n - 1) + fibonacci(n - 2)

    print(fibonacci(6))  # Output: 8
    ```
3. **Power**: Calculate the power of a number using recursion.

    ```python
    def power(base, exponent):
        if exponent == 0:
            return 1
        else:
            return base * power(base, exponent - 1)

    print(power(2, 3))  # Output: 8
    ```
4. **GCD**: Find the greatest common divisor of two numbers using recursion.

    ```python
    def gcd(a, b):
        if b == 0:
            return a
        else:    
            return gcd(b, a % b)

    print(gcd(12, 18))  # Output: 6
    ``` 
5. **binary_search**: Implement a binary search algorithm using recursion.

    ```python
    def binary_search(arr, target, low, high):
        if low > high:
            return -1
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            return binary_search(arr, target, mid + 1, high)
        else:
            return binary_search(arr, target, low, mid - 1)

    arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    target = 7
    index = binary_search(arr, target, 0, len(arr) - 1)
    if index != -1:
        print(f"Element {target} found at index {index}")
    else:
        print(f"Element {target} not found in the array")
    ```
## Best Practices

- **Use meaningful names**: Choose function names that convey the purpose of the function.
- **Keep functions short**: Ideally, functions should do one thing and do it well.
- **Document your functions**: Use docstrings to describe the purpose and usage of your functions.
- **Avoid global variables**: They can lead to code that is difficult to debug and maintain.
- **Leverage built-in functions**: Python provides many built-in functions that can simplify your code.
- **Test your functions**: Write test cases to ensure your functions work correctly.

## Conclusion

Functions are a crucial aspect of Python programming, enabling code modularity, reusability, and clarity. By understanding and leveraging functions, you can write more efficient and maintainable code. This document provides an overview of the key concepts and practices for working with functions in Python.
