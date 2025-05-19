
# Week 5: Applying Data Analysis and Visualization to Uncover Insights

In this demo, we'll explore how to use visualization tools (Matplotlib, Seaborn) to understand key features and relationships in a dataset. We will also examine a correlation matrix to connect visual insights with statistical relationships. Our goal is to identify patterns, outliers, and correlations that help interpret the data meaningfully.

---

## 1. Load and Inspect the Dataset

We'll use the famous Iris dataset, easily loaded via Seaborn:

```python
import seaborn as sns
import pandas as pd

# Load Iris dataset
iris = sns.load_dataset('iris')

# Preview the data
iris.head()
```

---

## 2. Visualizing Distributions and Outliers

### a) Histograms of Sepal Length and Width

```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10,4))
sns.histplot(iris['sepal_length'], bins=15, kde=True)
plt.title('Distribution of Sepal Length')
plt.xlabel('Sepal Length (cm)')
plt.ylabel('Count')
plt.show()

plt.figure(figsize=(10,4))
sns.histplot(iris['sepal_width'], bins=15, kde=True)
plt.title('Distribution of Sepal Width')
plt.xlabel('Sepal Width (cm)')
plt.ylabel('Count')
plt.show()
```

*Insight:* These histograms are useful for identifying outliers and understanding feature shapes.

---

### b) Boxplots to Spot Outliers and Compare Groups

```python
plt.figure(figsize=(8,6))
sns.boxplot(x='species', y='sepal_length', data=iris)
plt.title('Sepal Length by Iris Species')
plt.show()

plt.figure(figsize=(8,6))
sns.boxplot(x='species', y='sepal_width', data=iris)
plt.title('Sepal Width by Iris Species')
plt.show()
```

*Insight:* Boxplots reveal outliers and differences across species.

---

## 3. Exploring Relationships with Scatterplots

### a) Sepal Length vs. Width by Species

```python
sns.scatterplot(x='sepal_length', y='sepal_width', hue='species', data=iris)
plt.title('Sepal Dimensions by Species')
plt.show()
```

*Insight:* Visualize how features relate and differ among species.

---

### b) Pairplot of Multiple Features

```python
sns.pairplot(iris, hue='species')
plt.suptitle('Pairplot of Iris Features', y=1.02)
plt.show()
```

*Insight:* Pairplots reveal relationships and correlation patterns across features.

---

## 4. Correlation Matrix and Heatmap

Now, connect these visual insights with a correlation matrix to quantify linear relationships:

```python
# Select only numeric columns for correlation
numeric_cols = iris.select_dtypes(include='number')
corr_matrix = numeric_cols.corr()

# Plot heatmap
plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Matrix of Iris Features')
plt.show()
```

*Insight:* The heatmap shows strong positive correlations especially between sepal length and petal length (~0.87), supporting the visual trends.

---

## 5. Connecting Visuals and Correlations

- The high correlation between sepal length and petal length aligns with scatterplots showing their relationship.
- Outliers in boxplots or scatterplots can influence correlation metrics; interpret with context.

---

## 6. Summary

- Use histograms and boxplots to understand data distributions and see outliers.
- Use scatterplots and pairplots to investigate feature relationships.
- Use a correlation heatmap for a quick overview of linear relationships, confirming visual observations.
- Combining visualization approaches provides a comprehensive data understanding.

