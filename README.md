# 📊 Customer Churn Analysis (TCA) — Python | EDA

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Computation-blueviolet?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-lightgrey?logo=plotly&logoColor=black)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-green?logo=python&logoColor=white)

## 📌 Project Overview
**Customer Churn Analysis (TCA)** is a comprehensive data analytics project focused on identifying the root causes of customer attrition in the telecommunications industry. This project utilizes Python to perform deep-dive **Exploratory Data Analysis (EDA)**, helping businesses transition from reactive to proactive retention strategies.

## 🏢 Business Problem
In high-competition markets, the cost of acquiring a new customer is significantly higher than retaining an existing one. Telecommunication companies need to identify high-risk customers based on their service usage, contract types, and payment behaviors to minimize revenue loss.

## 🎯 Business Objectives
* **Identify key drivers** of customer churn (attrition).
* **Analyze service impact:** Compare Fiber optic vs. DSL loyalty.
* **Study Tenure Correlation:** How contract terms influence customer stay.
* **Evaluate Payment Methods:** Identify friction in the billing process.
* **Actionable Insights:** Provide data-driven recommendations for marketing teams.

---

## 📂 Dataset Information
* **File Name:** `Customer Churn.csv`
* **Total Records:** 7,043
* **Total Attributes:** 21
* **Target Variable:** `Churn` (Yes/No)
* **Source:** Telco Customer Churn Data

### 🧾 Dataset Schema (Key Columns)
| Column | Description |
| :--- | :--- |
| **customerID** | Unique identifier for each customer |
| **tenure** | Number of months the customer has stayed |
| **InternetService** | Provider (DSL, Fiber optic, No) |
| **Contract** | Term (Month-to-month, One year, Two year) |
| **MonthlyCharges** | Amount charged monthly |
| **Churn** | Whether the customer left or not (Target) |

---

## 🛠️ Data Pre-processing & Analysis

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

# Handling missing values in TotalCharges
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')
df['TotalCharges'].fillna(0, inplace=True)

# Mapping SeniorCitizen for better visualization
df['SeniorCitizen'] = df['SeniorCitizen'].map({0: 'No', 1: 'Yes'})

# Visualizing Churn by Payment Method
plt.figure(figsize=(10, 6))
ax = sns.countplot(x="PaymentMethod", data=df, hue="Churn", palette="viridis")
for container in ax.containers:
    ax.bar_label(container)
plt.title("Churned Customers by Payment Method")
plt.xticks(rotation=45)
plt.show()


💡 Key Insights

Critical Risk Factor: Customers using Electronic Checks exhibit the highest churn rates, suggesting friction in this payment process.

Service Vulnerability: Fiber optic users churn more frequently than DSL users, indicating potential issues with pricing or stability.

Contract Loyalty: Month-to-month contracts are the strongest predictors of churn; customers on two-year contracts show the highest loyalty.

Financial Thresholds: High monthly charges combined with short tenure are primary indicators of early-stage attrition.

📁 Requirements

To run this project locally, ensure you have the following dependencies installed:

pandas>=1.3.0
numpy>=1.20.0
matplotlib>=3.4.0
seaborn>=0.11.0
jupyter>=1.0.0


👨‍💻 Author

Rakesh Kumar Mistri Aspiring Data Analyst

GitHub: rakeshkumarmistri010413-collab

LinkedIn: https://www.linkedin.com/in/rakesh-kumar-mistri-07ab15334/

Email: rakeshkumarmistri010413@gmail.com
