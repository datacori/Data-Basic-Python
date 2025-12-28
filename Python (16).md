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
`
