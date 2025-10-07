# Telecom
📞 Telecom Customer Churn Project
👨‍💻 Author: Chirag Jangid
🗂️ Dataset: Telco-Customer-Churn.csv
📝 Project Overview

This project focuses on understanding the structure and initial exploration of a telecom customer dataset before performing advanced data analysis or prediction tasks.
It involves loading, cleaning, and performing exploratory checks on the dataset to gain early insights into the data quality, completeness, and customer demographics.

The main goal is to get familiar with the dataset and identify potential issues or patterns in the data that will later help in building predictive churn models.

🎯 Objectives

Load and inspect the Telco Customer Churn dataset.

Understand data structure: rows, columns, and types.

Check for missing or duplicate values.

Perform basic descriptive analysis on gender, partners, dependents, and senior citizens.

Verify data consistency before moving to visualization or modeling.

🧠 Key Steps and Explanations
1. Importing Required Libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns


Used core Python data science libraries for data handling and visualization.

2. Loading the Dataset
telecom = pd.read_csv("Telco-Customer-Churn.csv")


The dataset is loaded into a pandas DataFrame for analysis.

3. Basic Exploration

telecom.head() → Shows first 5 rows (used to understand column meanings).

telecom.tail() → Displays last 5 rows to check the data's ending structure.

telecom.shape → Reveals dataset size: 7043 rows × 21 columns.

telecom.info() → Shows data types and non-null counts.

telecom.describe() → Summary statistics of numerical features.

✅ Correct Points:

Proper use of pandas functions for exploration.

Verified dataset dimensions and column names early.

⚠️ Improvement:

Could include telecom.nunique() to find unique values in categorical columns.

Data visualization wasn’t fully implemented yet (just mentioned).

4. Checking Column-Wise Details

Used several commands like:

telecom['customerID'].reset_index()
telecom['gender'].reset_index()


These display column values in detail.

⚠️ Mistake: .reset_index() doesn’t help for inspecting columns — better to use:

telecom['gender'].value_counts()


to get actual counts per category.

5. Filtering Based on Conditions

Without Partner:

telecom.loc[telecom['Partner'] == 'No']


Found 3641 customers without partners.

Gender Distribution:

Female: 3488

Male: 3555

Senior Citizens (Age 60+):

1142 customers.

Dependents:

Yes: 2110

No: 4933

✅ Correct Point: Used logical conditions effectively.
⚠️ Improvement: Use .value_counts() or .groupby() for simpler summaries instead of multiple .loc[].

6. Missing & Duplicate Data Check
telecom.isnull().sum()
telecom.duplicated().sum()


No missing values found ✅

Duplicate check incorrectly implemented ❌
(The code used telecom.count().duplicated() which is wrong — that checks column counts, not rows.)

✅ Correct Command:

telecom.duplicated().sum()

🔍 Key Findings
Metric	Result
Total Customers	7043
Female Customers	3488
Male Customers	3555
Without Partner	3641
Senior Citizens (60+)	1142
Dependents (Yes)	2110
Dependents (No)	4933
Missing Values	0
Duplicate Rows	0
🧩 Mistakes & Corrections Summary
Mistake	Correction	Explanation
Used .count().duplicated() to find duplicates	Use telecom.duplicated().sum()	.duplicated() checks duplicate rows correctly
Used .reset_index() to view column data	Use .value_counts()	Easier way to count occurrences
No visualization yet	Add sns.countplot() or plt.bar()	To make the report more insightful
📊 Next Steps (Future Work)

Visualize categorical data (Gender, Partner, Dependents, etc.).

Analyze churn distribution (Churn column).

Handle categorical encoding and prepare for model training.

Build predictive models using Logistic Regression or Decision Trees.

Create a dashboard for interactive churn insights.

🧾 Conclusion

This Telecom project serves as a solid data understanding and cleaning phase before moving into modeling.
It successfully identifies data structure, verifies completeness, and provides early demographic insights.

The corrected version improves accuracy and readability, setting a strong foundation for advanced data analysis and churn prediction.

🗂️ Repository Structure (Recommended)
📁 Telecom-Churn-Project/
│
├── 📄 Telecom Project.ipynb         # Main notebook
├── 📄 Telco-Customer-Churn.csv      # Dataset file
├── 📄 README.md                     # Project description (this file)
├── 📊 images/                       # Optional graphs and visualizations
└── 📁 models/                       # Future predictive models
