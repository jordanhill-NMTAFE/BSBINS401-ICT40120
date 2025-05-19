# Week 9: Getting Started with NumPy – Fundamentals for Data Manipulation

In this demo, we will explore the basics of NumPy, a powerful Python library for numerical data manipulation.  
We will cover core functions and transformations step by step, highlighting each concept explicitly.  
There will be prompts for you to try for yourself after each new feature.

---

# 1. Import NumPy

Let's start by importing NumPy, the essential library for working with arrays in Python.

```python
import numpy as np
```

*Try it:*  
*In your own notebook, import numpy as np and run the cell.*

---

# 2. Creating Arrays

NumPy's core feature is the array.  
Let's learn different ways to create arrays.

### a) From a list

```python
# Create a 1D array from a Python list
array1 = np.array([1, 2, 3, 4, 5])
array1
```

### b) With zeros and ones

```python
# Create an array of zeros
zeros = np.zeros(5)
# Create an array of ones
ones = np.ones(5)

zeros, ones
```

### c) Using arange and linspace

```python
# Create a sequence of numbers with np.arange
arr_range = np.arange(0, 10, 2)  # from 0 to 10, step 2

# Create a range of numbers evenly spaced with np.linspace
arr_linspace = np.linspace(0, 1, 5)  # from 0 to 1, 5 points

arr_range, arr_linspace
```


*Try creating your own arrays using np.zeros, np.ones, np.arange, np.linspace!*  

---

# 3. Array Attributes

Learn how to understand your arrays using attributes:

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
(
    a.shape,  # dimensions
    a.ndim,   # number of dimensions
    a.size,   # total number of elements
    a.dtype,  # data type of elements
)
```

*Try it:*  
*Create your own array and check its shape, ndim, size, and dtype.*

---

# 4. Array Indexing and Slicing

Access specific elements or parts of an array:

```python
# 1D array slicing
array1 = np.array([10, 20, 30, 40, 50])
(
    array1[2],    # element at index 2
    array1[1:4],  # elements from index 1 to 3
    array1[:3],   # first three elements
    array1[-1],   # last element
)
```

```python
# 2D array slicing
matrix = np.array([[1, 2], [3, 4], [5, 6]])
(
    matrix[0, 1],  # element at row 0, column 1
    matrix[:, 0],  # all rows, first column
    matrix[1:, :], # from row 1 onwards, all columns
)
```

*Try slicing your own arrays to access or modify specific parts.*

---

# 5. Array Manipulation: reshape, transpose, flatten

### a) Reshape

```python
# Reshape a flat array into 2x3
arr = np.arange(6)
arr_reshaped = arr.reshape(2, 3)
arr_reshaped
```

### b) Transpose

```python
# Transpose a 2D array
arr_T = arr_reshaped.T
arr_T
```

### c) Flatten

```python
# Flatten a multi-dimensional array back to 1D
flat_arr = arr_reshaped.flatten()
flat_arr
```

*Try:*  
*Create your own arrays and experiment with reshape, transpose, and flatten.*

---

# 6. Array Arithmetic and Broadcasting

### a) Element-wise operations

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
{
    "Addition":
    a + b,

    "Multiplication":
    a * 2,
    "Division":
    b / 2,
}
```

### b) Broadcasting example

```python
# Add a scalar to an array
r = np.array([1, 2, 3]) + 10
print("scalar+array: ", r)

# Add a 1D array to a 2D array (broadcast)
matrix = np.array([[1, 2], [3, 4]])
vector = np.array([10, 20])
matrix + vector
```

*Prompt:*  
*Try performing arithmetic operations with your own arrays and scalars.*

---

# 7. Aggregation Functions

Find the min, max, mean, sum, etc.:

```python
arr = np.array([10, 20, 30, 40])

(
    arr.min(),
    arr.max(),
    arr.mean(),
    arr.sum(),
)
```

*Try:*  
*Use your own arrays and compute aggregate functions.*

---

# 8. Conditional Selection (Boolean Indexing)

Create masks and filter data:

```python
arr = np.array([1, 2, 3, 4, 5, 6])
# Elements greater than 3
mask = arr > 3
print(mask)
print(arr[mask])

# Or directly
arr[arr > 3]
```

*Try:*  
*Create an array and select elements based on conditions.*

---

# 9. Random Number Generation

Generate random data with specific distributions:

```python
# Uniform distribution between 0 and 1
rand_uniform = np.random.rand(5)

# Random integers between low and high
rand_int = np.random.randint(0, 10, size=5)

# Normal distribution
rand_normal = np.random.randn(5)


(rand_uniform,rand_int,rand_normal)
```

*Prompt:*  
*Try generating your own random arrays using np.random.*

---

# 10. Summary & Practice

We've covered:
- Creating arrays
- Array properties
- Indexing and slicing
- Reshaping and transposing
- Arithmetic and broadcasting
- Aggregation functions
- Conditional selection
- Random data generation

**Now it's your turn!**  
- Create your own arrays and try applying these functions.  
- Practice reshaping, arithmetic, and indexing.

---

# Final note

NumPy is a very powerful fundamental tool in data science. Mastering these basics will help you manipulate data efficiently.

Happy experimenting!
