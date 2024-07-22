# Conditional Statements in Python

Conditional statements in Python allow you to execute different blocks of code based on certain conditions. These are fundamental in controlling the flow of your program.

## `if` Statement

The `if` statement is used to test a specific condition. If the condition is true, the code block following the `if` statement is executed.

```python
x = 10
if x > 5:
    print("x is greater than 5")
```

### Syntax

```python
if condition:
    # code block
```

### Example

```python
age = 18
if age >= 18:
    print("You are eligible to vote.")
```

## `else` Statement

The `else` statement is used to execute a block of code if the condition in the `if` statement is false.

```python
x = 3
if x > 5:
    print("x is greater than 5")
else:
    print("x is 5 or less")
```

### Syntax

```python
if condition:
    # code block
else:
    # code block
```

### Example

```python
age = 16
if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

## `elif` Statement

The `elif` statement stands for "else if" and allows you to check multiple conditions sequentially. It executes the code block associated with the first condition that is true.

```python
x = 7
if x > 10:
    print("x is greater than 10")
elif x > 5:
    print("x is greater than 5 but less than or equal to 10")
else:
    print("x is 5 or less")
```

### Syntax

```python
if condition1:
    # code block
elif condition2:
    # code block
else:
    # code block
```

### Example

```python
marks = 85
if marks >= 90:
    print("Grade: A")
elif marks >= 80:
    print("Grade: B")
elif marks >= 70:
    print("Grade: C")
else:
    print("Grade: D or below")
```

## Nested Conditional Statements

You can nest conditional statements inside other conditional statements to check multiple conditions.

```python
x = 15
if x > 10:
    print("x is greater than 10")
    if x > 20:
        print("x is also greater than 20")
    else:
        print("x is not greater than 20")
```

### Syntax

```python
if condition1:
    # code block
    if condition2:
        # nested code block
    else:
        # nested code block
else:
    # code block
```

### Example

```python
number = 25
if number % 2 == 0:
    print("The number is even.")
    if number % 5 == 0:
        print("The number is also divisible by 5.")
    else:
        print("The number is not divisible by 5.")
else:
    print("The number is odd.")
```

## Logical Operators in Conditional Statements

You can combine multiple conditions using logical operators `and`, `or`, and `not`.

### `and` Operator

Both conditions must be true.

```python
x = 15
if x > 10 and x < 20:
    print("x is between 10 and 20")
```

### `or` Operator

At least one condition must be true.

```python
x = 5
if x < 10 or x > 20:
    print("x is either less than 10 or greater than 20")
```

### `not` Operator

Negates the condition.

```python
x = 15
if not x > 20:
    print("x is not greater than 20")
```

## The `pass` Statement

The `pass` statement is a null operation; nothing happens when it executes. It can be used as a placeholder for future code.

```python
x = 10
if x > 5:
    pass  # TODO: Implement this block later
else:
    print("x is 5 or less")
```

### Example

```python
age = 20
if age >= 18:
    pass  # Later we'll implement the voting logic here
else:
    print("You are not eligible to vote.")
```

## Conclusion

Conditional statements are crucial in controlling the flow of your Python programs. They allow you to execute different code blocks based on specific conditions, making your programs more dynamic and functional. By mastering `if`, `elif`, and `else` statements, along with logical operators and nested conditions, you can handle complex decision-making processes in your code.


