# Python Fundamentals Study (2025-12-24)

---

## Learning Goals 

- Understand core **NumPy concepts**
- Learn how NumPy **arrays** work
- Practice **array creation**
- Practice **function writing and modularization**

---

## What is NumPy?

**NumPy (Numerical Python)** is a fundamental Python library used for numerical and scientific computing.

- A Python-based **numerical computation library**
- Widely used for data analysis, machine learning, and scientific calculations

### Installation
```bash
pip install numpy
```

---

## NumPy Arrays

- A NumPy array is called an ndarray (N-dimensional array)
- Supports efficient array-to-array operations
- All elements in a NumPy array have the same data type by default
- Dimensions are represented using axes

---

## Array Dimensions

### 1D array
```python
import numpy as np

arr_1d = np.array([1, 2, 3, 4, 5])
```

Represents a simple one-dimensional structure similar to a list

### 2D array
```python
arr_2d = np.array([[1, 2, 3],
                   [4, 5, 6]])
```

Represents a matrix-like structure with rows and columns

### 3D array
```python
arr_3d = np.array([
    [[1, 2], [3, 4]],
    [[5, 6], [7, 8]]
])
```

Represents a multi-layered array structure, commonly used in advanced data processing
---

## Key Learnings

NumPy arrays enable fast numerical computation

All elements in an ndarray share the same data type

Understanding array dimensions is essential for data manipulation

Axes define how operations are applied across dimensions

---

## Common NumPy Array Attributes

NumPy arrays (`ndarray`) provide several built-in attributes that describe their structure and data properties.

---

### Key Attributes

- **`ndarray.shape`**  
  Returns the size of each axis (dimension) of the array

- **`ndarray.ndim`**  
  Returns the number of dimensions (axes)

- **`ndarray.dtype`**  
  Returns the data type of each element

- **`ndarray.itemsize`**  
  Returns the size (in bytes) of each element

- **`ndarray.size`**  
  Returns the total number of elements in the array

---

## Example

Create a 2D array with shape `(3, 4)`:

```python
import numpy as np

a = np.arange(12).reshape(3, 4)
print(a)
```
```text
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
```

### Array Shape
```python
print(a.shape)
```
```text
(3, 4)
```

### Element Data Type
```python
print(a.dtype)
```
```text
int64
```

### Size of Each Element (Bytes)
```python
print(a.itemsize)
```
```text
8
```

### Total Number of Elements
```python
print(a.size)
```
```text
12
```

## Key Learning

NumPy array attributes provide metadata about array structure and memory usage

Understanding shape and ndim is essential for reshaping and broadcasting

dtype and itemsize help manage memory efficiency

size is useful for validating data dimensions

---

### Creating NumPy Arrays

- NumPy arrays can be created using the `np.array()` function  
- Python built-in data types such as **lists** or **tuples** are converted into `numpy.ndarray` objects  
- NumPy automatically determines the appropriate data type (`dtype`) based on the input values  

**Example: Integer Array**
```python
import numpy as np

a = np.array([2, 3, 4])
print(a)
print(a.dtype)
```
```text
[2 3 4]
int64
```

### Example : Floating-point Array
```python
b = np.array([1.2, 3.5, 5.1])
print(b)
print(b.dtype)
```
```text
[1.2 3.5 5.1]
float64
```
---

## Initializing NumPy Arrays

NumPy provides several functions to create arrays with predefined values or without initialization.

---

### `np.zeros(shape)`

- Creates an N-dimensional array filled with zeros  
- Commonly used for initializing matrices or tensors  

```python
import numpy as np

print(np.zeros((3, 4)))
```
```text
[[0. 0. 0. 0.]
 [0. 0. 0. 0.]
 [0. 0. 0. 0.]]
```

### np.ones(shape, dtype)

- Creates an N-dimensional array filled with ones
- The data type can be explicitly specified using the dtype parameter

```python
print(np.ones((2, 3, 4), dtype=np.int64))
```
```text
[[[1 1 1]
  [1 1 1]
  [1 1 1]]

 [[1 1 1]
  [1 1 1]
  [1 1 1]]]
```

### np.empty(shape)

- Creates an N-dimensional array without initializing its values
- The array contains arbitrary values already present in memory
- Faster than zeeros() or ones() but should be used with caution

```python
np.empty(shape)
```
```text
[[5.03205381e-315 0.00000000e+000 1.94531707e+227]
 [1.63041663e-322 6.81001398e-310 6.81001398e-310]]
```
zeros() and ones() guarantee initialized values

empty() is useful when performance is critical and values will be overwritten immediately

---

## Key Learnings

- Practiced fundamental NumPy concepts through hands-on examples
- Gained familiarity with NumPy array creation and basic operations

---

## Reflections

- Learned NumPy based on previously studied Python fundamentals
- Became comfortable using the common NumPy alias `np`
- Improved familiarity with inspecting outputs using the `print()` function
- Keep going!

---

## Resources

- *Handbook_Python_Final.pdf*
- *Fast Campus – Practical Python Data Analysis Without Failure*

---

## Author

**RYU YEJIN**  

Studying Data Analysis 

From Python Fundamentals to Practical Projects  

📧 Email: datacori00@gmail.com

Blog : https://blog.naver.com/datacori/224116551211
