# Python Loops Documentation

## Table of Contents

1. [Introduction](#1-introduction)
2. [Types of Loops in Python](#2-types-of-loops-in-python)
   - [while Loop](#while-loop)
   - [for Loop](#for-loop)
3. [Loop Control Statements](#3-loop-control-statements)
   - [break Statement](#break-statement)
   - [continue Statement](#continue-statement)
   - [pass Statement](#pass-statement)
4. [Nested Loops](#4-nested-loops)
5. [Looping Techniques](#5-looping-techniques)
6. [List Comprehensions](#6-list-comprehensions)
7. [Conclusion](#7-conclusion)

## 1. Introduction

Loops are a fundamental concept in programming that allow you to execute a block of code repeatedly. Python provides two types of loops: `while` loops and `for` loops. In addition, Python offers several control statements that modify the behavior of loops, such as `break`, `continue`, and `pass`.

## 2. Types of Loops in Python

### while Loop

The `while` loop executes a block of code as long as a specified condition is true. It is useful when the number of iterations is not known beforehand.

**Syntax:**

```python
while condition:
    # Code to execute
```

**Example:**

```python
count = 0
while count < 5:
    print("Count is:", count)
    count += 1
```

**Explanation:**

In this example, the loop will continue to execute as long as `count` is less than 5. Each iteration prints the current value of `count` and then increments it by 1.

### for Loop

The `for` loop is used to iterate over a sequence (such as a list, tuple, dictionary, set, or string) and execute a block of code for each item in the sequence.

**Syntax:**

```python
for item in sequence:
    # Code to execute
```

**Example:**

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print("Fruit:", fruit)
```

**Explanation:**

In this example, the loop iterates over the list of fruits and prints each fruit.

#### Looping with `range()`

The `range()` function generates a sequence of numbers, which is useful for iterating a specific number of times.

**Example:**

```python
for i in range(5):
    print("Number:", i)
```

**Explanation:**

In this example, the loop iterates over the numbers 0 through 4, printing each number.

## 3. Loop Control Statements

Loop control statements change the execution of a loop from its normal sequence. Python provides three loop control statements: `break`, `continue`, and `pass`.

### break Statement

The `break` statement terminates the loop immediately, regardless of the loop's condition.

**Example:**

```python
for i in range(10):
    if i == 5:
        break
    print("Number:", i)
```

**Explanation:**

In this example, the loop will stop executing when `i` equals 5.

### continue Statement

The `continue` statement skips the rest of the code inside the loop for the current iteration and jumps to the next iteration.

**Example:**

```python
for i in range(10):
    if i % 2 == 0:
        continue
    print("Odd number:", i)
```

**Explanation:**

In this example, the loop will skip the even numbers and print only the odd numbers.

### pass Statement

The `pass` statement does nothing and is used as a placeholder for future code.

**Example:**

```python
for i in range(10):
    if i % 2 == 0:
        pass  # Placeholder for future code
    else:
        print("Odd number:", i)
```

**Explanation:**

In this example, the `pass` statement is used as a placeholder for code that has yet to be written.

## 4. Nested Loops

Nested loops are loops inside other loops. The inner loop will be executed one time for each iteration of the outer loop.

**Example:**

```python
for i in range(3):
    for j in range(3):
        print(f"i={i}, j={j}")
```

**Explanation:**

In this example, the inner loop will execute three times for each iteration of the outer loop, resulting in a total of nine iterations.

## 5. Looping Techniques

Python provides several techniques for iterating over sequences, such as `enumerate()`, `zip()`, and `items()`.

### Using `enumerate()`

The `enumerate()` function adds a counter to an iterable and returns it as an `enumerate` object.

**Example:**

```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(f"Index: {index}, Fruit: {fruit}")
```

**Explanation:**

In this example, `enumerate()` is used to iterate over the list of fruits while keeping track of the index of each fruit.

### Using `zip()`

The `zip()` function combines two or more iterables and returns an iterator of tuples.

**Example:**

```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

for name, age in zip(names, ages):
    print(f"Name: {name}, Age: {age}")
```

**Explanation:**

In this example, `zip()` is used to iterate over the `names` and `ages` lists in parallel.

### Using `items()`

The `items()` method returns a view object that displays a list of a dictionary's key-value tuple pairs.

**Example:**

```python
person = {"name": "Alice", "age": 25, "city": "New York"}

for key, value in person.items():
    print(f"{key}: {value}")
```

**Explanation:**

In this example, `items()` is used to iterate over the key-value pairs in the dictionary.

## 6. List Comprehensions

List comprehensions provide a concise way to create lists. They consist of brackets containing an expression followed by a `for` clause, then zero or more `for` or `if` clauses.

**Example:**

```python
squares = [x**2 for x in range(10)]
print(squares)  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

**Explanation:**

In this example, the list comprehension creates a list of the squares of numbers from 0 to 9.

List comprehensions can also include conditions.

**Example:**

```python
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares)  # Output: [0, 4, 16, 36, 64]
```

**Explanation:**

In this example, the list comprehension creates a list of the squares of even numbers from 0 to 9.

## 7. Conclusion

Loops are a fundamental concept in programming that allow you to execute a block of code repeatedly. Python provides two types of loops: `while` loops and `for` loops, as well as several loop control statements to modify the behavior of loops. By understanding and using loops effectively, you can write more efficient and powerful Python code.
