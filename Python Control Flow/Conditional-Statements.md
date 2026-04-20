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

## `match-case` (Structural Pattern Matching)
Starting from Python 3.10, Python introduced a powerful construct called `match-case`, which serves a similar purpose to `switch-case` in other languages—but with significantly more capabilities.

### 1. Basic Usage (Switch Replacement)
```python
command = "start"

match command:
    case "start":
        print("System is starting...")
    case "stop":
        print("System is stopping...")
    case "restart":
        print("System is restarting...")
    case _:
        print("Unknown command")

```
This is the most switch-like usage.
The underscore `_` acts as a default case.

### 2. Matching Multiple Values (Cleaner Than Many `elif`)

```python
day = 6

match day:
    case 1 | 2 | 3 | 4 | 5:
        print("Weekday")
    case 6 | 7:
        print("Weekend")

```
The `|` operator means `or`.

### 3. Matching Data Structures (Real Power)
This is where `match-case` becomes more powerful than traditional `switch` statements.
```python
event = ("click", 200, 350)

match event:
    case ("click", x, y):
        print(f"Mouse clicked at ({x}, {y})")
    case ("drag", x, y):
        print(f"Dragging from ({x}, {y})")
    case ("scroll", amount):
        print(f"Scrolled by {amount}")
    case _:
        print("Unknown event")

```
This is called destructuring patterns.This is far beyond classic `switch-case`.

### 4. Pattern Matching with Guards (Additional Conditions)
Guards allow conditional logic inside a pattern.
```python
age = 17

match age:
    case n if n < 0:
        print("Invalid age")
    case n if n < 18:
        print("Minor")
    case n if n >= 18:
        print("Adult")

```
### 5. Combining Structure + Guards
```python
reading = ("Tehran", 32)

match reading:
    case (city, temp) if temp >= 40:
        print(f"{city}: Extremely hot!")
    case (city, temp) if temp >= 30:
        print(f"{city}: Hot weather.")
    case (city, temp) if temp >= 20:
        print(f"{city}: Mild temperature.")
    case (city, temp):
        print(f"{city}: Cold weather.")

```
## Conclusion

Conditional statements are essential for controlling the flow of a Python program. They allow your code to make decisions and execute different actions depending on specific conditions.
Using `if`, `elif`, and `else`, you can create clear decision paths in your programs. Logical operators like `and`, `or`, and `not` help combine conditions, while nested conditionals allow more complex logic when needed.
In addition, Python’s `match-case` structure  provides a powerful way to match values and data structures, making certain types of decision logic cleaner and easier to read.
Together, these tools enable you to build programs that react intelligently to data, user input, and different runtime situations.

