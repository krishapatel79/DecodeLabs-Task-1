# Titanic Dataset — Project 1
## Data Cleaning & Preparation

---

# Project Overview

This project focuses on cleaning and preparing the Titanic dataset using Python and Pandas. The goal of the project is to improve data quality by handling missing values, removing duplicate rows, and correcting formatting inconsistencies.

The cleaned dataset becomes suitable for Exploratory Data Analysis (EDA) and Machine Learning applications.

---

# Dataset Information

- Dataset: Titanic Dataset
- Source: Kaggle
- File Format: CSV

The dataset contains passenger details such as:
- Passenger ID
- Name
- Age
- Gender
- Passenger Class
- Fare
- Embarkation Port
- Survival Status

---

# Objectives

The main objectives of this project are:

- Handle missing/null values
- Remove duplicate records
- Standardize text formatting
- Verify data quality
- Prepare dataset for analysis

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| Pandas | Data Cleaning & Manipulation |
| NumPy | Numerical Operations |
| Jupyter Notebook | Project Development |

---

# Libraries Used

```python
import pandas as pd
import numpy as np
```

---

# Data Cleaning Steps

## 1. Loading Dataset

```python
df = pd.read_csv("Titanic-Dataset.csv")
```

---

## 2. Initial Inspection

```python
df.head()
df.info()
df.shape
```

---

## 3. Handling Missing Values

### Age Column

```python
df["Age"] = df["Age"].fillna(df["Age"].median())
```

### Embarked Column

```python
df["Embarked"] = df["Embarked"].fillna(df["Embarked"].mode()[0])
```

### Cabin Column

```python
df = df.drop("Cabin", axis=1)
```

---

## 4. Duplicate Removal

```python
df = df.drop_duplicates()
```

---

## 5. Text Formatting

### Removing Extra Spaces

```python
df["Name"] = df["Name"].str.strip()
```

### Standardizing Text

```python
df["Sex"] = df["Sex"].str.lower()
```

---

## 6. Final Verification

```python
df.isnull().sum()
df.duplicated().sum()
```

---

# Output

```python
df.to_csv("cleaned_titanic.csv", index=False)
```

---

# Project Structure

```text
Titanic_Project1/
│
├── Titanic_Project1.ipynb
├── cleaned_titanic.csv
├── README.md
└── Titanic-Dataset.csv
```

---

# Key Learnings

- Data preprocessing
- Missing value handling
- Duplicate removal
- Text formatting
- Data preparation workflow
- Pandas operations

---

# Conclusion

The Titanic dataset was successfully cleaned and prepared for future analysis. Missing values were handled appropriately, duplicate rows were removed, and formatting issues were corrected.

The final cleaned dataset is now ready for Exploratory Data Analysis (EDA) and Machine Learning tasks.

---

# Future Work

The cleaned dataset can be further used for:

- Exploratory Data Analysis (EDA)
- Data Visualization
- Machine Learning Models
- Survival Prediction
- Statistical Analysis

---

# Author

Name: Your Name

Batch: 2026

Domain: Data Analytics

---

# Thank You

DecodeLabs — Industrial Training Program