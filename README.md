# Customer Shopping Behavior Analysis
## Project Overview

This project focuses on analyzing customer shopping behavior using Data Analytics techniques. The analysis helps identify customer purchasing patterns, shopping preferences, frequency of purchases, discount usage, and product category trends. The project combines Python-based data analysis, SQL database integration, and Power BI dashboard visualization to generate business insights from customer shopping data.

The project includes:
* Data preprocessing and cleaning using Python
* Exploratory Data Analysis (EDA)
* Customer segmentation and behavioral analysis
* SQL database connectivity
* Interactive Power BI dashboard
* Data visualization and reporting
---

# Project Structure
```bash
customer behavior Project/
│
├── customer_behavior_dashboard.pbix
├── Customer_Behavior_Data_Analysis.pptx
├── customer_shopping_behavior.csv
├── Customer_Shopping_Behavior_Analysis.ipynb
└── customersqlfile.sql
```
# Technologies Used
## Programming & Analysis

* Python
* Jupyter Notebook
* Pandas
* SQLAlchemy
* Psycopg2
* PyMySQL
* PyODBC

## Databases
* PostgreSQL
* MySQL
* Microsoft SQL Server

## Visualization
* Power BI
---

# Dataset Information
The dataset used in this project contains customer shopping behavior details such as:
* Customer Age
* Gender
* Product Category
* Purchase Amount
* Purchase Frequency
* Review Ratings
* Discounts Applied
* Subscription Status
* Shipping Type
* Payment Method
* Seasonal Purchases
* Item Purchased

Dataset File:
customer_shopping_behavior.csv
---

# Objectives of the Project
* Analyze customer purchasing behavior
* Understand shopping frequency trends
* Identify high-performing product categories
* Study the impact of discounts and promotions
* Perform customer segmentation based on age groups
* Build visual dashboards for business insights
* Connect analytical workflow with SQL databases
---

# Data Analysis Workflow
## 1. Data Loading
The dataset is loaded into Python using Pandas.
```python
import pandas as pd

df = pd.read_csv('customer_shopping_behavior.csv')

## 2. Data Exploration
Initial dataset inspection is performed using:

* `df.head()`
* `df.info()`
* `df.describe()`

This helps understand:

* Data types
* Missing values
* Statistical summary
* Dataset structure

## 3. Handling Missing Values
Missing values in the `Review Rating` column are handled using median imputation grouped by category.

```python
df['Review Rating'] = df.groupby('Category')['Review Rating'] \
    .transform(lambda x: x.fillna(x.median()))
```
## 4. Data Cleaning & Transformation
The project performs several preprocessing operations:
* Renaming columns using snake_case
* Standardizing column names
* Creating derived features
* Removing unnecessary columns

Example:

```python
df.columns = df.columns.str.lower()
df.columns = df.columns.str.replace(' ','_')
```
## 5. Feature Engineering
### Age Group Segmentation
Customers are divided into different age groups:

* Young Adult
* Adult
* Middle-aged
* Senior

```python
labels = ['Young Adult', 'Adult', 'Middle-aged', 'Senior']
df['age_group'] = pd.qcut(df['age'], q=4, labels=labels)
```
### Purchase Frequency Mapping
Purchase frequency values are converted into numerical day values for analysis.

Example:

| Purchase Frequency | Days |
| ------------------ | ---- |
| Weekly             | 7    |
| Monthly            | 30   |
| Quarterly          | 90   |
| Annually           | 365  |
---
# SQL Database Integration
The project demonstrates database integration using multiple database systems.
## PostgreSQL Connection
The notebook includes PostgreSQL connectivity using SQLAlchemy and Psycopg2.
```python
from sqlalchemy import create_engine
```
## MySQL Connection
The project also supports MySQL database connectivity.
## Microsoft SQL Server Connection
MS SQL Server connectivity is implemented using PyODBC.
---
# Power BI Dashboard
The Power BI dashboard file:
```bash
customer_behavior_dashboard.pbix
```
The dashboard provides visual insights including:
* Customer purchase trends
* Category-wise analysis
* Discount usage patterns
* Payment method distribution
* Age group analysis
* Purchase frequency visualization
---
# Key Insights Generated
* Customer purchase behavior varies across age groups.
* Discounts and promotional offers influence purchasing activity.
* Certain product categories generate higher purchase frequency.
* Subscription users show different buying behavior compared to non-subscribers.
* Seasonal trends impact customer purchasing decisions.
---
# How to Run the Project
## Step 1: Install Required Libraries
```bash
pip install pandas sqlalchemy psycopg2-binary pymysql pyodbc matplotlib seaborn
```
## Step 2: Open Jupyter Notebook
```bash
jupyter notebook
```
Open:
```bash
Customer_Shopping_Behavior_Analysis.ipynb
```
## Step 3: Run Notebook Cells
Execute all notebook cells sequentially to:
* Load dataset
* Clean data
* Perform analysis
* Generate insights
* Connect databases
---
## Step 4: Open Power BI Dashboard
Open the following file in Power BI Desktop:

```bash
customer_behavior_dashboard.pbix
```
# Requirements
## Python Libraries
```text
pandas
sqlalchemy
psycopg2-binary
pymysql
pyodbc
```
# Future Improvements
* Add machine learning models for customer prediction
* Build recommendation systems
* Add real-time analytics
* Create automated ETL pipeline
* Integrate cloud databases
---
# Learning Outcomes
Through this project, the following concepts were implemented:
* Data preprocessing
* Data cleaning
* Exploratory Data Analysis
* Feature engineering
* SQL database integration
* Dashboard development
* Business intelligence reporting
---
# Author
**Irfan Pathan**

Data Analytics Project
---
# Conclusion
This project successfully analyzes customer shopping behavior using Data Analytics techniques. It demonstrates the complete analytics workflow from data preprocessing and transformation to visualization and database integration. The project helps generate meaningful business insights that can support better customer understanding and decision-making.
