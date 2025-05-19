# Week 11: Deep Dive into pandas — Advanced Data Transformations & Explorations

Welcome!  
In this notebook, we’ll explore powerful pandas features—especially focusing on:
- Using lambda functions to perform custom transformations
- Visualizing complex mathematical functions with pandas and numpy
- Merging and concatenating datasets for flexible data combination
- Converting pandas DataFrames and numpy arrays back and forth—understanding how they relate
- Building examples from simple to advanced scenarios, with plenty of prompts to learn by doing

Let’s unlock some fun with data and math!

---

# 1. Setup: Import core libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

*Try:*  
Run this cell. You are now ready to experiment with pandas and numpy!

---

# 2. Create Data for Mathematical Fun

Let's create a set of data points from a smooth mathematical function that allows us to visualize and transform easily:

```python
# Generate 200 points evenly spread between -pi and pi
x = np.linspace(-np.pi, np.pi, 200)

# Build a DataFrame with multiple functions of x for exploration
df = pd.DataFrame({
    'x': x,                                    # the x values
    'sin_x': np.sin(x),                         # sine of x
    'cos_x': np.cos(x),                         # cosine of x
    'tan_x': np.tan(x),                         # tangent of x (be careful near asymptotes!)
    'x_squared': x**2,                          # x squared
    'abs_x': np.abs(x),                         # absolute value of x
    'exp_x': np.exp(x / 4),                     # scaled exponential
    'sin_x_squared': np.sin(x)**2               # sine squared
})
df.head()
```

**Prompt:**  
- Try creating your own functions, e.g., `np.log1p(np.abs(x))` for a logarithmic curve.  
- Think: how might these functions evolve if you change parameters?  
- Plot them individually to see their shape.

---

# 3. Applying lambda functions to customize data transformations

Lambda functions in pandas are super-powerful for custom calculations.

### a) Create a new column that combines existing ones with a lambda

```python
# Sum of sine and cosine (use apply with lambda)
df['sin_plus_cos'] = df.apply(lambda row: row['sin_x'] + row['cos_x'], axis=1)
```

*Prompt:*  
- Try creating a new column with `np.abs(np.sin(x) * np.cos(x))`.  
- Or experiment with other operations: e.g., `row['sin_x']**3` or `np.exp(row['x'])`.  
- Calculate a formula involving multiple columns.

---

### b) Visualize the result

```python
plt.plot(df['x'], df['sin_plus_cos'])
plt.title('Sum of sin(x) + cos(x)')
plt.xlabel('x')
plt.ylabel('sum')
plt.show()
```

*Prompt:*  
- Plot other combined functions to see complex waves: e.g., `np.sin(2*x) + 0.5*np.cos(4*x)`.

---

# 4. Create and plot complex mathematical functions with lambda

Let’s generate visually interesting functions using lambda for custom formulas:

```python
# Multiply sine by a scaled cosine using apply + lambda
df['modulated_wave'] = df['x'].apply(lambda x: np.sin(x) + 0.5*np.cos(5*x))
```

```python
# Plot this complex wave
plt.plot(df['x'], df['modulated_wave'])
plt.title('Wave: sin(x) + 0.5*cos(5x)')
plt.xlabel('x')
plt.ylabel('amplitude')
plt.show()
```

*Prompt:*  
- Play with different functions: e.g., `np.exp(-x**2) * np.cos(3*x)` for a Gaussian-modulated wave.  
- Can you create a waveform that appears like a "damped oscillation"?

---

# 5. Plotting and visualizing transformations of functions

### a) Visualize `x * sin(x)`, a classic example

```python
# Apply lambda to generate x*sin(x)
df['x_sin_x'] = df['x'].apply(lambda x: x * np.sin(x))
plt.plot(df['x'], df['x_sin_x'])
plt.title('Plot of x * sin(x)')
plt.xlabel('x')
plt.ylabel('x * sin(x)')
plt.show()
```

###b) Visualize `np.exp(-x**2)` and its negative

```python
# Create a Gaussian-like curve
df['gaussian'] = np.exp(-df['x']**2)

plt.plot(df['x'], df['gaussian'])
plt.title('Gaussian Function: exp(-x^2)')
plt.xlabel('x')
plt.ylabel('f(x)')
plt.show()
```

*Prompt:*  
- Create your own weighted functions: e.g., `(np.sin(3*x)+np.cos(2*x))/2`.  
- Plot how changing parameters affects shape.

---

# 6. Merging and concatenating datasets

Suppose we generate additional data sources, then combine them:

```python
# New dataset with different functions
df2 = pd.DataFrame({
    'x': x,
    'sin_x': np.sin(x),
    'cos_x_squared': np.cos(x)**2,
    'tan_x': np.tan(x/2)
})
```

### a) Merging on common column `'x'`

```python
merged_df = pd.merge(df, df2, on='x', suffixes=('_orig', '_new'))
merged_df.head()
```

### b) Concatenate datasets vertically or horizontally

```python
# Vertical concatenation (stack rows)
concat_rows = pd.concat([df, df2], axis=0)
print('Vertical concatenation shape:', concat_rows.shape)

# Horizontal concatenation (combine columns)
concat_cols = pd.concat([df, df2], axis=1)
print('Horizontal concatenation shape:', concat_cols.shape)
```

*Prompt:*  
- Create your own small datasets, then merge or concatenate in different ways.  
- Explore what happens if datasets have different columns.

---

# 7. Converting pandas DataFrame back and forth to NumPy arrays

**Q:** Why bother with different formats? When do you convert from pandas to numpy, or vice versa?

### a) pandas DataFrame → numpy array

```python
# Take a column from pandas as numpy array
np_array = df['sin_x'].values
print('Array shape:', np_array.shape)
```

*Tip:*  
- For multi-dimensional DataFrame, `.values` preserves the shape.
- To get only one row or column, ensure dimensions match; for example:

```python
# For a column (series), shape is (100,)
# For a DataFrame with multiple columns, shape is (rows, columns)
```

### b) numpy array → pandas DataFrame

```python
# Create a numpy array with multiple columns
np_data = np.linspace(-np.pi, np.pi, 200).reshape(100, 2)
# Convert to DataFrame with labels
df_from_np = pd.DataFrame(np_data, columns=['x', 'sin_ln'])
df_from_np.head()
```

*Prompt:*  
- Pick a column from your pandas DataFrame and convert back to numpy array.  
- Create a numpy array of your own functions, then convert to pandas.  
- Observe how shape and labels are maintained or lost.

---

# 8. Fun with complex functions and lambda

Visualize functions with multiple frequencies, phases, or parameters:

```python
# 3-frequency combined wave
df['multi_wave'] = df['x'].apply(lambda x: np.sin(x) + 0.5*np.sin(3*x) + 0.25*np.sin(5*x))
plt.plot(df['x'], df['multi_wave'])
plt.title('Multi-frequency Wave')
plt.xlabel('x')
plt.ylabel('amplitude')
plt.show()
```

**Prompt:**  
- Experiment by adding or subtracting components.   Create an oscillation that looks like a complex musical tone!  
- Think of a real-world signal or pattern: can you replicate it?

---

# 9. Summing up: Playing with math, pandas, and numpy

- Lambda functions help you craft custom transformations.
- pandas and numpy complement each other—conversions give flexible options.
- Visualize complex functions or signals easily.

---

# 10. How to convert back and forth between pandas and numpy

### pandas to numpy

```python
# Extract a column to numpy array
array_from_series = df['x'].values
print("Shape:", array_from_series.shape)
```

### numpy to pandas

```python
# Generate an array
x_array = np.linspace(0, 10, 100)
# Convert to DataFrame
df_x = pd.DataFrame({'x': x_array, 'sin_x': np.sin(x_array)})
df_x.head()
```

*Prompt:*  
- Pick your favorite pandas DataFrame and convert a column into numpy.  
- Generate numpy data based on mathematical functions, then turn it into a pandas DataFrame to analyze structure.

---

# 11. Final challenge: Your own mathematical functions + pandas

Create a new wave:

```python
x = np.linspace(-np.pi, np.pi, 300)
df = pd.DataFrame({'x': x})
# Use lambda to create a custom signal
df['custom_wave'] = df['x'].apply(lambda x: np.sin(2*x) + 0.5*np.cos(4*x) - 0.3*np.sin(6*x))
plt.plot(df['x'], df['custom_wave'])
plt.title('Custom Complex Wave')
plt.xlabel('x')
plt.ylabel('Amplitude')
plt.show()
```

**Prompt:**  
- What combination of functions creates interesting patterns?  
- Adjust coefficients or frequencies, and plot the effect.

---

# **Summary and reflection**

You have explored:
- Advanced lambda functions for mathematical transformations
- How to switch between pandas and numpy effectively
- Combining and merging different datasets
- Visualizing complex mathematical signals

Keep experimenting with these tools!

---

# End of demo