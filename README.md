# 📊 Customer Churn Analysis — Data Science Project

## 🧠 Project Overview
This project focuses on analyzing **Customer Churn** in a telecom company using **Python** and **data visualization techniques**.  
The main goal is to identify key factors influencing customer churn and visualize customer behavior patterns using Seaborn and Matplotlib.

---

## 📁 Dataset Information
The dataset used is **Customer Churn.csv**, containing the following features:

| Column | Description |
|:--------|:-------------|
| customerID | Unique identifier for each customer |
| gender | Male or Female |
| SeniorCitizen | Whether the customer is a senior citizen (1 = Yes, 0 = No) |
| Partner | Whether the customer has a partner |
| Dependents | Whether the customer has dependents |
| tenure | Number of months the customer has stayed |
| PhoneService | Whether the customer has a phone service |
| MultipleLines | Whether the customer has multiple lines |
| InternetService | Type of internet service (DSL, Fiber optic, None) |
| OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport | Availability of extra services |
| StreamingTV, StreamingMovies | Whether the customer streams TV/movies |
| Contract | Customer’s contract type (Month-to-month, One year, Two year) |
| PaperlessBilling | Whether billing is paperless |
| PaymentMethod | Payment type (Electronic check, Credit card, etc.) |
| MonthlyCharges | Monthly payment amount |
| TotalCharges | Total amount charged to the customer |
| Churn | Target variable (Yes = Customer left, No = Stayed) |

---

## 🧹 Data Preprocessing

```python
# Importing Libraries
import pandas as pd
import numpy as np

# Reading Dataset
df = pd.read_csv("Customer Churn.csv")

# Handling missing or blank TotalCharges
df["TotalCharges"] = df["TotalCharges"].replace(" ", "0").astype("float")

# Converting 'SeniorCitizen' from numeric to categorical
def conv(value):
    return "yes" if value == 1 else "no"
df['SeniorCitizen'] = df["SeniorCitizen"].apply(conv)

# Checking data info
df.info()

# Checking for missing values
df.isnull().sum()
