---
title: "Assessment 2 Marking Guide"
subtitle: "BSBINS401 - Analyse and Present Research Information"
date: "2023-XX-XX"
---
    
# Assessment 2 Marking Guide
    
**Qualification**: ICT40120 Certificate IV in Information Technology (Data Science and AI)  
**Unit**: BSBINS401 – Analyse and Present Research Information  
**Assessment**: Assessment 2: Independent Research Project Final Report and Presentation  
**Assessor**: [Assessor Name]  
**Date**: [Date]
    
---
    
## Overview
    
- **Assessment Components**:
  - **Research Proposal**: Submitted earlier in Week 10.
  - **Final Report**: Comprehensive report detailing research and analysis.
  - **In-Class Presentation**: Presentation summarizing research findings.
    
- **Focus**: This assessment evaluates the student's ability to independently conduct research, analyze data, and present findings in alignment with BSBINS401 performance criteria and knowledge evidence.
    
- **Marking**: Competency-based (Satisfactory/Not Yet Satisfactory)
    
This marking guide provides:
    
1. **Notes to the Marker**:
   - Key points to assess in each student's response.
   - How each task relates to specific elements and performance criteria of BSBINS401.
    
2. **Example Response**:
   - A sample answer or key components that meet the required criteria for each task.
    
---
    
## Marking Guidelines
    
- **Satisfactory (S)**: The student's response meets all the key requirements for the task, demonstrating competence as outlined in the performance criteria and foundation skills.
    
- **Not Yet Satisfactory (NYS)**: The student's response is missing key elements or demonstrates gaps in understanding, and does not meet the requirements for competence.
    
---
    
## Assessment Tasks
    
### **Task 1: Identify Research Objectives and Develop Research Strategy**
    
#### **Notes to the Marker**
    
- **Key Points to Assess**:
  - **Research Objectives**:
    - Clear identification of at least two specific research objectives relevant to the chosen topic.
    - Objectives align with organizational requirements and address a real-world problem or opportunity.
  - **Research Strategy**:
    - Well-defined strategy outlining methods and approaches to achieve the research objectives.
    - Appropriateness and feasibility of the strategy in the context of the project.
    - Consideration of data sources, analysis techniques, and timeline.
    
- **Relation to BSBINS401 Knowledge Elements**:
  - **Knowledge Evidence 1**:
    - Identify and confirm research strategy.
    
- **Foundation Skills**:
  - **Reading**: Interprets and analyses information from datasets and background materials.
  - **Planning and Organizing**: Develops a structured research approach.
    
#### **Example Response**
    
**Research Objectives and Strategy**
    
*Research Objectives*:
    
1. **Determine the key factors influencing customer satisfaction in the e-commerce sector.**
2. **Analyze the relationship between website usability and conversion rates.**
    
*Research Strategy*:
    
To achieve these objectives, the research will involve:
    
- **Data Collection**: Gathering data from customer surveys, website analytics, and transaction records.
- **Data Cleaning and Preparation**: Using Python and Pandas to clean the data, handle missing values, and prepare it for analysis.
- **Descriptive Analysis**: Calculating summary statistics to understand the distribution of key variables.
- **Correlation Analysis**: Utilizing statistical methods to identify relationships between website usability metrics and conversion rates.
- **Visualization**: Creating visualizations with Matplotlib and Seaborn to illustrate findings.
- **Reporting**: Compiling the analysis into a comprehensive report and preparing an in-class presentation to communicate the results.
    
This strategy aligns with organizational goals to enhance customer experience and increase sales through improved website design.
    
---
    
### **Task 2: Collect and Store Research Information**
    
#### **Notes to the Marker**
    
- **Key Points to Assess**:
  - **Data Collection**:
    - Effective extraction of relevant data from chosen sources.
    - Utilization of appropriate tools and techniques for data gathering.
  - **Data Organization**:
    - Logical structuring of data suitable for analysis (e.g., clean dataframes).
    - Proper handling of different data types and formats.
  - **Data Storage**:
    - Secure storage methods adhering to organizational policies.
    - Implementation of data protection measures (e.g., encryption, access controls).
    
- **Relation to BSBINS401 Knowledge Elements**:
  - **Knowledge Evidence 2**:
    - Collect and store research information.
    
- **Foundation Skills**:
  - **Technology**: Uses digital tools effectively to manipulate and store data.
  - **Numeracy**: Handles and processes numerical data accurately.
    
#### **Example Response**
    
**Data Collection and Storage**
    
- **Data Collection**:
    
  The dataset was sourced from Kaggle’s “E-commerce Customer Satisfaction” repository. Data extraction was performed using the following Python code:
    
  ```python
  import pandas as pd
    
  # Load the dataset
  df = pd.read_csv('ecommerce_customer_satisfaction.csv')
  ```
    
- **Data Cleaning**:
    
  - **Handled Missing Values**: Applied imputation for missing satisfaction scores using the mean value.
  - **Data Type Conversion**: Converted the “PurchaseAmount” column from string to float.
    
  ```python
  # Impute missing values
  df['SatisfactionScore'].fillna(df['SatisfactionScore'].mean(), inplace=True)
    
  # Convert data types
  df['PurchaseAmount'] = df['PurchaseAmount'].replace('[\$,]', '', regex=True).astype(float)
  ```
    
- **Data Organization**:
    
  - Filtered the dataset to include only relevant columns: `CustomerID`, `WebsiteUsabilityScore`, `SatisfactionScore`, `ConversionRate`.
  - Created a cleaned dataframe ready for analysis.
    
- **Data Storage**:
    
  - Stored the cleaned data in an encrypted cloud storage solution provided by the organization.
  - Set up access controls to ensure only the research team had access to the data.
  - Backed up the data regularly to prevent loss.
    
  ```python
  # Save the cleaned data to a secure location
  df.to_csv('/secure_storage/ecommerce_cleaned.csv', index=False, encryption=True)
  ```
    
  Compliance with the organization’s data security policies was maintained by restricting access to authorized personnel and ensuring data was encrypted both in transit and at rest.
    
---
    
### **Task 3: Analyse Information and Synthesise Findings**
    
#### **Notes to the Marker**
    
- **Key Points to Assess**:
  - **Data Analysis**:
    - Application of appropriate analytical methods to address research objectives.
    - Use of statistical techniques and data visualization to uncover patterns and relationships.
  - **Synthesis of Findings**:
    - Identification of key themes and insights derived from the analysis.
    - Logical and evidence-based conclusions that align with research objectives.
  - **Assumptions and Justifications**:
    - Clearly stated assumptions underlying the analysis.
    - Justification of conclusions with support from data.
    
- **Relation to BSBINS401 Knowledge Elements**:
  - **Knowledge Evidence 3**:
    - Analyse and synthesize research information.
    
- **Foundation Skills**:
  - **Problem Solving**: Identifies trends and interprets data.
  - **Critical Thinking**: Evaluates information to form conclusions.
    
#### **Example Response**
    
**Data Analysis and Findings**
    
- **Descriptive Statistics**:
    
  Calculated summary statistics to understand the distribution of customer satisfaction scores and conversion rates.
    
  ```python
  # Summary statistics
  print(df[['SatisfactionScore', 'ConversionRate']].describe())
  ```
    
- **Correlation Analysis**:
    
  Analyzed the relationship between website usability scores and conversion rates.
    
  ```python
  # Correlation matrix
  corr_matrix = df[['WebsiteUsabilityScore', 'ConversionRate']].corr()
  print(corr_matrix)
  ```
    
  The correlation coefficient of 0.72 indicates a strong positive relationship between website usability and conversion rates.
    
- **Visualization**:
    
  Created scatter plots to visualize the relationship between website usability and conversion rates.
    
  ```python
  import seaborn as sns
  import matplotlib.pyplot as plt
    
  sns.scatterplot(data=df, x='WebsiteUsabilityScore', y='ConversionRate')
  plt.title('Website Usability vs Conversion Rate')
  plt.show()
  ```
    
  The scatter plot shows a clear trend where higher usability scores are associated with higher conversion rates, reinforcing the correlation analysis.
    
- **Key Findings**:
    
  1. **Positive Correlation**: There is a strong positive correlation between website usability and conversion rates, suggesting that improvements in website design can lead to increased sales.
    
  2. **Customer Satisfaction Impact**: Higher satisfaction scores are linked to better conversion rates, indicating that customer satisfaction is a critical factor in driving business success.
    
- **Conclusions**:
    
  Based on the analysis, enhancing website usability can significantly boost conversion rates. Additionally, focusing on increasing customer satisfaction should be a priority to maintain and grow sales figures.
    
- **Assumptions**:
    
  - Assumed that the dataset accurately represents the customer base and their interactions with the website.
  - Assumed that all relevant variables have been included and that there are no significant external factors influencing the results.
    
---
    
### **Task 4: Prepare the Final Report**
    
#### **Notes to the Marker**
    
- **Key Points to Assess**:
  - **Report Structure**:
    - Adherence to the provided report template and organizational guidelines.
    - Inclusion of all required sections: Executive Summary, Introduction, Methodology, Analysis and Findings, Conclusions and Recommendations, References, Appendices.
  - **Professionalism and Clarity**:
    - Use of clear and concise language.
    - Logical flow and organization of content.
    - Proper formatting and adherence to word limits.
  - **Visual Aids**:
    - Effective use of charts, graphs, and tables to support analysis.
    - Visuals are well-integrated into the narrative and appropriately labeled.
  - **Alignment with Organizational Requirements**:
    - Report meets the needs of the intended audience.
    - Recommendations are actionable and aligned with organizational goals.
    
- **Relation to BSBINS401 Knowledge Elements**:
  - **Knowledge Evidence 4**:
    - Form and content of research reports required by the organisation.
    
- **Foundation Skills**:
  - **Writing**: Communicates information clearly in written format.
  - **Reading**: Interprets and analyses information from various sources.
  - **Planning and Organizing**: Structures the report effectively.
    
#### **Example Response**
    
**Final Report Structure**
    
1. **Executive Summary**
    
   - Overview of research objectives, methods, key findings, and recommendations.
    
2. **Introduction**
    
   - Background on the importance of website usability and customer satisfaction in e-commerce.
   - Statement of research objectives.
    
3. **Methodology**
    
   - Description of data sources and variables used.
   - Explanation of data cleaning and analysis techniques.
    
4. **Analysis and Findings**
    
   - **Descriptive Statistics**: Summary of customer satisfaction scores and conversion rates.
   - **Correlation Analysis**: Detailed discussion of the relationship between website usability and conversion rates.
   - **Visualizations**: Scatter plots and correlation heatmaps illustrating key findings.
    
5. **Conclusions and Recommendations**
    
   - **Conclusions**:
     - Enhancing website usability can significantly improve conversion rates.
     - Increasing customer satisfaction is essential for sustaining sales growth.
   
   - **Recommendations**:
     - Invest in user experience (UX) improvements based on usability scores.
     - Implement customer feedback mechanisms to continuously monitor and enhance satisfaction.
    
6. **References**
    
   - Citations of all data sources, literature, and tools used in the research.
    
7. **Appendices**
    
   - Supplementary materials such as detailed analysis code, additional charts, and raw data excerpts.
    
**Visual Aids Included**:
    
- Correlation heatmap showcasing the relationship between variables.
- Scatter plot illustrating the link between website usability and conversion rates.
- Bar charts comparing satisfaction scores across different customer segments.
    
**Professionalism and Clarity**:
    
- The report uses formal language appropriate for a professional audience.
- Logical flow from introduction to conclusions ensures readability and comprehension.
- Visual aids are clearly labeled and referenced within the text to support analysis.
    
**Alignment with Organizational Requirements**:
    
- Recommendations are tailored to the organization’s goal of improving e-commerce performance.
- Visualizations and analyses are directly relevant to strategic decision-making processes.
    
---
    
### **Task 5: Present Research Information and Obtain Feedback**
    
#### **Notes to the Marker**
    
- **Key Points to Assess**:
  - **Presentation Content**:
    - Clear articulation of research objectives, methodology, findings, and conclusions.
    - Logical progression of information and storytelling.
  - **Delivery Skills**:
    - Confident and clear speaking.
    - Effective use of visual aids to enhance understanding.
    - Engagement with the audience, maintaining eye contact, and appropriate pacing.
  - **Use of Visual Aids**:
    - Quality and clarity of slides.
    - Integration of visualizations to support key points.
  - **Handling Questions and Feedback**:
    - Ability to respond accurately and thoughtfully to audience questions.
    - Receptiveness to feedback and constructive discussions.
    
- **Relation to BSBINS401 Knowledge Elements**:
  - **Knowledge Evidence 4**:
    - Present research information.
    
- **Foundation Skills**:
  - **Oral Communication**: Articulates information clearly and confidently.
  - **Interpersonal Skills**: Engages effectively with the audience.
  - **Technology**: Utilizes presentation tools proficiently.
    
#### **Example Response**
    
**Presentation Structure**
    
1. **Introduction Slide**
    
   - Title of the research project.
   - Student’s name and affiliation.
   - Brief overview of the presentation content.
    
2. **Research Objectives**
    
   - Clear articulation of the two research objectives.
   - Explanation of their relevance to the e-commerce sector.
    
3. **Methodology**
    
   - Overview of data sources and data collection methods.
   - Explanation of data cleaning and analysis techniques used.
    
4. **Analysis and Findings**
    
   - Presentation of key findings with supporting visualizations (scatter plots, correlation heatmaps).
   - Interpretation of the relationship between website usability and conversion rates.
    
5. **Conclusions and Recommendations**
    
   - Summary of conclusions drawn from the analysis.
   - Actionable recommendations for the organization to improve website usability and customer satisfaction.
    
6. **Q&A Session**
    
   - Open the floor for audience questions.
   - Provide thoughtful and evidence-based responses.
    
**Delivery Skills**
    
- **Clarity and Confidence**: Presented information in a clear and confident manner, ensuring that each slide was explained thoroughly.
- **Engagement**: Maintained eye contact with the audience and interacted through questions to keep engagement high.
- **Pacing**: Balanced the timing of each section to cover all aspects within the allotted time without rushing.
    
**Use of Visual Aids**
    
- **Quality Slides**: Slides were professionally designed with consistent formatting and high-quality graphics.
- **Effective Visualizations**: Incorporated scatter plots and heatmaps to visually represent the correlation between usability and conversion rates, enhancing audience understanding.
    
**Handling Questions and Feedback**
    
- **Responsive Answers**: Answered questions accurately, demonstrating a deep understanding of the research topic.
- **Openness to Feedback**: Receptive to feedback and suggestions, acknowledging valid points and considering them for future research improvements.
    
---
    
## Overall Assessment
    
- **Observe** the student's capabilities across all tasks for evidence of competence.
- **Provide Feedback**: Offer constructive feedback on strengths and areas for improvement.
- **Assessment Decision**:
    
  - **Satisfactory (S)**: The student has met all the requirements across the tasks.
  - **Not Yet Satisfactory (NYS)**: The student needs to address gaps as per feedback.
    
---
    
## Assessor Sign-off
    
- **Assessor Name**: _______________________  
- **Signature**: ___________________________  
- **Date**: _______________________________  
    
---