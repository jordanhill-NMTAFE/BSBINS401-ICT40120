---
footer: "![height:50px](footer.png)"
marp: true
theme: nmt-theme
title: "Session 6: Report Writing and Effective Visuals"
paginate: true
---

<!-- _class: lead -->
# BSBINS401 - Analyse and Present Research Information

## Session 6: Report Writing & Effective Visuals

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

1. Understand the core components of a well-structured report.  
2. Learn strategies for choosing effective visuals to support your findings.  
3. Explore Jupyter nbconvert for converting .ipynb notebooks to PDF.  
4. Demonstrate the workflow from notebook to a polished PDF report.  

---

## Session Overview

- Writing an Effective Report  
- Structuring Your Findings and Analysis  
- Selecting the Right Visuals  
- Introducing nbconvert  
- Demonstration: Converting .ipynb → PDF  
- Final Tips and Best Practices  

---

## 1. Writing an Effective Report

### Elements of a Comprehensive Report

<table style="width:100%;">
  <tr style="border: 1px solid #ddd;">
    <th>Section</th>
    <th>Contents / Purpose</th>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>Introduction</strong></td>
    <td>Clearly define research objectives, context, and scope</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>Methodology</strong></td>
    <td>Describe data collection, cleaning, analysis approaches</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>Analysis & Findings</strong></td>
    <td>Present data-driven insights, tables, and charts</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>Discussion</strong></td>
    <td>Interpret findings; link back to objectives; note limitations</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>Conclusions & Recommendations</strong></td>
    <td>Sum up key takeaways; outline potential next steps</td>
  </tr>
  <tr style="border:1px solid #ddd;">
    <td><strong>References & Appendices</strong></td>
    <td>Cite sources, include supplementary data or code</td>
  </tr>
</table>

---

## 2. Structuring Your Findings & Analysis

- **Flow of Information**:  
  - Start broad with context → Narrow down to specific analysis → Summarize key insights  
- **Maintain Clarity**:  
  - Use headings, bullet points, sub-sections  
  - Avoid jargon, or define it clearly
- **Tell a Story**:  
  - Guide readers through logical steps  
  - Provide necessary background and context  

---

## 3. Choosing Effective Visuals

1. **Relevance**: Does this visual directly support your key findings?  
2. **Simplicity**: Minimize clutter; highlight the most important data points.  
3. **Appropriate Graph Type**:  
   - Bar chart for categorical comparisons  
   - Line chart for trends over time  
   - Histogram for distribution  
   - Scatter plot for relationships (two variables)  
4. **Aesthetics**: Clear labels, consistent color scheme, readable font sizes  

---

## Example: Aligning Data to Visual Choice

<table style="margin-top: 1em; margin-bottom: 2em; width:100%; border-collapse: collapse;">
<tr style="border:1px solid #ddd;">
  <th style="border:1px solid #ddd; padding:8px;">Data / Finding</th>
  <th style="border:1px solid #ddd; padding:8px;">Possible Visual(s)</th>
  <th style="border:1px solid #ddd; padding:8px;">Why it Works</th>
</tr>
<tr style="border:1px solid #ddd;">
  <td style="padding:8px; border:1px solid #ddd;">Sales by Region</td>
  <td style="padding:8px; border:1px solid #ddd;">Bar Chart / Donut Chart</td>
  <td style="padding:8px; border:1px solid #ddd;">Compares discrete categories clearly</td>
</tr>
<tr style="border:1px solid #ddd;">
  <td style="padding:8px; border:1px solid #ddd;">Student Scores Over Time</td>
  <td style="padding:8px; border:1px solid #ddd;">Line Chart</td>
  <td style="padding:8px; border:1px solid #ddd;">Shows trends or fluctuations</td>
</tr>
<tr style="border:1px solid #ddd;">
  <td style="padding:8px; border:1px solid #ddd;">Two Variables Relationship</td>
  <td style="padding:8px; border:1px solid #ddd;">Scatter Plot</td>
  <td style="padding:8px; border:1px solid #ddd;">Reveals correlation or clustering</td>
</tr>
</table>

---

## 4. Introducing nbconvert

<br>

### **What is nbconvert?**

> “nbconvert” is a tool that allows you to convert Jupyter Notebooks to a variety of formats like HTML, PDF, and slides.

### **Why Use nbconvert?**
> Streamline your workflow from interactive exploration to final deliverables.  
> Share your work with stakeholders in PDF or HTML format.  
> Standardize reporting outputs in a reproducible manner.

---

## 5. Demo: Converting .ipynb → PDF

### Prerequisites
- Ensure you have a working LaTeX distribution for PDF export (e.g., MiKTeX, TeX Live).  
- Install nbconvert if not installed:
  ```bash
  pip install nbconvert
  ```
  
### Basic Command
```bash
jupyter nbconvert your_notebook.ipynb --to pdf
```

- This will generate a PDF in the same directory, using the default exporter.  

---

## Demonstration Steps
1. **Open Terminal/Command Prompt**  
2. **Navigate** to the folder containing your .ipynb file  
3. **Run** the nbconvert command:
   ```bash
   jupyter nbconvert MyAnalysis.ipynb --to pdf
   ```
4. Check for any errors (e.g., missing LaTeX components)  
5. **Locate** your newly created PDF in the same directory  

---

## 6. Best Practices for PDF Exports

1. **Clean Up the Notebook**  
   - Remove extraneous code cells or debugging outputs  
   - Add section headings and markdown explanations  
2. **Check Image Sizes**  
   - Large images may get clipped in PDFs  
3. **Use a Stylized Template (Optional)**  
   - You can customize nbconvert templates for consistent branding  
4. **Verify Font Rendering**  
   - Especially for special characters or math expressions  

---

## Activity: Practice Converting a Notebook

1. **Download** the sample Jupyter Notebook from the LMS (or create your own).  
2. **Edit** the notebook to include a short explanation, 1–2 visuals, and a conclusion.  
3. **Export** using nbconvert → PDF.  
4. **Review** the finished PDF for clarity and formatting.  

---

## Final Tips & Next Steps

- **Incorporate Effective Visuals**:  
  - Provide context, label axes, and include brief captions.  
- **Refine Your Report**:  
  - Structure it for readability.  
  - Use headings, bullet points, and short paragraphs.  
- **Prepare for Assessment 1**:  
  - Draft your methodology and findings with meaningful visuals.  
- **Next Session**:  
  - Peer review your initial report drafts.  
  - Discuss advanced presentation methods.

---

## Questions?

- Office Hours: Monday – Friday, 9 AM – 5 PM  
- Email: jordan.hill@nmtafe.wa.edu.au

![width:10%](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Question_mark.svg/240px-Question_mark.svg.png)
