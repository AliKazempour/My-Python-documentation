# Error Handling and Custom Errors in Python

**Error Handling** in Python is a way to manage unexpected problems (errors or exceptions) that might occur while your program runs. Instead of crashing, you can "catch" these errors and handle them gracefully. **Custom Errors** let you define your own error types to make your code more specific and meaningful.

---

## Table of Contents

1. [Introduction to Error Handling](#1-introduction-to-error-handling)
2. [Core Concepts of Error Handling](#2-core-concepts-of-error-handling)
   - [Exceptions](#21-exceptions)
   - [Try and Except](#22-try-and-except)
   - [Else and Finally](#23-else-and-finally)
   - [Raising Exceptions](#24-raising-exceptions)
   - [Custom Exceptions](#25-custom-exceptions)
3. [Syntax of Try-Except](#3-syntax-of-try-except)
4. [Built-in Exceptions](#4-built-in-exceptions)
5. [Creating Custom Exception Classes](#5-creating-custom-exception-classes)
6. [Best Practices](#6-best-practices)
7. [Problems and Practice](#7-problems-and-practice)
8. [Summary](#8-summary)

---

## 1. Introduction to Error Handling

Imagine you’re writing a program to divide two numbers, but the user enters "0" as the divisor. Without error handling, your program crashes with a "division by zero" error. Error handling lets you catch that mistake and respond—like telling the user, "Hey, you can’t divide by zero!" Custom errors take this further by letting you create specific error types, like `TooBigError` for numbers over a limit.

### Why Use Error Handling?
- **Prevent Crashes**: Keep your program running despite issues.
- **User-Friendly**: Show helpful messages instead of scary errors.
- **Control Flow**: Decide what happens when things go wrong.
- **Debugging**: Identify and manage problems systematically.

---

## 2. Core Concepts of Error Handling

Let’s explore the key ideas of error handling with examples you might encounter in everyday coding.

---

### 2.1 Exceptions

- **Exception**: An error that stops your program unless handled (e.g., dividing by zero, opening a nonexistent file).

#### Detailed Explanation:
Think of exceptions as alarms. When something goes wrong—like trying to access a list item that doesn’t exist—Python "raises" an exception to alert you.

#### Example 1: Basic Exception
```python
numbers = [1, 2, 3]
print(numbers[5])  # IndexError: list index out of range
```

#### Example 2: Division Error
```python
result = 10 / 0  # ZeroDivisionError: division by zero
```

---

### 2.2 Try and Except

- **Try and Except**: A way to "try" risky code and "catch" errors if they happen.

#### Detailed Explanation:
It’s like putting a safety net under a tightrope walker. The `try` block holds the risky code, and the `except` block catches the fall (error).

#### Example 1: Division Safety
```python
try:
    num = int(input("Enter a number to divide 10 by: "))
    result = 10 / num
    print(f"Result: {result}")
except ZeroDivisionError:
    print("You can’t divide by zero!")
# Output (if input is 0): You can’t divide by zero!
```

#### Example 2: List Access
```python
try:
    items = ["apple", "banana"]
    index = int(input("Enter an index: "))
    print(items[index])
except IndexError:
    print("That index doesn’t exist!")
# Output (if input is 3): That index doesn’t exist!
```

---

### 2.3 Else and Finally

- **Else**: Runs if no error occurs in `try`.
- **Finally**: Runs no matter what—error or not.

#### Detailed Explanation:
`Else` is like a reward for success, while `finally` is a cleanup crew that always shows up.

#### Example 1: Full Structure
```python
try:
    num = int(input("Enter a number: "))
    result = 100 / num
except ValueError:
    print("Please enter a valid number!")
except ZeroDivisionError:
    print("Can’t divide by zero!")
else:
    print(f"Success! Result is {result}")
finally:
    print("Thanks for using the program!")
# Output (if input is 5): Success! Result is 20.0, Thanks for using the program!
```

#### Example 2: File Handling
```python
try:
    file = open("data.txt", "r")
except FileNotFoundError:
    print("File not found!")
else:
    print(file.read())
    file.close()
finally:
    print("Done with file operations.")
```

---

### 2.4 Raising Exceptions

- **Raising**: Manually triggering an exception when something’s wrong.

#### Detailed Explanation:
Think of it as sounding your own alarm—like rejecting a negative age in a form.

#### Example 1: Age Check
```python
age = int(input("Enter your age: "))
if age < 0:
    raise ValueError("Age can’t be negative!")
print(f"You are {age} years old.")
# Output (if input is -5): ValueError: Age can’t be negative!
```

#### Example 2: Password Length
```python
password = input("Enter a password (min 6 chars): ")
if len(password) < 6:
    raise Exception("Password too short!")
print("Password accepted!")
```

---

### 2.5 Custom Exceptions

- **Custom Exceptions**: Your own error types, defined as classes.

#### Detailed Explanation:
Built-in errors like `ValueError` are general. Custom exceptions let you be specific—like `OverdrawnError` for a bank account going negative.

#### Example 1: Bank Balance
```python
class OverdrawnError(Exception):
    pass

balance = 50
withdraw = int(input("How much to withdraw? "))
if withdraw > balance:
    raise OverdrawnError("Can’t withdraw more than balance!")
balance -= withdraw
print(f"New balance: {balance}")
# Output (if input is 60): OverdrawnError: Can’t withdraw more than balance!
```

#### Example 2: Temperature Limit
```python
class TooHotError(Exception):
    pass

temp = int(input("Enter temperature in Celsius: "))
if temp > 100:
    raise TooHotError("Temperature too high for safety!")
print(f"Temperature recorded: {temp}°C")
```

---

## 3. Syntax of Try-Except

Here’s the basic structure:
```python
try:
    # Code that might fail
except ExceptionType:
    # Handle that specific error
else:
    # Run if no error
finally:
    # Always run this
```

---

## 4. Built-in Exceptions

| Exception           | When It Happens                       | Example                  |
|---------------------|---------------------------------------|--------------------------|
| `ValueError`        | Wrong value type                     | `int("abc")`            |
| `ZeroDivisionError` | Division by zero                     | `10 / 0`                |
| `IndexError`        | List index out of range              | `lst[10]` (small list)  |
| `FileNotFoundError` | File doesn’t exist                   | `open("nope.txt")`      |
| `TypeError`         | Wrong operation for type             | `"2" + 3`               |

---

## 5. Creating Custom Exception Classes

Custom exceptions are classes that inherit from `Exception`. Add details for clarity.

#### Example 1: Detailed Custom Error
```python
class InsufficientFundsError(Exception):
    def __init__(self, amount, balance):
        self.amount = amount
        self.balance = balance
        self.message = f"Tried to withdraw {amount}, but only {balance} available."
        super().__init__(self.message)

balance = 100
withdraw = 150
if withdraw > balance:
    raise InsufficientFundsError(withdraw, balance)
# Output: InsufficientFundsError: Tried to withdraw 150, but only 100 available.
```

#### Example 2: Student Grade Error
```python
class InvalidGradeError(Exception):
    def __init__(self, grade):
        self.grade = grade
        self.message = f"Grade {grade} is invalid (must be 0-100)."
        super().__init__(self.message)

grade = int(input("Enter grade: "))
if grade < 0 or grade > 100:
    raise InvalidGradeError(grade)
print(f"Grade {grade} recorded.")
```

---

## 6. Best Practices

- **Specificity**: Catch specific exceptions (`ValueError`) instead of all (`Exception`).
- **Minimal Try**: Keep `try` blocks small—only the risky code.
- **Informative Messages**: Use clear error messages for users and debugging.
- **Clean Up**: Use `finally` for resources like files or connections.
- **Custom When Needed**: Create custom exceptions for unique cases, not everything.

---

## 7. Problems and Practice

### Problem 1: Safe Division Calculator
```python
def divide_safe():
    try:
        a = float(input("Enter numerator: "))
        b = float(input("Enter denominator: "))
        result = a / b
    except ZeroDivisionError:
        print("Error: Division by zero!")
    except ValueError:
        print("Error: Enter numbers only!")
    else:
        print(f"Result: {result}")
    finally:
        print("Calculation attempt complete.")

divide_safe()
```

### Problem 2: Custom Error for Age Limit
```python
class TooYoungError(Exception):
    def __init__(self, age):
        self.message = f"Age {age} is too young (must be 13+)."
        super().__init__(self.message)

age = int(input("Enter your age: "))
if age < 13:
    raise TooYoungError(age)
print("Welcome to the club!")
```

### Problem 3: File Reader with Error Handling
```python
def read_file(filename):
    try:
        with open(filename, "r") as file:
            content = file.read()
    except FileNotFoundError:
        print(f"Error: {filename} not found!")
    else:
        print("File contents:", content)
    finally:
        print("File operation finished.")

read_file("test.txt")
```

---

## 8. Summary

| Concept             | What It Does                                      | Example                       |
|---------------------|--------------------------------------------------|-------------------------------|
| **Exceptions**      | Errors that disrupt normal flow                  | `10 / 0` → `ZeroDivisionError` |
| **Try-Except**      | Catches and handles errors                       | Catch division by zero        |
| **Else-Finally**    | Runs on success or always                        | Cleanup after file read       |
| **Raising**         | Triggers errors manually                         | Reject negative age           |
| **Custom Exceptions**| Defines specific error types                     | `OverdrawnError` for bank     |

