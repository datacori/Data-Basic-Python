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

---

## Creating a Base Array

First, create a one-dimensional NumPy array.

```python
import numpy as np

a = np.arange(8) ** 2
print(a)
```
```text
[ 0  1  4  9 16 25 36 49]
```
This array contains the squares of numbers from 0 to 7

---

## Indexing with a 1D Index Array
You can use another array of indices to select specific elements.
```python
i = np.array([1, 1, 3, 5])
print(a[i])
```
```text
[ 1  1  9 25]
```
---

## Indexing with a 2D Index Array
Index arrays can also be multi-dimensional.
```python
j = np.array([[3, 4],
              [2, 5]])
print(a[j])
```
```text
[[ 9 16]
 [ 4 25]]
```
---

## Key Takeaways
- Index arrays allow flexible and powerful data selection
- The output shape is determined by the index array, not the original array
- Fancy indexing is useful for advanced data manipulation and anlysis

---

## NumPy Boolean Indexing

---

## Creating a 2D Array

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
This creates a 3x4 array with values from 0 to 11

---
## Creating a Boolean Mask
Apply a condition to generate a Boolean array
```python
b = a >4
print(b)
```
```text
[[False False False False]
 [False  True  True  True]
 [ True  True  True  True]]
```
Each element is evaluated against the condition a >4

True indicates elements that satisfy the condition

---
## Selecting Elements Using Boolean Indexing
```python
print(a[b])
print(a[b].shape)
```
```text
[ 5  6  7  8  9 10 11]
(7,)
```
---

## Modifying Values with Boolean Indexing
Boolean indexing can also be used to update array values
```python
a[b] = 0
print(a)
```
```text
[[0 1 2 3]
 [4 0 0 0]
 [0 0 0 0]]
```
All elements that satisfy the condition are replaced with 0

This operation modifies the original array in-place

---
## Key Takeaways
- Boolean indexing enables conditional filtering of NumPy arrays
- It works similarly to WHERE clauses in SQL
- Boolean masks can be reused for selection and assignment
- Useful for data cleaning and preprocessing

---

## NumPy Array Shape Manipulation

---

## Checking Array Shape

NumPy arrays allow flexible shape manipulation.

```python
import numpy as np

a = np.arange(12).reshape(3, 4)
print(a)
print(a.shape)
```
```text
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
(3, 4)
```
---
## Flattening an Array

### Using ravel()
```python
print(a.ravel())
```

### Using reshape(-1)
```python
print(a.reshape(-1)
```
```text
[ 0  1  2  3  4  5  6  7  8  9 10 11]
```
Both methods convert the array into a 1D array

---
## Reshaping to a Specific Dimension
```python
print(a.reshape(2, 6)
```
```text
[[ 0  1  2  3  4  5]
 [ 6  7  8  9 10 11]]
```
The total number of elements must remain the same
Reshaping is useful when preparing data for modeling or analysis

---
## Trasposing an Array

### Using .T
```python
print(a.T)
print(a.T.shape)
```
```text
[[ 0  4  8]
 [ 1  5  9]
 [ 2  6 10]
 [ 3  7 11]]
(4, 3)
```
Transpose swaps rows and colunms
Commonly used in linear algebra and data transformations

---

## Key Takeaways
- NumPy arrays can be reshaped without changing the data
- ravel() and reshape(-1) flatten arrays into 1D
- reshape() is essential for controlling data dimensions
- Transpose is useful for matrix operations and feature engineering

---

## NumPy Array Stacking (vstack & hstack)

This section covers how to combine NumPy arrays using vertical and horizontal stacking methods.  
I practiced using `np.vstack()` and `np.hstack()` to understand how the `axis` parameter affects array shapes and data alignment.

---

## Creating Sample Arrays

Two 2D arrays were created using `reshape()` to clearly observe the stacking results.

```python
import numpy as np

a = np.array([1, 2, 3, 4]).reshape(2, 2)
print(a)
```
```text
[[1 2]
 [3 4]]
```

```python
b = np.array([5, 6, 7, 8]).reshape(2, 2)
print(b)
```
```text
[[5 6]
 [7 8]]
```

## Vertical Stacking : np.vstack()
- Stacks arrays row-wise
- Equivalent to stacking along axi = 0
- The number of columns must be the same

```python
print(np.vstack((a, b)))
```
```text
[[1 2]
 [3 4]
 [5 6]
 [7 8]]
```
The two arrays are stacked vertically, increasing the number of rows.

---
## Horizontal Stacking : np.hstack()
- Stacks arrays column-wise
- Equivalent to stacking along axis = 1
- The number of rows must be the same

```python
print(np.hstack((a, b)))
```
```text
[[1 2 5 6]
 [3 4 7 8]]
```
The two arrays are stacked horizontally, increasing the number of columns

---
## Key Takeaways
- np.vstack() → vertical stacking (axis = 0)
- np.hstack() → horizontal stacking (axis = 1)
- Array dimensions must be compatible before stacking
- Understanding array shapes is essential for data preprocessing and feature engineering

---

# NumPy Array Splitting (hsplit)

This section focuses on splitting NumPy arrays horizontally using `np.hsplit()`.  
I explored different ways to divide arrays by specifying either the number of equal splits or explicit column indices.

---

## Creating a Sample Array

A 2D array was created using `np.arange()` and `reshape()` to clearly demonstrate how horizontal splitting works.

```python
import numpy as np

a = np.arange(12).reshape(2, 6)
print(a)
```
```text
[[ 0  1  2  3  4  5]
 [ 6  7  8  9 10 11]]
```
---

## Splitting into Equal Sections

When an integer is passed to np.hsplit(), the array is divided into that many equal-sized sub-arrays along axis = 1

```python
print(np.hsplit(a,3)
```
```text
[array([[0, 1],
        [6, 7]]),
 array([[2, 3],
        [8, 9]]),
 array([[ 4,  5],
        [10, 11]])]
```
---

## Splitting by Specific Column Indices

np.hsplit() can also split arrays using a list of column indices.
```python
print(np.hsplit(a, (3, 4)))
```
```text
[array([[0, 1, 2],
        [6, 7, 8]]),
 array([[3],
        [9]]),
 array([[ 4,  5],
        [10, 11]])]
```
---

## Key Takeaways
- np.hsplit() splits arrays horizontally (axis = 1)
- Passing an integer → equal-sized splits
- Passing a list/tuple → custom column-based splits
- Useful for feature separation and preprocessing in data analysis

---
## Key Learnings

- Gained a solid understanding of NumPy indexing and slicing
- Practiced splitting and stacking NumPy arrays for data manipulation
- Improved familiarity with array shapes and axis-based operations

---

## Reflections

- NumPy array operations initially felt challenging, but became clearer through hands-on practice
- Python indexing and slicing concepts directly transfer to NumPy arrays
- Using `reshape()` makes it much easier to visually understand and manipulate multi-dimensional data
- Continuous practice is key to mastering numerical computing with NumPy
- Keep going!

---

## Resources

- *Handbook_Python_Final.pdf*
- Fast Campus – **Practical Python Data Analysis Without Trial and Error**

---

## Author

**RYU YEJIN**  

Aspiring Data Analyst  

Documenting the journey from Python fundamentals to practical data analysis projects  

📧 Email: datacorio00@gmail.com

Blog : https://blog.naver.com/datacori/224117579062
