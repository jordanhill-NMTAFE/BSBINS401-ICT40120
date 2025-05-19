# Week 12: Combining Data with pandas — concat, merge, and Joins

In this demo, we will learn:
- How to combine datasets vertically and horizontally using `pd.concat`
- How to join datasets on keys using `pd.merge`
- What the different types of joins mean: **inner, outer, left, right**
- Visualize joins with simple Venn diagrams or scatter plots

Let's make data friends!

---

# 1. Setup: Import pandas and matplotlib

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

*Try:*  
Run this cell. Get comfy—you’ll be making and combining data!

---

# 2. Create simple datasets to experiment with

Let's make two small datasets about Titanic passengers for simplicity.

```python
# Dataset 1: Passenger ID and Age
df1 = pd.DataFrame({
    'PassengerID': [1, 2, 3, 4],
    'Age': [22, 38, 26, 35]
})

# Dataset 2: Passenger ID and Ticket Class
df2 = pd.DataFrame({
    'PassengerID': [3, 4, 5, 6],
    'Class': ['First', 'Second', 'Third', 'First']
})

# Show them
df1, df2
```

**Prompt:**  
- Think: which passengers are shared? Which are unique?  
- What happens if you only want passengers in both datasets? (Join the data!)

---

# 3. Using `pd.concat` to stack data

### a) Concatenate vertically (row-wise)

```python
# Stack 'df1' and 'df2' on top of each other?
pd.concat([df1, df2], axis=0)
```

**Prompt:**  
- Add some missing values or extra rows and see what happens!  
- How does pandas align columns? What if columns don’t match?

---

### b) Concatenate horizontally (column-wise)

```python
# Side-by-side, aligning by index (default)
pd.concat([df1, df2], axis=1)
```

**Prompt:**  
- What if columns have the same name?  
- Try concatenating `df1` with another dataset on the same index to add more info.

---

# 4. Using `pd.merge` to join datasets on key columns

`pd.merge` allows us to join based on one or more key columns (like `PassengerID`).

### Basic merge example (inner join by default):

```python
# Merge on 'PassengerID' (inner join)
pd.merge(df1, df2, on='PassengerID')
```

---

## What do the different joins mean? Here's a quick guide:

| Type    | Description                     | Resulting dataset includes?                          | Visual analogy                     |
|---------|---------------------------------|------------------------------------------------------|-------------------------------------|
| **Inner**   | Only the intersection (common keys) | Passengers that are in both datasets                | Venn diagram with overlapping area |
| **Outer**   | All keys (union), include *all* data  | All passengers, label NaNs where data missing    | Full Venn diagram with entire circles |
| **Left**    | All keys from the *left* dataset     | All in df1, matching df2 where available       | Left circle full, right intersect side only |
| **Right**   | All keys from the *right* dataset    | All in df2, matching df1 where available       | Right circle full, left intersect side only |

---

# 5. Visualizing joins with Venn diagrams

Let's visualize the sets of data with simple Venn diagrams.

```python
import matplotlib_venn as venn

# Create sets of Passenger IDs
set1 = set(df1['PassengerID'])
set2 = set(df2['PassengerID'])

# Plot Venn diagrams for each join type
plt.figure(figsize=(10,4))

# Inner join
plt.subplot(1, 2, 1)
venn.venn2([set1, set2], set_labels=('df1', 'df2'))
plt.title('Inner Join')

# Outer join (union)
plt.subplot(1, 2, 2)
venn.venn2([set1, set2], set_labels=('df1', 'df2'))
plt.title('Outer Join (Union)')

plt.tight_layout()
plt.show()
```

*Prompt:*  
- Try making diagrams for `left` and `right` joins!  
- Think about how these sets overlap or don't overlap.  

---

# 6. Practical example: Complex merge with multiple keys

Suppose we have an extended Titanic dataset (or made-up extended info). For example:

```python
# Passengers with Bookings and Ticket info
df3 = pd.DataFrame({
    'PassengerID': [1, 2, 3, 4, 7],
    'TicketNumber': ['A123', 'B456', 'C789', 'D012', 'E345']
})

# Merge `df1` with `df3` on PassengerID (inner join)
pd.merge(df1, df3, on='PassengerID')
```

---

# 7. Play Time! Your turn

**Prompt:**

- Create your own small datasets about a topic you like (books, movies, etc.)
- Make sure there's a key column (like ISBN, Title)
- Practice merging datasets with different join types
- Visualize overlaps or differences with venn diagrams or scatter plots

---

# 8. Recap: When to Use Which?

- Use `concat` to stack datasets with similar structures.
- Use `merge` to combine datasets on shared info (keys).
- Choose `inner`, `outer`, `left`, or `right` depending on which data you want to keep.

---

# 9. Bonus: Tips to avoid common pitfalls

- Always check your data types before merging (`.dtypes`)
- Examine the key column for duplicates or missing data
- Visualize (with venn diagrams or plots) to confirm your join results
- Be explicit about the join type you want

---

# End of demo!  
Keep playing with pandas, merge, concat, and fun visualizations.  
Let's connect data to your real-world topics. Happy exploring!
