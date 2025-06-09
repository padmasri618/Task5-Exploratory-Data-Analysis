# Titanic Dataset - Exploratory Data Analysis (EDA)

## Objective
To explore and analyze the Titanic dataset using Python libraries to uncover trends, patterns, and anomalies that influenced survival outcomes.

## Tools Used
- Python
- Pandas
- Seaborn
- Matplotlib
- Jupyter Notebook

---

##  Dataset Summary

- Source: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic/data)
- File: `train.csv`
- Rows: 891
- Columns: 12
- Key Columns: `Survived`, `Pclass`, `Sex`, `Age`, `Fare`, `Embarked`, etc.

---
#  Code
## 1. Import required libraries
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
## 2. load the dataset
df = pd.read_csv("C:/Users/padma/OneDrive/Documents/anaconda/train.csv")
#Dataset structure
print("=== .info() ===")
print(df.info())

#Summary statistics
print("\n=== .describe() ===")
print(df.describe())

#Value counts for categorical variables
print("\n=== .value_counts() ===")
print("Survived value counts:\n", df["Survived"].value_counts())
print("Pclass value counts:\n", df["Pclass"].value_counts())
print("Sex value counts:\n", df["Sex"].value_counts())

## 3. Initial data exploration
print("Shape of the dataset:", df.shape)
print("\nData Types and Nulls:\n", df.info())
print("\nSummary statistics:\n", df.describe())

## 4. Check for missing values
print("\nMissing values per column:\n", df.isnull().sum())

## 5. Value counts for categorical variables
print("\nSurvived value counts:\n", df["Survived"].value_counts())
print("\nPclass value counts:\n", df["Pclass"].value_counts())
print("\nSex value counts:\n", df["Sex"].value_counts())

## 6. Histogram: Age Distribution
plt.figure()
df["Age"].hist(bins=30, edgecolor="black")
plt.title("Age Distribution")
plt.xlabel("Age")
plt.ylabel("Count")
plt.show()

## 7. Countplot: Survival Count
plt.figure()
sns.countplot(x="Survived", data=df)
plt.title("Survival Count")
plt.xlabel("Survived (0 = No, 1 = Yes)")
plt.ylabel("Count")
plt.show()

## 8. Boxplot: Age vs Pclass
plt.figure()
sns.boxplot(x="Pclass", y="Age", data=df)
plt.title("Age Distribution by Passenger Class")
plt.show()

## 9. Barplot: Survival Rate by Class
plt.figure()
sns.barplot(x="Pclass", y="Survived", data=df)
plt.title("Survival Rate by Passenger Class")
plt.show()


## 10. Barplot: Survival Rate by Sex
plt.figure()
sns.barplot(x="Sex", y="Survived", data=df)
plt.title("Survival Rate by Sex")
plt.show()

## 11. Barplot: Embarked vs Survival
plt.figure()
sns.barplot(x="Embarked", y="Survived", data=df)
plt.title("Survival Rate by Port of Embarkation")
plt.show()

## 12. Heatmap: Correlation
plt.figure(figsize=(10, 8))
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap="coolwarm")
plt.title("Feature Correlation Heatmap")
plt.show()

## 13. Pairplot: Survival with numerical features
sns.pairplot(df[["Survived", "Pclass", "Age", "Fare"]].dropna(), hue="Survived")
plt.suptitle("Pairplot of Key Features by Survival", y=1.02)
plt.show()

## 14. Final Summary
print("🔍 Final Observations:")
print("- Female passengers had higher survival rates.")
print("- Passengers in higher classes (1st class) had better survival chances.")
print("- Younger passengers were more likely to survive.")
print("- Fare is positively correlated with survival.")
print("- Missing values exist in 'Age' and 'Cabin'.")


---

##  Visualizations, Content, Insights & Anomalies

### 1. Age Distribution (Histogram)
- **Content**: Shows how ages are distributed.
- **Insight**: Majority of passengers are aged between 20–40.
- **Anomaly**: Few infants (<1 year) and very old (>70).
![Screenshot 2025-06-09 121348](https://github.com/user-attachments/assets/b60e7c98-02f4-41f8-acd3-9e7aebaeb9f8)


---

### 2. Survival Count (Countplot)
- **Content**: Compares number of survivors vs non-survivors.
- **Insight**: About 38% survived, 62% didn't.
- ![Screenshot 2025-06-09 121401](https://github.com/user-attachments/assets/68395c97-029f-4150-a9c0-430511bf7a01)


---

### 3. Age vs Pclass (Boxplot)
- **Content**: Age spread in each class.
- **Insight**: 1st class passengers are generally older.
- **Anomaly**: Young kids found across all classes.
![Screenshot 2025-06-09 121412](https://github.com/user-attachments/assets/94a2248e-2a2e-4e3a-a98a-01eef10b8d5d)

---

### 4. Survival Rate by Class (Barplot)
- **Insight**: Higher class passengers had significantly better survival chances.
![Screenshot 2025-06-09 121421](https://github.com/user-attachments/assets/70f768f0-65a0-4f7b-b5bc-95f19390c210)


---

### 5. Survival Rate by Sex (Barplot)
- **Insight**: Females were far more likely to survive.
- **Anomaly**: Male survival rate drops across all classes.
![Screenshot 2025-06-09 121431](https://github.com/user-attachments/assets/05ea224f-1f34-4dcf-81fb-d1487eaa6a68)

---

### 6. Survival Rate by Embarked Port (Barplot)
- **Insight**: Passengers from Cherbourg (C) had the highest survival rate.
![Screenshot 2025-06-09 121445](https://github.com/user-attachments/assets/c7b383af-7e51-4460-8c06-9dba3889bbf4)

---

### 7. Correlation Heatmap
- **Content**: Shows how features correlate with each other.
- **Insight**: Fare is positively correlated with survival; Pclass negatively.
![Screenshot 2025-06-09 121514](https://github.com/user-attachments/assets/b4ed0b39-9487-4476-b9cf-32f700e0c59d)

---

### 8. Pairplot: Survival vs Numerical Features
- **Content**: Plots pairwise relationships of numerical features.
- **Insight**: High Fare and lower class indicate higher survival.
![Screenshot 2025-06-09 121722](https://github.com/user-attachments/assets/d1105585-8e2d-4165-baf6-ff8240a50682)
![Screenshot 2025-06-09 121711](https://github.com/user-attachments/assets/d9fa803f-238d-4064-9581-e55edf831757)
![Screenshot 2025-06-09 121651](https://github.com/user-attachments/assets/b2e57732-1d64-43ef-80bf-39333b4ec03c)

---

## Key Insights
- Women and children were prioritized in rescue.
- Passengers in 1st class had better facilities and escape chances.
- High fare and boarding from Cherbourg are associated with survival.
- Missing data in `Age`, `Cabin` should be handled before modeling.



