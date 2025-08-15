# Supervised Learning Models for Classification & Regression: Predicting Import-Export Dynamics

## Project Contents
- Project Information  
- Description of Data  
- Data Sampling  
- Project Objectives | Problem Statements  
- Analysis of Data  
- Observations | Findings  
- Managerial Insights | Recommendations   

---

## Description of Data

The dataset records international trade transactions, covering both **imports** and **exports**, with comprehensive details on products, countries, shipping methods, and more.

**Data Format:** CSV  

**Data Type:** Panel Data (longitudinal), recording multiple entities (countries) over time.

**Columns:**
- **Identifiers:** `Transaction_ID`, `Invoice_Number`
- **Categorical:** `Country`, `Product`, `Import_Export`, `Category`, `Port`, `Customer`, `Supplier`, `Customs_Code`, `Payment_Terms`, `Shipping_Method`
- **Numerical:**  
  - Integer: `Quantity`, `Customs_Code`, `Invoice_Number`  
  - Float: `Value`, `Weight`  
- **Datetime:** `Date`
- **Derived:** `Total_Value` (Quantity × Value)

---

## Data Sampling
- **Original Dataset Size:** 15,000 records  
- **Sample Used (Unique sample):** 5,001 records  
- **Reason:** Manageable size for exploration while retaining variability.  

---

## Project Objectives
1. Classify the dataset into **segments/clusters/classes** using supervised learning algorithms.
2. Identify **important/contributing variables** and their **thresholds** for classification.
3. Determine the **best classification model** based on performance metrics.

---

## Data Analysis & Preprocessing

### 1 Data Preprocessing
- No missing values in dataset
- **Ordinal Encoding** for:
  - `Payment_Terms`: COD → 0, Net 30 → 1, Net 60 → 2, Prepaid → 3  
  - `Shipping_Method`: Air → 0, Land → 1, Sea → 2  
  - `Import/Export`: Export → 0, Import → 1  
- **Scaling:** Min-Max Scaling for all numerical variables (range: 0–1).  

### 2 Exploratory Data Analysis
- **Numerical Variables:** Symmetric distributions for most variables except `Total_Value` (slight positive skew).
- **Correlation Insights:**
  - `Quantity` & `Value` strongly correlate with `Total_Value` (~0.65 each).
  - `Weight` has negligible correlation with other features.
  - Minimal multicollinearity observed.
- **Categorical Variables:** Highly diverse distributions, especially for `Country`, `Product`, and `Port`.
- **Inferential Stats:** Only `Shipping_Method` showed a significant association with `Import/Export`.

---

## Machine Learning Models

### Models Tested
- **Regression-Based:** Logistic Regression (LR)  
- **Tree-Based:** Decision Tree (DT), Random Forest (RF)  
- **Distance-Based:** K-Nearest Neighbors (KNN)  
- **Margin-Based:** Support Vector Machine (SVM)  
- **Others:** Naive Bayes, SGD, Bagging, Boosting  

### Performance Summary (Top Models)
| Model            | Avg. CV Score | Key Features Identified |
|------------------|--------------|-------------------------|
| **Random Forest** | **0.5221**   | Invoice Number, Weight, Value, Quantity, Total_Value |
| **Decision Tree** | 0.5065       | Invoice Number, Weight, Value, Total_Value, Quantity, Payment_Terms |
| Logistic Regression | 0.5005    | None |
| KNN               | 0.5023       | None |
| SVM               | 0.4995       | None |

---

## Observations & Findings

### Key Takeaways
- **Best Overall Models:** Random Forest & Decision Tree.  
- **Most Interpretable:** Decision Tree (clear feature importance).  
- **Stable Performance:** Random Forest across folds.  
- **Top Predictors:** `Invoice_Number`, `Weight`, `Value`, `Quantity`, `Total_Value`.

### Dropped Features
- Low relevance: `Country`, `Product`, `Category`, `Port`, `Customer`, `Supplier`, `Customs_Code`.

---

## Managerial Insights & Recommendations

### Data Preparation
- Use **One-Hot Encoding** for nominal categorical variables in the future.
- Continue **Min-Max Scaling** for numerical features.
- Outlier handling (IQR/Z-score) and log transformation for skewed variables (e.g., `Total_Value`).

### Model Recommendations
- **Decision Tree:**  
  - Use for interpretability.  
  - Focus on thresholds > 0.7 for high-importance features like `Invoice_Number` & `Weight`.
- **Random Forest:**  
  - Use for accuracy and stability.  
  - Best suited when interpretability is secondary.
- **Logistic Regression & SVM:**  
  - Less effective for this dataset.
- **KNN:**  
  - Avoid for large/high-dimensional datasets.

---

## Conclusion
This project demonstrates how supervised learning models can classify import/export transactions and identify key influencing factors. **Random Forest** emerged as the top-performing model, with **Decision Tree** offering the highest interpretability for managerial decision-making.

---

## Resources
- **Code & Analysis:** Python Notebooks (Pandas, Scikit-learn, Lazy Predict)
- **Visualizations:** Bar Charts, Heatmaps, Histograms, Correlation Matrices

---

## Tools & Libraries
- Python (Pandas, NumPy, Scikit-learn)
- Lazy Predict (Model Benchmarking)
- Matplotlib / Seaborn (Visualization)

---
**Author:** Shefali Dhingra
```
