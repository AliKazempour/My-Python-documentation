# Python Variables Documentation

## Table of Contents

1. Introduction to Variables
2. Variable Naming Conventions
3. Assigning Values to Variables
4. Variable Types
5. Working with Variables
6. Variable Scope
7. Constants in Python
8. Best Practices
9. Conclusion

## 1. Introduction to Variables

Variables are fundamental to programming and are used to store data that can be manipulated and retrieved later. In Python, variables are dynamically typed, meaning you don't need to declare their type explicitly.

## 2. Variable Naming Conventions

### Rules

1. Variable names must start with a letter (a-z, A-Z) or an underscore (\_).
2. The rest of the name can contain letters, digits (0-9), and underscores.
3. Variable names are case-sensitive (e.g., `age` and `Age` are different).

### Best Practices

- Use descriptive names (e.g., `age`, `first_name`, `total_amount`).
- Use lowercase letters, separating words with underscores (snake_case).

## 3. Assigning Values to Variables

Variables are assigned values using the `=` operator.

```python
# Example of variable assignment
age = 20
name = "Ali"
is_student = True
```

You can also assign multiple variables in one line.

```python
a, b, c = 1, 2, 3
```

## 4. Variable Types

Python variables can hold values of different data types, including:

- **Integers**: Whole numbers (e.g., `42`, `-3`)
- **Floats**: Decimal numbers (e.g., `3.14`, `-0.001`)
- **Strings**: Text (e.g., `"Hello, World!"`, `'Zahra'`)
- **Booleans**: True or False values (`True`, `False`)
- **Lists**: Ordered collections (e.g., `[1, 2, 3]`)
- **Tuples**: Immutable ordered collections (e.g., `(1, 2, 3)`)
- **Dictionaries**: Key-value pairs (e.g., `{"name": "Ali", "age": 20}`)
- **Sets**: Unordered collections of unique elements (e.g., `{1, 2, 3}`)

### Example:

```python
integer_var = 10
float_var = 10.5
string_var = "Hello Ali!"
boolean_var = True
list_var = [1, 2, 3]
tuple_var = (1, 2, 3)
dict_var = {"key": "value"}
set_var = {1, 2, 3}
```

## 5. Working with Variables

### Reassigning Variables

Variables can be reassigned to new values of the same or different types.

```python
x = 5
x = "Now I'm a string 😁"
```

### Type Checking and Conversion

- Use the `type()` function to check the type of a variable.
- Use type conversion functions (`int()`, `float()`, `str()`, `list()`, etc.) to convert between types.

```python
x = 10
print(type(x))  # Output: <class 'int'>

x = str(x)
print(type(x))  # Output: <class 'str'>
```

### Operations with Variables

You can perform operations on variables depending on their type.

```python
# Arithmetic operations
a = 10
b = 5
print(a + b)  # Output: 15
print(a - b)  # Output: 5
print(a * b)  # Output: 50
print(a / b)  # Output: 2.0

# Comparison operations
c = 10
d = 5
print(c > d)  # Output: True
print(c < d)  # Output: False
print(c == d)  # Output: False
print(c != d)  # Output: True

# Logical operations
e = True
f = False
print(e and f)  # Output: False
print(e or f)  # Output: True
print(not e)  # Output: False

# String concatenation
str1 = "Hello"
str2 = "Peter"
print(str1 + " " + str2)  # Output: Hello Peter

# List operations
list1 = [1, 2, 3]
list2 = [4, 5]
print(list1 + list2)  # Output: [1, 2, 3, 4, 5]
```

## 6. Variable Scope

The scope of a variable determines where it can be accessed.

### Local Scope

Variables defined inside a function are local to that function.

```python
def my_function():
    local_var = 10
    print(local_var)

my_function()
# print(local_var)  # This would raise an error
```

### Global Scope

Variables defined outside of functions are global and can be accessed anywhere in the module.

```python
global_var = 20

def my_function():
    print(global_var)

my_function()
print(global_var)  # Accessible here as well
```

## 7. Constants in Python

Python doesn't have built-in constant types, but conventionally, constants are written in all uppercase letters.

```python
PI = 3.14159
MAX_CONNECTIONS = 100
```

## 8. Best Practices

- Use meaningful variable names.
- Stick to the naming conventions.
- Keep the scope of variables as small as possible.
- Use constants for values that should not change.
- Avoid using Python reserved words for variable names (e.g., `class`, `def`, `return`).

## 9. Conclusion

Understanding and using variables effectively is fundamental to programming in Python. Variables allow you to store, manipulate, and retrieve data, making your code more dynamic and flexible. By following best practices and understanding variable scope, you can write more readable and maintainable code.
