Certainly! Here's the updated `demo.md` with added descriptions and narrative that explain what each step is doing, suitable for a Week 3 demo. The code blocks remain plain markdown style for seamless conversion.

---

# Working with Matplotlib and Seaborn

This demo introduces basic data visualization in Python. We'll start by creating sample data using NumPy, then use Matplotlib to produce simple plots. Afterwards, we'll demonstrate how Seaborn makes it easier and more elegant to create visualizations when working directly with pandas DataFrames.

---

## 1. Importing Libraries

We begin by importing the necessary Python libraries:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Setting Seaborn style for more attractive default plots
sns.set_style('whitegrid')
```

Matplotlib and Seaborn are both powerful visualization libraries. Seaborn is built on top of Matplotlib and provides simplified and styled functions for common chart types.

---

## 2. Creating Sample Data with NumPy

Next, we generate some random data to visualize. Using NumPy, we create an array of 100 random numbers following a normal distribution.

```python
np.random.seed(0)
data = np.random.randn(100)  # Generate 100 random values from a standard normal distribution
```

This data will serve as our dataset for plotting. Setting the seed ensures reproducibility.

---

## 3. Plotting with Matplotlib: Basic Line Chart

Let's start by plotting this data as a simple line chart with Matplotlib, which is a fundamental plotting library in Python. 

```python
plt.figure(figsize=(8, 4))
plt.plot(data, color='blue', marker='o', linestyle='-')
plt.title('Matplotlib Basic Line Plot')
plt.xlabel('Index')
plt.ylabel('Value')
plt.show()
```

Here, we specify the figure size, plot the data points connected by lines, and add axis labels and a title. This basic approach is good for quick visual checks but can be verbose when customizing multiple plots.

---

## 4. Creating a Histogram for Data Distribution

Let's visualize the distribution of the data with a histogram, which shows how data points are spread across different ranges.

```python
plt.figure(figsize=(8, 4))
plt.hist(data, bins=15, color='skyblue', edgecolor='black')
plt.title('Histogram of Data (Matplotlib)')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()
```

The number of bins controls the granularity. Histograms are essential for understanding data spread and skewness.

---

## 5. Using Pandas DataFrame for More Structured Data

Instead of just raw arrays, pandas DataFrames are convenient for working with labeled data with multiple columns. Let's add a categorical variable and create a DataFrame.

```python
df = pd.DataFrame({
    'score': data,
    'category': np.random.choice(['A', 'B'], size=100)
})
df.head()
```

This DataFrame includes scores and categories, which makes it easy to create grouped or category-based plots.

---

## 6. Plotting with Seaborn: Easier and More Aesthetic

Seaborn is designed to work seamlessly with pandas DataFrames using column labels, reducing the amount of code needed and producing more attractive visuals.

### a) Scatterplot: Visualizing Data Points

```python
sns.scatterplot(x='score', y='score', data=df, hue='category')
plt.title('Seaborn Scatterplot')
plt.show()
```

This plot shows individual data points, with color coding to distinguish categories. Seaborn automatically styles the plot, making it more professional without much effort.

---

### b) Boxplot: Comparing Distributions Across Categories

```python
sns.boxplot(x='category', y='score', data=df)
plt.title('Boxplot by Category')
plt.show()
```

Boxplots summarize the distribution, median, and outliers within each category, offering a quick way to compare groups visually.

---

### c) Distribution Plot (Histogram + KDE): Details of Data Distribution

```python
sns.histplot(data=df, x='score', hue='category', kde=True)
plt.title('Distribution of Scores with KDE')
plt.show()
```

This combines a histogram with Kernel Density Estimation (KDE), providing a smooth estimate of the data distribution. Adding `hue='category'` compares categories.

---

## 7. Why Use Seaborn with DataFrames?

- **Simpler syntax:** You specify column names directly, e.g., `x='score'`.
- **Default attractive styles:** No need for extensive styling code.
- **Built-in support for advanced plots:** Pairplots, heatmaps, violin plots, etc.
- **Integrates smoothly with pandas:** No need to manually extract arrays.

---

## 8. Summary Comparison

| Aspect | Matplotlib | Seaborn |
|---------|--------------|---------|
| Data source | Arrays, lists | pandas DataFrame columns or Series |
| Ease of use | More verbose | Concise, high-level API |
| Styling | Customizable but manual | Attractive default styles |
| Plot variety | Basic plots | Statistical, categorical, and complex plots |

Matplotlib provides detailed control, but for quick, publication-ready visuals, Seaborn often makes life easier.

---

## Final note

In practice, combining both tools allows for powerful and fast visualization workflows. Use Matplotlib when you need fine control, and Seaborn for quick statistical plots with style.

Would you like me to prepare this as a Jupyter notebook with all code snippets and explanations?