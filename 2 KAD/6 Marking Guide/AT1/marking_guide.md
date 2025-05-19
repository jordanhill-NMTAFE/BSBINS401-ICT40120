---
title: "Assessment 1 Marking Guide"
subtitle: "BSBINS401 - Analyse and Present Research Information"
date: "2023-XX-XX"
---

# Assessment 1 Marking Guide

**Qualification**: ICT40120 Certificate IV in Information Technology (Data Science and AI)  
**Unit**: BSBINS401 – Analyse and Present Research Information  
**Assessment**: Assessment 1: Analysis and Presentation of a Standard Dataset  
**Assessor**: [Assessor Name]  
**Date**: [Date]

---

## Overview

- **Assessment Components**:
  - **Written Report**: Students submit a comprehensive report detailing their research and analysis.
  - **In-Class Presentation**: Students deliver a presentation summarizing their findings.

- **Focus**: This assessment evaluates the student's ability to conduct research, analyze data, and present findings in alignment with BSBINS401 performance criteria and knowledge evidence.

- **Marking**: Competency-based (Satisfactory/Not Yet Satisfactory)

This marking guide provides:

1. **Notes to the Marker**:
   - Key points to assess in the student's response.
   - How each task relates to specific elements and performance criteria of BSBINS401.

2. **Example Response**:
   - A sample answer or key components that meet the required criteria.

---

## Marking Guidelines

- **Satisfactory (S)**: The student's response meets all the key requirements for the task, demonstrating competence as outlined in the performance criteria and foundation skills.
- **Not Yet Satisfactory (NYS)**: The student's response is missing key elements or demonstrates gaps in understanding, and does not meet the requirements for competence.

---

## Assessment Tasks

### Task 1: Identify Research Objectives and Strategy

#### **Notes to the Marker**

- **Key Points to Assess**:
  - Clear identification of at least two specific research objectives relevant to the provided dataset.
  - Alignment of research objectives with the organizational requirements (as per the given scenario).
  - A well-defined research strategy that is appropriate for achieving the objectives.
  - Evidence of understanding the dataset's context and potential insights.

- **Relation to BSBINS401**:
  - **Element 1**: Identify and confirm research strategy.
  - **Performance Criteria**:
    - **1.1**: Identify research objectives according to organizational requirements.
    - **1.4**: Identify and confirm information research strategy is relevant to research objectives.

- **Foundation Skills**:
  - **Reading**: Interprets and analyses information from the dataset and background materials.
  - **Planning and Organizing**: Develops a structured research approach.

#### **Example Response**

**Research Objectives and Strategy**

*Research Objectives*:

1. **Identify the key factors contributing to employee attrition within the organization.**
2. **Analyze the relationship between employee satisfaction scores and departmental performance metrics.**

*Research Strategy*:

To address these objectives, the research will involve:

- **Data Exploration**: Initial examination of the dataset to understand available variables.
- **Descriptive Statistics**: Calculating means, medians, and distribution characteristics for key variables.
- **Correlation Analysis**: Assessing relationships between variables such as satisfaction scores and attrition rates.
- **Visualization Techniques**: Using plots and charts to identify patterns and trends.
- **Focus on Organizational Requirements**: Aligning findings with the organization's aim to reduce attrition and improve departmental performance.

---

### Task 2: Collect and Organize Data

#### **Notes to the Marker**

- **Key Points to Assess**:
  - Effective extraction of relevant data from the provided dataset.
  - Logical organization of data suitable for analysis (e.g., cleaned dataframes).
  - Explanation of data storage methods, including security considerations.

- **Relation to BSBINS401**:
  - **Element 2**: Collect and store research information.
  - **Performance Criteria**:
    - **2.1**: Access and extract relevant information in a format suitable for analysis.
    - **2.2**: Store research information according to security requirements and organizational policies.

- **Foundation Skills**:
  - **Technology**: Uses digital tools effectively to manipulate data.
  - **Numeracy**: Handles and processes numerical data accurately.

#### **Example Response**

**Data Collection and Organization**

- **Data Extraction**:

  The dataset was accessed from the LMS and loaded into a Jupyter Notebook using Pandas:

  ```python
  import pandas as pd
  df = pd.read_csv('employee_attrition.csv')
  ```

- **Data Cleaning**:

  - **Handled Missing Values**: Identified and addressed missing data using `df.isnull().sum()` and imputed or dropped as appropriate.
  - **Data Types**: Ensured all variables had correct data types for analysis (e.g., converting "Age" to integer).

- **Data Organization**:

  - Created new dataframes focusing on variables relevant to the research objectives, such as `attrition_df` containing only employees who have left the company.
  - Structured data to facilitate correlation and regression analyses.

- **Data Storage and Security**:

  - Stored the cleaned data securely on the organization's encrypted cloud storage.
  - Access permissions were set to restrict data to authorized personnel only.
  - Complied with the organization's data protection policies as outlined in the staff handbook.

---

### Task 3: Analyze Data and Draw Conclusions

#### **Notes to the Marker**

- **Key Points to Assess**:
  - Use of appropriate data analysis techniques to address research objectives.
  - Identification of key themes, patterns, or trends.
  - Conclusions are clear, justified, and supported by evidence from the analysis.
  - Assumptions made are explicitly stated and reasonable.

- **Relation to BSBINS401**:
  - **Element 3**: Analyze and synthesize research information.
  - **Performance Criteria**:
    - **3.1**: Analyze stored information according to the research strategy.
    - **3.2**: Identify themes and draw conclusions.
    - **3.3**: Demonstrate that assumptions and conclusions are justified and supported by evidence.

- **Foundation Skills**:
  - **Problem Solving**: Identifies trends and interprets data.
  - **Critical Thinking**: Evaluates information to form conclusions.

#### **Example Response**

**Data Analysis and Findings**

- **Analysis Methods**:

  - **Correlation Analysis**: Computed correlation coefficients between employee satisfaction scores and attrition rates.
  
    ```python
    corr = df['SatisfactionScore'].corr(df['Attrition'])
    ```
  
  - **Visualization**: Generated a heatmap to visualize correlations and bar charts to compare attrition rates across departments.

- **Key Findings**:

  - **Finding 1**: There is a strong negative correlation (-0.68) between employee satisfaction scores and attrition, indicating that lower satisfaction is associated with higher attrition.
  - **Finding 2**: Departments such as Sales and Customer Service have higher attrition rates compared to others.

- **Conclusions**:

  - **Conclusion 1**: Enhancing employee satisfaction could significantly reduce attrition rates.
  - **Conclusion 2**: Targeted interventions in high-attrition departments may be necessary.

- **Assumptions**:

  - Assumed that the satisfaction scores are an accurate reflection of employee sentiment.
  - Assumed that the data is representative of the entire organization.

---

### Task 4: Prepare the Written Report

#### **Notes to the Marker**

- **Key Points to Assess**:
  - The report follows a logical structure with all required sections.
  - Professional language, clear writing, and appropriate formatting.
  - Inclusion of visualizations that effectively support the findings.
  - Alignment with organizational requirements and intended audience.

- **Relation to BSBINS401**:
  - **Element 4**: Present research information.
  - **Performance Criteria**:
    - **4.1**: Identify methods of reporting that align with the intended audience and organizational requirements.
    - **4.2**: Prepare research report on findings.

- **Foundation Skills**:
  - **Writing**: Communicates information clearly in written format.
  - **Planning and Organizing**: Structures the report effectively.

#### **Example Response**

*As this is a marking guide, an example response is a summary of what should be included rather than the full report.*

**Report Content Overview**:

- **Executive Summary**:

  - Summarizes the research objectives, methods, key findings, and recommendations.

- **Introduction**:

  - Provides background on the importance of studying employee attrition.
  - States the research objectives clearly.

- **Methodology**:

  - Describes the dataset and variables used.
  - Explains the analysis techniques employed.

- **Analysis and Findings**:

  - Presents the results with accompanying charts and graphs.
  - Interprets the data in the context of the research objectives.

- **Conclusions and Recommendations**:

  - Highlights the main conclusions drawn from the analysis.
  - Offers evidence-based recommendations for the organization.

- **References and Appendices**:

  - Includes any references to literature or organizational documents.
  - Provides supplementary materials such as code snippets.

**Visualizations Included**:

- Correlation heatmap.
- Bar charts comparing attrition rates by department.
- Scatter plot of satisfaction scores versus attrition.

---

### Task 5: Deliver the Presentation

#### **Notes to the Marker**

- **Key Points to Assess**:
  - Clarity and effectiveness of the presentation.
  - Ability to articulate research objectives, methodology, findings, and conclusions.
  - Use of visual aids to enhance understanding.
  - Engagement with the audience and responsiveness to questions.
  - Adherence to time limits and professional presentation skills.

- **Relation to BSBINS401**:
  - **Element 4**: Present research information.
  - **Performance Criteria**:
    - **4.1**: Identify methods of reporting that align with the intended audience and organizational requirements.
    - **4.5**: Present research findings according to organizational requirements.

- **Foundation Skills**:
  - **Oral Communication**: Articulates information clearly.
  - **Interpersonal Skills**: Engages with the audience.

#### **Example Response**

*As this is a marking guide, the example response notes key components expected in the presentation.*

**Presentation Components**:

- **Introduction Slide**:

  - Briefly introduces the topic, student name, and purpose of the presentation.

- **Overview of Research Objectives**:

  - Clearly states the objectives addressed.

- **Methodology**:

  - Summarizes the data sources and analysis techniques.

- **Findings**:

  - Highlights key findings with visual support (charts/graphs).

- **Conclusions and Recommendations**:

  - Summarizes conclusions drawn and suggests actionable recommendations for the organization.

- **Engagement**:

  - Uses clear language and pacing.
  - Invites questions and responds appropriately.

**Visual Aids**:

- Slides are well-designed with appropriate use of graphics.
- Text is legible and not overcrowded.

---

## Overall Assessment

- **Observe** the student's capabilities across tasks for evidence of competence.
- **Provide Feedback**: Offer constructive feedback on strengths and areas for improvement.
- **Assessment Decision**:

  - **Satisfactory (S)**: The student has met all the requirements across the tasks.
  - **Not Yet Satisfactory (NYS)**: The student needs to address gaps as per feedback.

