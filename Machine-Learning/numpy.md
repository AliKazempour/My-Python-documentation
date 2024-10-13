In this work, we develop a machine learning algorithm capable
of predicting base editing outcomes of commonly used ABEs and
CBEs on any given protospacer sequence in silico available via# NumPy Documentation

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Creating Arrays](#creating-arrays)
4. [Array Indexing and Slicing](#array-indexing-and-slicing)
5. [Array Operations](#array-operations)
6. [Broadcasting](#broadcasting)
7. [Mathematical Functions](#mathematical-functions)
8. [Linear Algebra](#linear-algebra)
9. [Random Module](#random-module)
10. [Reshaping and Resizing](#reshaping-and-resizing)
11. [Aggregations](#aggregations)
12. [Useful Tips](#useful-tips)
13. [Conclusion](#conclusion)

---

## Introduction

**NumPy** (Numerical Python) is a powerful library for numerical computations in Python. It provides support for:

- Multidimensional arrays (`ndarray`)
- Mathematical functions to operate on arrays
- Linear algebra, Fourier transform, and random number generation.

NumPy is widely used in data science, machine learning, and scientific computing due to its efficiency in handling large datasets.

## Installation

To install NumPy, use `pip`:

```bash
pip install numpy
```

Import it into your Python scripts as:

```python
import numpy as np
```

## Creating Arrays

NumPy arrays can be created using lists, tuples, or with special functions.

### Using Lists

```python
import numpy as np

# Creating a 1D array
arr1 = np.array([1, 2, 3, 4, 5])
print(arr1) # Output: [1 2 3 4 5]

# Creating a 2D array
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print(arr2) # Output: [[1 2 3] [4 5 6]]
```

### Using Built-in Functions

- **`np.zeros()`**: Creates an array filled with zeros.

```python
zeros = np.zeros((2, 3))
print(zeros) # Output: [[0. 0. 0.] [0. 0. 0.]]
```

- **`np.ones()`**: Creates an array filled with ones.

```python
ones = np.ones((3, 2))
print(ones) # Output: [[1. 1.][1. 1.][1. 1.]]
```

- **`np.arange()`**: Creates an array with evenly spaced values.

```python
arr = np.arange(0, 10, 2)  # Start at 0, end before 10, step 2
print(arr)  # Output: [0 2 4 6 8]
```

- **`np.linspace()`**: Creates an array with specified number of evenly spaced values between a start and end.

```python
linspace = np.linspace(0, 1, 5)  # 5 values between 0 and 1
print(linspace)  # Output: [0.  0.2 0.4 0.6 0.8]
```

## Array Indexing and Slicing

### Indexing

```python
arr = np.array([10, 20, 30, 40, 50])

# Access the first element
print(arr[0]) # Output: 10

# Access the last element
print(arr[-1]) # Output: 50
```

### Slicing

```python
arr = np.array([0, 10, 20, 30, 40, 50])

# Slicing from index 1 to 4 (not inclusive)
print(arr[1:4])  # Output: [10 20 30]

# Slicing with a step
print(arr[::2])  # Every second element
# Output: [ 0 20 40]
```

### Multi-dimensional Indexing

```python
arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Access the element at row 1, column 2
print(arr2d[1, 2])  # Output: 6

# Slice subarray (first 2 rows, first 2 columns)
print(arr2d[:2, :2])  # Output: [[1 2][4 5]]
```

## Array Operations

NumPy allows element-wise operations on arrays, making computations simple and efficient.

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# Element-wise addition
print(a + b) # Output: [5 7 9]

# Element-wise subtraction
print(a - b) # Output: [-3 -3 -3]

# Element-wise multiplication
print(a * b) # Output: [4 10 18]

# Element-wise division
print(a / b) # Output: [0.25 0.4 0.5]

# Scalar multiplication
print(a * 2) # Output: [2 4 6]
```

## Broadcasting

**Broadcasting** allows NumPy to work with arrays of different shapes when performing arithmetic operations.

```python
a = np.array([1, 2, 3])
b = 2

# Broadcasting 'b' to match the shape of 'a'
print(a + b) # Output: [3 4 5]
```

For more complex examples:

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
b = np.array([1, 2, 3])

# Broadcasting 'b' to each row of 'a'
print(a + b) # Output: [[2 4 6] [5 7 9]]
```

## Mathematical Functions

NumPy provides various functions to perform element-wise mathematical operations.

```python
a = np.array([1, 4, 9, 16])

# Square root
print(np.sqrt(a)) # Output: [1 2 3 4]

# Exponential (e^x)
print(np.exp(a)) # Output: [ 2.71828183 54.59815003 8103.08392758 81057.38401569]

# Logarithm
print(np.log(a)) # Output: [0.        1.38629436 2.19722458 2.77258872]

# Trigonometric functions
angles = np.array([0, np.pi / 2, np.pi])
print(np.sin(angles)) # Output: [0.00000000e+00  1.00000000e+00 -1.22464680e-16]
```

## Linear Algebra

NumPy supports a range of linear algebra functions.

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# Matrix multiplication
print(np.dot(A, B)) # Output: [[19 22][43 50]]

# Transpose
print(A.T) # Output: [[1 3][2 4]]

# Determinant
print(np.linalg.det(A)) # Output: -2

# Inverse
print(np.linalg.inv(A)) # Output: [[-2.  3.][ 1. -1.]]
```

## Random Module

The `np.random` module allows generation of random numbers.

```python
# Random floats between 0 and 1
random_floats = np.random.random(5)
print(random_floats) # Output: [0. 0. 0. 0. 0.]

# Random integers between 0 and 10
random_ints = np.random.randint(0, 10, size=5)
print(random_ints) # Output: [8 5 7 7 6]

# Random numbers from a normal distribution
normal_dist = np.random.randn(3, 3)
print(normal_dist) # Output: [[-1.037105  1.013542  0.206664] [-0.249354  0.341964  1.056062] [-0.036647  0.220439 -0.029912]]
```

## Reshaping and Resizing

```python
arr = np.array([1, 2, 3, 4, 5, 6])

# Reshape to 2x3
reshaped = arr.reshape(2, 3)
print(reshaped) # Output: [[1 2 3] [4 5 6]]

# Flattening an array
flattened = reshaped.flatten()
print(flattened) # Output: [1 2 3 4 5 6]
```

## Aggregations

NumPy supports various aggregation functions:

```python
a = np.array([1, 2, 3, 4, 5])

# Sum
print(np.sum(a)) # Output: 15

# Mean
print(np.mean(a)) # Output: 3.0

# Maximum and Minimum
print(np.max(a)) # Output: 5
print(np.min(a)) # Output: 1

# Standard Deviation
print(np.std(a)) # Output: 1.4142135623730951
```

## Useful Tips

1. **Vectorization**: Avoid loops by using NumPy's vectorized operations, which are faster and more efficient.
2. **Copying Arrays**: Use `np.copy()` to avoid modifying the original array when making changes.
3. **Shape Attribute**: Use `arr.shape` to get the shape of an array, and `arr.reshape()` to change it.

## Conclusion

NumPy is a versatile and powerful library that simplifies numerical computations. By using its multidimensional arrays and efficient mathematical functions, you can speed up your data analysis and machine learning workflows. For further details, refer to the [official documentation](https://numpy.org/doc/).
