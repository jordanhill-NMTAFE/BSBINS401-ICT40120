
# Beginner-Friendly Introduction to Jupyter Notebooks

In this notebook, we will explore:
- What a Jupyter Notebook is and how it works
- How to create and run cells
- Useful keyboard shortcuts
- How to install and use extensions
- Understanding magic commands (`%`, `%%`, `!`)
- Building confidence for people new to programming and report writing

Let's get started!

---

# What is a Jupyter Notebook?

Jupyter Notebook is an interactive environment that lets you:
- Write and run code (like Python)
- Add explanatory text in Markdown
- See results immediately after running code cells
- Combine code, output, and notes in one document

This makes it a powerful tool for learning, exploring data, and preparing reports.

---

# Opening Your First Notebook

If you haven't installed Jupyter Notebook:

1. Install Python via Anaconda (recommended for beginners):  
[https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)

2. Launch Jupyter Notebook:
- Open Anaconda Navigator or open your terminal/command prompt
- Run:

```bash
jupyter notebook
```

3. Your default browser will open showing the Jupyter dashboard.

---

# Create Your First Notebook

- In the dashboard, click **"New"** at the top right
- Select **"Python 3"** (or your installed version)

A new tab will open with an empty notebook.

---

# Cells and How They Work

A notebook is made of **cells**:
- **Code cells:** Run Python code
- **Markdown cells:** Write explanations, headings, notes

To run a cell:
- Click on it to select
- Press **Shift + Enter** OR click **Run** button

---

# Example: Your First Code Cell

Let's write some simple Python code!

```python
# Assign two variables
a = 3
b = 4

# Calculate the sum
a + b
```

*How to execute:*

- Click the cell
- Hit **Shift + Enter**

You should see the output:
```
7
```

---

# Adding Explanatory Text with Markdown

Insert a new cell:
- Click the **+** button or press **B** (in command mode)
- Change the cell type to **Markdown** (from the dropdown menu or use keyboard shortcut `M` in command mode)

Write explanations like this:

```markdown
## Sample Explanation

This cell shows how to add two numbers in Python. Run the cell above to see the output.
```

Run the markdown cell with **Shift + Enter** to see it formatted.

---

# Markdown Tips for Clarity

- Use `#` for headings:
  
```markdown
# Main Title
## Subheading
### Smaller Heading
```

- Use `*` or `-` for lists:
  
```markdown
- Item 1
- Item 2
```

- **Bold**: `**text**`  
- *Italic*: `*text*`  

- Insert images:  
`![alt text](url)`

---

# Keyboard Shortcuts (Essential!)

In command mode:
- **A**: Insert new cell above
- **B**: Insert new cell below
- **M**: Change cell to Markdown
- **Y**: Change cell to Code
- **D, D**: Delete cell
- **Shift + Enter**: Run cell and go to next
- **Ctrl + Enter**: Run the current cell (stay here)
- **Esc**: Enter command mode

In editing mode (green border):
- Type normally to edit

---

# Using Python from a Code Cell

Let's make a simple plot.

```python
import numpy as np
import matplotlib.pyplot as plt

# Create some data
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Plot
plt.plot(x, y)
plt.title("Sine Wave")
plt.xlabel("X")
plt.ylabel("Y")
plt.show()
```

### Note:
- Run the cell with **Shift + Enter**
- A plot appears below

---

# Installing and Using Extensions (Optional)

Extensions can improve your experience!

In Jupyter:
- Install Nbextensions (via pip or conda):
  
```bash
conda install -c conda-forge jupyter_contrib_nbextensions
```

- Enable extensions through the tab `Nbextensions` in the dashboard.

**Using in VSCode**:
- Install [Visual Studio Code](https://code.visualstudio.com/)
- Add the **Python** extension
- Install **Jupyter** extension
- Open notebooks `.ipynb` directly

---

# Magic Commands: What Are They?

Magic commands start with `%` (single line) or `%%` (block/multiline). They make complex tasks easier.

### 1. `%` magic (single line)

```python
# Measure execution time of a command
%timeit np.sum(np.random.rand(1000))
```

### 2. `%%` magic (cell magic)

```python
# Run multiple lines with special behavior
%%time
total = 0
for i in range(10000):
    total += i
```

### 3. Shell commands with `!`

You can run terminal commands:

```python
# List files in current directory
!ls
```

*On Windows, use `!dir` instead of `ls`.*

---

# Example: More Magic Commands

```python
# Check current working directory
%pwd

# Run a shell command
!echo Hello, world!

# Load a CSV file directly
!head -n 5 dataset.csv
```

---

# Key Takeaways

- Cells can contain code or Markdown explanations.
- Keyboard shortcuts help you work faster.
- Extensions improve your notebook experience.
- Magic commands add powerful features without leaving the notebook.

---

# Practice!

- Write your own explanations in Markdown.
- Create plots with your data.
- Try magic commands `%timeit`, `!ls`, etc.

---

# Wrapping Up

Jupyter Notebooks are a beginner-friendly way to learn coding, explore data, and prepare reports all in one place.  
Take your time, experiment with cells, and have fun exploring!

---

# End of Demo

Happy coding!
```

---

Would you like me to produce this as an `.ipynb` file content (JSON) or give instructions on how to load this into Jupyter?