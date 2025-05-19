---
footer: "![height:50px](footer.png)"
marp: true
theme: nmt-theme
title: "Session 11: Data Collection and Storage"
paginate: true
---

<!-- _class: lead -->
# BSBINS401 - Analyse and Present Research Information

## Session 11: Data Collection and Storage

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

By the end of this session, you will be able to:

- **Understand methods for accessing and extracting data.**
- **Organize data effectively for analysis.**
- **Implement secure storage practices for research data.**

---

## Session Overview

- **Topics Covered**:
  - Methods for accessing and extracting data
  - Organizing data for analysis
  - Secure storage practices

- **Activities**:
  - Hands-on data collection
  - Setting up data storage solutions

---

## 1. Methods for Accessing and Extracting Data

### **Data Sources**

- **Public Repositories**:
  - [Kaggle](https://www.kaggle.com/datasets)
  - [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)

- **Organizational Databases**:
  - Internal SQL databases
  - NoSQL databases like MongoDB

- **APIs**:
  - [Twitter API](https://developer.twitter.com/en/docs)
  - [Google APIs](https://developers.google.com/apis-explorer)

### **Data Extraction Techniques**

- **Web Scraping**:
  - Tools: BeautifulSoup, Scrapy
  - Use Cases: Extracting data from websites

- **Database Queries**:
  - Language: SQL
  - Operations: SELECT, JOIN, WHERE

- **Using APIs with Python**:
  - Libraries: `requests`, `http.client`
  - Example:
    ```python
    import requests

    response = requests.get('https://api.example.com/data')
    data = response.json()
    ```

---

## 2. Organizing Data for Analysis

### **Data Structures**

- **Dataframes**:
  - Library: Pandas
  - Example:
    ```python
    import pandas as pd

    df = pd.read_csv('data.csv')
    ```

- **Arrays**:
  - Library: NumPy
  - Example:
    ```python
    import numpy as np

    arr = np.array([1, 2, 3, 4, 5])
    ```

- **Databases**:
  - SQL (e.g., MySQL, PostgreSQL)
  - NoSQL (e.g., MongoDB)

### **Best Practices**

- **Consistent Naming Conventions**:
  - Use snake_case for variable names
  - Clear and descriptive column names

- **Logical Structuring**:
  - Normalize data to reduce redundancy
  - Use appropriate indexing for faster queries

- **Documentation**:
  - Maintain a data dictionary
  - Comment your code for clarity

### **Tools**

- **Pandas** for data manipulation
- **Jupyter Notebooks** for exploratory analysis
- **Version Control** (e.g., Git) for tracking changes

---

## 3. Secure Storage Practices

### **Data Security Principles**

- **Confidentiality**: Ensure that only authorized personnel can access the data.
- **Integrity**: Protect data from unauthorized alterations.
- **Availability**: Ensure that data is accessible to authorized users when needed.

### **Storage Solutions**

- **Cloud Storage**:
  - Examples: [Google Drive](https://drive.google.com/), [AWS S3](https://aws.amazon.com/s3/), [Azure Blob Storage](https://azure.microsoft.com/en-us/services/storage/blobs/)
  
- **Institutional Repositories**:
  - University-provided storage solutions
  
- **Encrypted Local Storage**:
  - Use encryption tools like VeraCrypt to secure data on local machines

### **Security Measures**

- **Encryption**:
  - Encrypt data at rest and in transit
  - Tools: AES-256, SSL/TLS for data transmission

- **Access Controls**:
  - Implement role-based access control (RBAC)
  - Use strong authentication methods (e.g., multi-factor authentication)

- **Regular Backups**:
  - Schedule automated backups
  - Use redundant storage locations to prevent data loss

---

## Activities

### **Lab: Setting Up Data Storage Solutions**

1. **Choose a Storage Platform**
   - Options: Google Drive, AWS S3, Azure Blob Storage

2. **Configure Access Controls**
   - Set up user permissions and access levels

3. **Upload and Secure Data**
   - Encrypt data files before uploading

4. **Implement Backup Strategy**
   - Schedule regular backups and verify their integrity

---

## Reading Resources

- **Data Collection Techniques**
  - [Guide to Data Collection](https://www.example.com/data-collection-guide)

- **Organizing Data for Analysis**
  - *Python for Data Analysis* by Wes McKinney, Chapter 5

- **Secure Data Storage**
  - [Data Security Best Practices](https://www.example.com/data-security)

---

## Lab Resources

- **Tutorials**:
  - [Using APIs with Python](https://www.kaggle.com/learn/api)
  - [Database Queries with SQL](https://www.kaggle.com/learn/pandas)

- **Tools**:
  - [Pandas Documentation](https://pandas.pydata.org/docs/)
  - [AWS S3 Getting Started Guide](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html)

---

## Next Steps

- **Apply** the data access and extraction methods to your project dataset.
- **Organize** your data following the best practices discussed.
- **Implement** secure storage solutions to safeguard your research data.
- **Prepare** for the next session on advanced data analysis techniques.

---

## Questions?

- Contact: jordan.hill@nmtafe.wa.edu.au  
- Office Hours: Mon–Fri, 9 AM – 5 PM

![width:10%](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Question_mark.svg/240px-Question_mark.svg.png)

