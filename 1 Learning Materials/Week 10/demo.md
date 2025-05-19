# Week 10: Introduction to Pandas – Data Manipulation and Analysis

In this demo, we will explore the basics of pandas, a powerful Python library designed for data manipulation and analysis.  
We’ll see how pandas handles labeled data, compare it to NumPy, and learn how to convert data back and forth between the two formats.  
You will also get lots of hands-on prompts to practice and deepen your understanding.

---

# 1. Import pandas

Let's begin by importing pandas.

```python
import pandas as pd
```

*Try it:*  
*In your notebook, run this cell to load pandas.*

---

# 2. Creating DataFrames from Data

Unlike NumPy arrays, pandas DataFrames are tabular data with labeled columns and rows.

## a) Create DataFrame from a dictionary

```python
# Create a simple DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 30, 35, 40],
    'Salary': [50000, 60000, 55000, 65000]
}
df = pd.DataFrame(data)
df
```

*Prompt:*  
*Try changing the data: add a new person with different details and re-run the cell.*

---

## b) Load from CSV file (if you have data)

```python
# Uncomment and run if you have a CSV file:
# df = pd.read_csv('your_data.csv')
```

*Prompt:*  
*Explore your own CSV files and see what data you can load into pandas.*

---

# 3. Viewing Data and Basic Info

```python
# View first 5 rows
df.head()
```

```python
# Get data info (columns, datatypes, non-null counts)
df.info()
```

```python
# Summary statistics for numeric columns
df.describe()
```

*Prompt:*  
*Try adding some missing values to the DataFrame and see how `df.info()` updates.*

---

# 4. Selecting and Filtering Data

## a) Select a column

```python
# Select 'Age'
ages = df['Age']
ages
```

*Prompt:*  
*Try selecting other columns, or filter for ages over 30:*

```python
ages_over_30 = df[df['Age'] > 30]
ages_over_30
```

## b) Select multiple columns

```python
df[['Name', 'Salary']]
```

*Prompt:*  
*Create your own list of columns to select—try selecting 'Name' and 'Age'.*

---

# 5. Filtering Rows based on Conditions

```python
# Ages over 30
df[df['Age'] > 30]
```

```python
# Salaries below 60000
df[df['Salary'] < 60000]
```

*Prompt:*  
*Try combining conditions: Age > 25 and Salary > 51000.*

```python
filtered = df[(df['Age'] > 25) & (df['Salary'] > 51000)]
filtered
```

---

# 6. Sorting Data

```python
# Sort by Salary descending
df.sort_values('Salary', ascending=False)
```

*Prompt:*  
*Sort by Age ascending and check the order.*

```python
df_sorted_age = df.sort_values('Age')
df_sorted_age
```

---

# 7. Adding and Modifying Data

## a) Add a new column

```python
# Example: add 'Tax' at 20%
df['Tax'] = df['Salary'] * 0.2
df
```

*Prompt:*  
*Try creating a new column: 'NetSalary' = 'Salary' - 'Tax'.*

```python
df['NetSalary'] = df['Salary'] - df['Tax']
df
```

## b) Change existing values

```python
# Increase everyone’s Salary by 10%
df['Salary'] = df['Salary'] * 1.1
df
```

*Prompt:*  
*Try increasing only those with Salary below 55,000.*

```python
df.loc[df['Salary'] < 55000, 'Salary'] = df['Salary'] * 1.2
```

---

# 8. Grouping and Aggregations

Suppose multiple departments or groups.

```python
# Example data
group_data = {
    'Department': ['HR', 'Sales', 'HR', 'Sales', 'IT', 'IT'],
    'Salary': [50000, 60000, 52000, 61000, 55000, 58000]
}
group_df = pd.DataFrame(group_data)

# Group by Department and get average Salary
grouped = group_df.groupby('Department')['Salary'].mean()
grouped
```

*Prompt:*  
*Use your data: group by 'Type' or other column and calculate mean, max, or count.*

---

# 9. Pivot Tables: Re-arranging Your Data

```python
# Define sample data
pivot_data = {
    'Region': ['North', 'South', 'North', 'South'],
    'Gender': ['Male', 'Female', 'Female', 'Male'],
    'Sales': [100, 150, 200, 250]
}
pivot_df = pd.DataFrame(pivot_data)

# Create a pivot table averaging Sales by Region and Gender
pivot_table = pd.pivot_table(pivot_df, values='Sales', index='Region', columns='Gender', aggfunc='mean')
pivot_table
```

*Prompt:*  
*Try creating your own pivot table: group data by different columns.*

---

# 10. Save Your Data

```python
# Save DataFrame as CSV
df.to_csv('my_data.csv', index=False)
```

*Prompt:*  
*Try saving your DataFrame, then re-loading it with pd.read_csv() and compare.*

---

# 11. Converting Between numpy arrays and pandas DataFrames

### **From NumPy to pandas**

```python
import numpy as np
# Create a NumPy array
np_array = np.array([10, 20, 30, 40])
# Convert to pandas DataFrame
df_from_np = pd.DataFrame(np_array, columns=['Values'])
df_from_np
```

### **From pandas to NumPy**

```python
# Take a column from our DataFrame
np_array2 = df['Age'].values
np_array2  # numpy array of ages
```

**Prompt:**  
*Try converting a numpy array to a pandas DataFrame AND a DataFrame to a numpy array for your data.*

---

# 12. Final Tips and Practice

- Use `head()`, `info()`, and `describe()` often to understand your data.
- Use groupby and pivot tables to summarize large tables.
- Use `.values` and `pd.DataFrame()` to switch between pandas and NumPy.
- Do hands-on practice: try similar operations on your own datasets.

---

# Conclusion

- pandas makes working with structured data (tables) easy and powerful.  
- NumPy is great for fast numeric calculations.  
- Combining pandas and NumPy allows flexible data workflows.

---

# **Your Turn**:  
- Pick your dataset. Practice creating DataFrames, selecting, filtering, grouping, and converting data.  
- Explore the combining of NumPy and pandas yourself!  

Good luck!
