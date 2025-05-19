
# Week 13: Mastering Tidy Data – Practical Transformations for Real-World Datasets

---

## What is tidy data?

**Tidy data** is a way of organizing datasets to make analysis intuitive. Its core principles:

- **Each variable is a column.**  
  (e.g., age, sales, temperature)

- **Each observation is a row.**  
  (e.g., a person, a time point, a transaction)

- **Each observational unit is a table.**  
  (e.g., customer data, weekly sales, weather data)

**Why does this matter?**

- Makes filtering, summarizing, and visualization straightforward.
- Ensures datasets work smoothly with common analysis tools.
- Supports reproducibility and sharing.

---

# 1. Wide-to-Long Format: Yearly Data

### Starting with data (simulating sales over years):

```python
import pandas as pd

df1 = pd.DataFrame({
    'Product': ['Widget A', 'Widget B', 'Widget C', 'Widget D'],
    'Sales_2019': [500, 300, 450, 600],
    'Sales_2020': [550, 330, 460, 620],
    'Sales_2021': [600, 390, 480, 650]
})
```

### Goal:

Convert to tidy format — one row per product-year-sales.

```python
# Use melt to reshape
long_df1 = pd.melt(df1, id_vars=['Product'],
                   value_vars=['Sales_2019', 'Sales_2020', 'Sales_2021'],
                   var_name='Year', value_name='Sales')

# Clean 'Year' column
long_df1['Year'] = long_df1['Year'].str.replace('Sales_', '')

long_df1
```

**Student Activity:**  
*Now you try*—add another year (e.g., 2022) or product, and repeat the melt. Try changing the variable columns to include more metrics (like Units).

---

# 2. Variables in One Column: Separate into multiple

### Starting data (product details):

```python
df2 = pd.DataFrame({
    'Product': ['Widget A', 'Widget B', 'Widget C', 'Widget D'],
    'Details': ['Price: 20, Qty: 5', 'Price: 15, Qty: 7', 'Price: 25, Qty: 3', 'Price: 30, Qty: 6']
})
```

### Goal:

Split the 'Details' string into separate numeric `Price` and `Qty` columns.

```python
# Split Details
split_details = df2['Details'].str.split(', ', expand=True)

# Remove labels and convert
split_details['Price'] = split_details[0].str.replace('Price: ', '').astype(int)
split_details['Qty'] = split_details[1].str.replace('Qty: ', '').astype(int)

# Merge back
tidy_df2 = pd.concat([df2['Product'], split_details[['Price', 'Qty']]], axis=1)

tidy_df2
```

**Student Activity:**  
*Now you try* — add more variables into the 'Details' column, e.g., "Revenue: 100", and split again.

---

# 3. Wide Format: Animal measurements

### Starting dataset:

```python
df3 = pd.DataFrame({
    'Animal': ['Dog', 'Cat', 'Rabbit', 'Horse'],
    'Length': [60, 40, 30, 170],
    'Weight': [20, 10, 5, 500],
    'Height': [50, 30, 25, 160]
})
```

### Goal:

Transform into long format — one row per animal-measurement.

```python
long_measures = pd.melt(df3, id_vars=['Animal'], 
                        value_vars=['Length', 'Weight', 'Height'],
                        var_name='MeasureType', value_name='Value')

long_measures
```

**Student Activity:**  
*Now you try* — add a new measurement type, such as "Speed", and melt again. Then, plot different measures.

---

# 4. String Data with Units

### Starting data (measurements with units):

```python
df4 = pd.DataFrame({
    'Person': ['Alice', 'Bob', 'Charlie', 'Daisy'],
    'Data': ['170cm, 60kg', '180cm, 75kg', '165cm, 55kg', '160cm, 50kg']
})
```

### Goal:

Split into numeric height and weight, converting units to integers.

```python
split_df4 = df4['Data'].str.split(', ', expand=True)
split_df4.columns = ['Height', 'Weight']

# Remove units and convert to int
split_df4['Height'] = split_df4['Height'].str.replace('cm', '').astype(int)
split_df4['Weight'] = split_df4['Weight'].str.replace('kg', '').astype(int)

# Combine back
tidy_people = pd.concat([df4['Person'], split_df4], axis=1)
tidy_people
```

**Student Activity:**  
*Now you try* — convert height from cm to inches (`cm / 2.54`) and visualize the distribution.

---

# 5. Observations in Sections

### Starting dataset:

```python
df5 = pd.DataFrame({
    'StudentID': [101, 102, 103, 104],
    'Session1': [85, 78, 92, 70],
    'Session2': [88, 80, 94, 72],
    'Session3': [90, 82, 96, 75]
})
```

### Goal:

Convert to long format: one row per student per session.

```python
long_scores = pd.melt(df5, id_vars=['StudentID'], 
                      value_vars=['Session1', 'Session2', 'Session3'],
                      var_name='Session', value_name='Score')

long_scores['Session'] = long_scores['Session'].str.replace('Session', '')

long_scores
```

**Student Activity:**  
*Now you try* — add `Session4` and melt again. Calculate the average score per session.

---

# 6. How to convert pandas DataFrame column to numpy array and back

### a) From pandas to numpy

```python
x = range(10)
y = range(10)
df = pd.DataFrame({"x":[*x], "y":[*y]})


# Try picking a column and convert to numpy, how does that change the shape?
x = df.to_numpy()
print('Shape:', x.shape)
```

### b) From numpy to pandas

```python
import numpy as np
# Generate numpy data
np_x = np.linspace(0, 2*np.pi, 100)

# Convert to pandas DataFrame
df_x = pd.DataFrame({'x': np_x, 'cos_x': np.cos(np_x)})
df_x.head()
```

**Prompt:**  
*Now you try* — pick a column from your DataFrame, convert it to numpy using `.values` or `.to_numpy()`.  
Then, generate a numpy array with a wave function (e.g., `np.tan`) and convert it back into pandas.

---

# 7. Build your own wave (advanced)

Create a waveform with multiple sine waves:

```python
import matplotlib.pyplot as plt

x_vals = np.linspace(-np.pi, np.pi, 300)
df_wave = pd.DataFrame({'x': x_vals})

# Use lambda to formulate a complex wave
df_wave['wave'] = df_wave['x'].apply(
    lambda x: np.sin(2*x) + 0.5*np.sin(4*x) - 0.3*np.sin(6*x)
)

plt.plot(df_wave['x'], df_wave['wave'])
plt.title('Sum of multiple sine waves')
plt.xlabel('x')
plt.ylabel('Amplitude')
plt.show()
```

**Student Activity:**  
*Now you try* — change coefficients or add more sine terms to create your own wave pattern.

---

# Final thoughts: Putting it all together

- You can reshape, split, merge, and concatenate messy datasets into tidy formats.  
- Lambdas help you craft custom math features.  
- Converting between pandas and numpy provides flexibility but keep an eye on array shapes!  
- Visualizations can help you interpret complex, combined signals.

**Your challenge:**  
- Take any messy dataset and attempt all these transformations.  
- Practice creating tidy data for analysis.

---

# End of demo!

Master these steps to handle practical data challenges. Remember the core principles: each variable in a column, each observation in a row, and related variables kept in logical tables.
