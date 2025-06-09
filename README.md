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
- Key Columns: `Survived`, `Pclass`, `Sex`, `Age`, `Fare`, `Embarked`, etc
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



