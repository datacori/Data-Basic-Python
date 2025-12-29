# Python Fundamentals Study (2025-12-25)
---

## Learning Goals 

- Generate data using NumPy `arange` and `linspace`
- Understand NumPy array output formats
- Perform element-wise operations
- Practice basic mathematical calculations
- Apply functions and operators in NumPy

---

## NumPy `arange`

- `np.arange()` generates evenly spaced numeric values within a given range
- Similar to Python’s `range()`, but supports floating-point steps
- The end value is **excluded**

### Example

```python
import numpy as np

print(np.arange(10, 30, 5))
# Output: [10 15 20 25]

print(np.arange(0, 2, 0.3))
# Output: [0.  0.3 0.6 0.9 1.2 1.5 1.8]
```
---

## NumPy linspace

- np.linspace() generates a specified number of evenly spaced values
- Both the start and end values are included
- Useful when the exact number of data points is required

### Example
```python
import numpy as np

x = np.linspace(0, 99, 100)
print(x)
```
```python
print(np.linspace(0, 1, 5))
```
```text
[0.   0.25 0.5  0.75 1.  ]
```
---

## NumPy Array Output

### 1D Array Output

- A one-dimensional NumPy array represents a simple sequence of values
- Commonly used for basic numerical operations and indexing

```python
import numpy as np

a = np.arange(6)
print(a)
```
```text
[0 1 2 3 4 5]
```

### 2D Array Output

## NumPy Array Output

### 1D Array Output

- A two-dimensional array represents data in rows and columns
- Often used to model tables or matrices
- Created by reshaping a 1D array

```python
b = np.arange(12).reshape(4, 3)
print(b)
```
```text
[[ 0  1  2]
 [ 3  4  5]
 [ 6  7  8]
 [ 9 10 11]]
```

### 3D Array Output

- A three-dimensional array is composed of multiple 2D arrays
- Commonly used in image processing, deep learning, and multidimensional data analysis

```python
c = np.arange(24).reshape(2, 3, 4)
print(c)
```
```text
[[[ 0  1  2  3]
  [ 4  5  6  7]
  [ 8  9 10 11]]

 [[12 13 14 15]
  [16 17 18 19]
  [20 21 22 23]]]
```
---

## 1. Element-wise Operations

NumPy performs operations **element by element** when applying arithmetic or comparison operators to arrays of the same shape.

### Example: 1D Array Operations

```python
import numpy as np

a = np.array([20, 30, 40, 50])
b = np.arange(4)

print(a)
print(b)
```
```text
[20 30 40 50]
[0 1 2 3]
```

### Arithmetic Operation
```python
print(b ** 2)
```
```text
[0 1 4 9]
```
Each element in b is squared independently

### Comparison Operation
```python
print(a < 35)
```
```text
[ True  True False False]
```
This produces a boolean array by comparing each element in a with the value 35.

---
## 2. Element-wise Multiplication vs Matrix Multiplication

NumPy distinguishes between element-wise multiplication and matrix multiplication, which is an important concept when working with multi-dimensional arrays.

### Example: 2D Arrays
```python
A = np.array([[1, 1],
              [0, 1]])

B = np.array([[2, 0],
              [3, 4]])

print(A)
print(B)
```

### Element-wise Multiplication (*)
```python
print(A*B)
```
```text
[[2 0]
 [0 4]]
```
Each element in a A is multiplied by the corresponding element in B.

### Matrix Multiplication (@)
```python
print(A @ B)
```
```text
[[5 4]
 [3 4]]
```
This performs true matrix multiplication follwing linear algebra rules.

---

## Key Takeaways

NumPy arithmetic and comparison operators work element-wise by default

* → element-wise multiplication

@ → matrix multiplication

Understanding this distinction is essential for data analysis, machine learning, and numerical computing

---

## NumPy Automatic Type Conversion (Type Casting)

This document explains how NumPy automatically converts data types during numerical operations, also known as **type casting** or **upcasting**.

Understanding NumPy’s type conversion rules is important to avoid unexpected results when working with mixed data types.

---

## 1. Automatic Type Conversion in NumPy

When performing numerical operations, NumPy automatically converts arrays to a **compatible data type** that can safely represent the result.

### Type Hierarchy (Simplified)


- Operations between different types are promoted to the **higher-precision type**
- This process is called **upcasting**

---

## 2. Example: Array Creation and Data Types

```python
import numpy as np

a = np.ones(3, dtype=np.int32)
b = np.linspace(0, np.pi, 3)

print(a)
print(b)
print(a.dtype)
print(b.dtype)
```
```text
[1 1 1]
[0.         1.57079633 3.14159265]
int32
float64
```
- a is an integer array (int32)
- b is a floating-point array (float64)

## Upcasting During Arthmetic Operations
```python
c = a + b
print(c)
print(c.dtype)
```
```text
[1.         2.57079633 4.14159265]
float64
```
- Adding an int32 array and a float64 array results in a float 64 array
- Numpy upcasts integers to floats to preserve numerical precision

## Complex Numbers from Mathematical Operations

Some mathematical functions return complex numbers even when the input is real.

### Example : Exponential Function
```python
d = np.exp(c * 1j)
print(d)
print(d.dtype)
```
```text
[ 0.54030231+0.84147098j -0.84147098+0.54030231j
 -0.54030231-0.84147098j]
complex128
```
- Multiplying by 1j introduces an imaginary component
- The result is automatically converted to complex129

---

## Key takeaways

NumPy automatically converts data types during operations

Mixed-type operations follow a safe upcasting rule

int + float → float

Operations involving imaginary numbers produce complex arrays

Understanding type conversion helps prevent bugs and precision loss

---

## NumPy Aggregation Functions

## 1. Common Aggregation Functions

- `sum()` → sum of all elements  
- `min()` → minimum value  
- `max()` → maximum value  
- `argmax()` → index of the maximum value  
- `cumsum()` → cumulative sum of elements  

---

## 2. Example: Aggregation on a 2D Array

```python
import numpy as np

a = np.arange(8).reshape(2, 4) ** 2
print(a)
```
```text
[[ 0  1  4  9]
 [16 25 36 49]]
```

### Finding the Index of the Maximum Value
```python
print(a.argmax())
```
```text
7
```
- argmax() returns the index of the maximum value in the flattened array
- NumPy flattens the array row-wise by default

## 3. Aggregation with the axis Parameter

The axis parameter specifies the direction along which aggregation is performed

Axis Reference
- axis = 0 → column-wise aggregation
- axis = 1 → row-wise aggregation

### Example : Sum Along Different Axes
```python
b = np.arange(12).reshape(3, 4)
print(b)
```
```text
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
```

Column-wise Sum (axis = 0)
```python
print(b.sum(axis=0))
```
```text
[12 15 18 21]
```

Row-wise Sum (axis = 1)
```python
print(b.sum(axis=1))
```
```text
[ 6 22 38]
```
---

## Key Takeaways

NumPy aggregation functions summarize data efficiently

argmax() returns the index in the flattened array unless an axis is specified

The axis parameter controls the direction of aggregation

Correct use of axis is critical for data analysis and machine learning workflows

---

## NumPy Array Basics

This document summarizes basic NumPy array operations I learned while studying Python.

## NumPy Array Functions

NumPy provides various functions that operate element-wise on arrays:

- Addition / Subtraction
- Multiplication / Division
- Logarithmic and Trigonometric functions  
  (`log`, `sin`, `cos`, `tan`)

### Example: Creating and Printing a NumPy Array

```python
import numpy as np

B = np.array([1, 4, 9])
print(B)
```
```text
[1 4 9]
```

### Example : Squre Root Calculation
NumPy allows mathematical operations to be applied to all elements of an array at once
```python
print(np.sqrt(B))
```
```
[1. 2. 3.]
```

## Key Takeaways

NumPy arrays support vectorized operations without using loops.

Mathematical functions like sqrt() are applied element-wise.

Using NumPy makes numerical computations simpler and more efficient.

---

## Key Learnings

### NumPy Data Creation
- `arange()` for creating arrays with a fixed step size
- `linspace()` for generating evenly spaced values within a given range

### NumPy Operations
- Element-wise operations on arrays
- Aggregate functions using the `axis` parameter

### NumPy Array Functions

---

## Reflections

- Initially, I encountered errors when using arange() and linspace().
- After investigating, I realized the issue was caused by NumPy not being imported in Google Colab.
- Once I added import numpy as np, the code worked as expected.
- Merry Christmas 🎄
Keep going!

---

## Resources
- Handbook_Python_Final.pdf
- Fast Campus – Python Data Analysis Fundamentals

## Author

**RYU YEJIN**

Python & Data Analysis Learner

Documenting my journey from Python basics to practical projects

📧 Email: datacori00@gmail.com

Blog : https://blog.naver.com/datacori/224116551211
