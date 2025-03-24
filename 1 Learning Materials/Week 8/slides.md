---
footer: "![height:50px](footer.png)"
marp: true
theme: nmt-theme
title: "Session 8: Introducing More Advanced Data Analysis Techniques"
paginate: true
---

<!-- _class: lead -->
# BSBINS401 - Analyse and Present Research Information

## Week 8: Introducing More Advanced Data Analysis Techniques  

Lecturer: Jordan Hill

<style scoped>
  p {
    padding: 0.25em;
    padding-right: 1em;
    text-align: right;
  }
</style>

---

## Learning Objectives

1. Understand why we might need more detailed analysis methods beyond basic summaries.  
2. Explore basic approaches to identifying patterns and trends when multiple variables are involved (multivariate thinking).  
3. Gain familiarity with simple ways to compare groups (basic statistical tests).  
4. Learn how to visualize more complex relationships (Kaggle Learn Lesson 4: Scatter Plots, Lesson 5: Distributions).  
5. Reinforce best practices in data visualization and interpretation.

---

## Session Overview

- Why Look Beyond Simple Charts?  
- Comparing Groups: Basic Statistical Ideas  
- Introduction to “Multivariate Thinking”  
- Handling Complex Data (reminder: cleaning, missing values)  
- Hands-on with Kaggle Learn: Scatter Plots & Distributions  
- Activities and Next Steps

---

## 1. Why Look Beyond Simple Charts?

- When we have multiple variables (e.g., age, salary, department), a single average or bar chart might miss important information.  
- Organizations often need deeper insights:  
  - “Which factors might relate to higher sales?”  
  - “Do certain groups consistently score higher or show different behaviors?”  
- Moving beyond simple summaries can highlight hidden relationships or patterns.

---

## 2. Comparing Groups: Basic Statistical Ideas

### Example Scenario
• Suppose you have two groups (Group A and Group B) and you want to see if there’s a meaningful difference in their average test score or average salary.


<table style="width:100%; border-collapse: collapse;">
  <tr style="border:1px solid #ddd;">
    <th style="padding:8px;">Approach</th>
    <th style="padding:8px;">What It Does</th>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td style="padding:8px;"><strong>Visual Comparison</strong></td>
    <td style="padding:8px;">Simple bar chart or box plot side-by-side to see if one group is higher than the other.</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td style="padding:8px;"><strong>Basic Statistical Test</strong> (e.g., T-test)</td>
    <td style="padding:8px;">
      Checks (mathematically) if the difference you see might be due to chance or is likely real.
      <br/><em>(We typically get a “p-value” – a smaller p-value often suggests a real difference.)</em>
    </td>
  </tr>
</table>

---

## 3. Introduction to “Multivariate Thinking”

- **What does “multivariate” mean?**  
  It simply means two or more variables in play (e.g., salary, age, department, and performance score).  

- **Why is it helpful?**  
  - Real-world situations rarely hinge on just one variable.  
  - Sometimes, a combination of factors influences an outcome (e.g., department + age + education might all affect salary).

- **Example**:  
  - Could an employee’s “salary” be related both to “age” and “years of education”?  
  - Exploring more than one variable at a time gives richer insights.

---

## 4. Handling Complex Data (A Reminder)

<br>

<table style="width:100%; border-collapse: collapse;">
  <tr style="border:1px solid #ddd;">
    <td style="padding:8px; width:50%;">
      <strong>1. Data Cleaning</strong><br/>
      - Check for missing values or inconsistent data.<br/>
      - Decide how to handle them (drop, fill, or investigate further).
    </td>
    <td style="padding:8px; width:50%;">
      <strong>3. Visualization</strong><br/>
      - Summaries first (like describe(), histograms).<br/> 
      - Then consider more advanced plots (scatter plots across multiple variables).
    </td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td style="padding:8px; width:50%;">
      <strong>2. Documentation</strong><br/>
      - Keep a record of any cleaning steps or assumptions.
    </td>
    <td style="padding:8px; width:50%;">
      <strong>4. Interpret Carefully</strong><br/>
      - A pattern doesn't always mean "cause and effect."<br/>
      - We look for associations or relationships, not instant proof of causation.
    </td>
  </tr>
</table>

---

## 5. Hands-On: Kaggle Learn (Scatter Plots & Distributions)

<div style="margin-top:1em;">
  <table style="width:100%; border-collapse: collapse;">
    <tr style="border:1px solid #ddd;">
      <th style="border:1px solid #ddd; padding:8px;">Lesson</th>
      <th style="border:1px solid #ddd; padding:8px;">Key Focus</th>
      <th style="border:1px solid #ddd; padding:8px;">Link</th>
    </tr>
    <tr style="border:1px solid #ddd;">
      <td style="padding:8px;"><strong>Lesson 4: Scatter Plots</strong></td>
      <td style="padding:8px;">Visualizing relationships between two numeric variables.</td>
      <td style="padding:8px;"><a href="https://www.kaggle.com/code/alexisbcook/scatter-plots">Kaggle Scatter Plots</a></td>
    </tr>
    <tr style="border:1px solid #ddd;">
      <td style="padding:8px;"><strong>Lesson 5: Distributions</strong></td>
      <td style="padding:8px;">Understanding how observations spread out (histograms, box plots, etc.).</td>
      <td style="padding:8px;"><a href="https://www.kaggle.com/code/alexisbcook/distributions">Kaggle Distributions</a></td>
    </tr>
  </table>
</div>

---

### Activity: Visualizing Multiple Variables

1. **Scatter Plot**: Try plotting “salary” vs. “age,” and add color or markers for “department.”  
2. **Distribution Plot**: Examine how “salary” (or another continuous variable) is distributed. Is it skewed? Are there outliers?  
3. **Discussion**:  
   - Which variables might you compare in your own project?  
   - Did you notice any interesting clusters or big differences between groups?

---

## Additional Notes on Basic Analysis

- **Correlation**:  
  - A quick measure to see if two numeric variables move together (positively or negatively).  
  - Ranges from -1 (perfect negative) to +1 (perfect positive). A correlation near 0 means little linear relationship.  
  - Remember: correlation ≠ causation.
  
- **Regression** 
  - A method to see how one or more variables predict another.  
---

## 6. In-Class Exercises

1. **Scatter Plot & Correlation Check**  
   - Choose any two numeric variables from a dataset (e.g., Kaggle’s “Employee Attrition” or your own).  
   - Create a scatter plot; calculate correlation with a single line of code (e.g., df.corr()).  
2. **Compare Two Groups**  
   - If you have a categorical variable with two groups (like “North” vs “South”), compare a numeric outcome (like average monthly income). A bar chart is fine!  
   - (Optional) For the more adventurous, attempt a straightforward t-test with your lecturer’s guidance.

---

## Next Steps

1. **Practice** the scatter plot, correlation, and group comparison methods on your own dataset.  
2. **Document** any new findings or interesting relationships.  
3. **Consider** how these methods might inform the next stage of your research project or final report.  

---

## Questions?

• Email: jordan.hill@nmtafe.wa.edu.au  
• Office Hours: Mon–Fri, 9 AM – 5 PM  

![width:10%](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Question_mark.svg/240px-Question_mark.svg.png)