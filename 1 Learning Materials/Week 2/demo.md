# Week 2 Demo: Introduction to Matplotlib with NumPy

In this demo, we will begin with the *very basics* of plotting in Python using **Matplotlib**.  
We will use **NumPy** to generate data structures.  
Each step will be explicitly highlighted so you can clearly see how each component works.

---

## Step 1: Import the necessary libraries

```python
# Import NumPy for data creation
import numpy as np

# Import matplotlib.pyplot for plotting
import matplotlib.pyplot as plt
```

---

## Step 2: Create some data with NumPy

```python
# Create a simple data array: sequence of numbers from 0 to 9
x = np.arange(10)
# Create random data of the same length
y = np.random.rand(10)
```

*Comment:*  
- `np.arange(10)` creates a sequence of numbers [0, 1, 2, ..., 9].  
- `np.random.rand(10)` creates 10 random numbers between 0 and 1.

---

## Step 3: Start with a simple line plot

```python
# Create a new figure for plotting
plt.figure()

# Plot x against y as a line plot
plt.plot(x, y)

# Show the plot to display it
plt.show()
```

*Note:*  
- `plt.figure()` starts a new plot window.  
- `plt.plot()` creates a line connecting the points (x, y).  
- `plt.show()` displays the plot.

---

## Step 4: Customize the plot! (Add labels)

```python
plt.figure()

# Plot points with a blue line and circle markers
plt.plot(x, y, color='blue', marker='o', linestyle='-')

# Add a title
plt.title("My First Matplotlib Plot!")

# Add labels to axes
plt.xlabel("X Axis (the sequence of numbers)")
plt.ylabel("Y Axis (random data)")

# Display the plot
plt.show()
```

*Tip:*  
- `color='blue'` makes the line blue.  
- `marker='o'` adds circles at each data point.  
- `linestyle='-'` makes it a solid line.

---

## Step 5: Add multiple data series (more lines)

```python
# Generate another set of data
y2 = np.cos(x / 2)

plt.figure()

# Plot the first data: original y
plt.plot(x, y, color='blue', marker='o', linestyle='-' , label='Random Data')

# Plot the second data: cosine wave
plt.plot(x, y2, color='red', marker='x', linestyle='--' , label='Cosine Wave')

# Add title and labels
plt.title("Plot with Two Data Series")
plt.xlabel("X")
plt.ylabel("Y")
plt.legend()  # Show legend to distinguish lines

plt.show()
```

*Note:*  
- You can plot multiple lines with different styles and labels.  
- `plt.legend()` shows a key explaining each line.

---

## Step 6: Final comment: So many options!

Matplotlib is very powerful — here we just scratched the surface.  
You can change **colors**, **line styles**, **markers**, **titles**, **labels**, and **legends**.

Try exploring further! Change colors, mark points differently, or add gridlines.

---

# End of demo

*Enjoy exploring why plots help us understand data!*

