# Python Fundamentals Study (2025-12-26)

---

## Learning Goals 

- NumPy Indexing and Slicing
- Reshaping NumPy Arrays
- NumPy Data Concatenation and Splitting
- Practice Writing Functions and Solving Problems

## NumPy Indexing and Slicing

Indexing and slicing are used to access specific elements or ranges within an array.

- **Indexing**: Accessing a single element
- **Slicing**: Accessing a range of elements

### Example : Creating an Array

```python
import numpy as np
a = np.arange(10) ** 2
print(a)
```
```text
[ 0  1  4  9 16 25 36 49 64 81]
```

### Example : Indexing
Accessing the element at index 2
```python
print(a[2])
```
```text
4
```

### Example : Slicing
Accessing elements from index 2 to 4
```python
print(a[2:5])
```
```text
[ 4  9 16]
```

### Example : Reverse Order
Using slicing to reverse the array
```python
print(a[::-1])
```
```text
[81 64 49 36 25 16  9  4  1  0]
```
--- 

## Key Takeaways
- Indexing retrieves a single value from an array.
- Slicing retrieves multiple values using a range.
- NumPy slicing allows step control, including reversing arrays.
- These features make data manipulation concise and efficient.
