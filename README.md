# 🏦 Credit Risk Prediction

A machine learning project to predict customer credit default risk using Home Credit data.  
This project focuses on building a data-driven solution to support better lending decisions by balancing risk and business growth.

---

## 📊 Problem Statement

Financial institutions face a key challenge:

- ❌ Too lenient → High number of default customers  
- ⚠️ Too strict → Loss of good customers  

👉 The goal is to build a model that can **accurately predict which customers are likely to default**, enabling smarter credit decisions.

---

## 📁 Dataset

- Source: Home Credit Default Risk (Kaggle)
- Train data: 307,511 customers | 122 features  
- Test data: 48,744 customers | 121 features  

### ⚖️ Target Imbalance
- 91.9% Non-default  
- 8.1% Default  

👉 Handled using **SMOTE** to improve model performance.

---

## 🛠️ Data Preprocessing

### 1. Data Cleaning
- Removed columns with >60% missing values  
- Imputed remaining missing values using median (numerical) and mode (categorical)

### 2. Feature Engineering
Created new features:
- `CREDIT_TO_INCOME`
- `ANNUITY_TO_INCOME`
- `AGE_YEARS`
- `EXT_SCORE_MEAN`
- `INCOME_PER_FAMILY`

### 3. Encoding
- Ordinal encoding for ordered categories  
- One-hot encoding for nominal features  

### 4. Standardization
- Applied **StandardScaler**

### 5. Handling Imbalanced Data
- Used **SMOTE** (8% → 30%)

---

## 🤖 Model Development

### Model Used: Random Forest

**Why Random Forest?**
- Stable performance  
- Handles non-linearity well  
- Provides feature importance  
- Less prone to overfitting  

### ⚙️ Hyperparameters
- `n_estimators = 300`
- `max_depth = 20`
- `min_samples_split = 5`
- `class_weight = 'balanced'`

---

## 📈 Model Performance

| Metric   | Score |
|----------|------|
| ROC-AUC  | 0.74 |
| KS Score | 0.36 |

👉 In credit scoring, **AUC > 0.7 is considered good**

---

## 🔍 Key Insights

### 1. External Credit Score is the Most Important Factor
- `EXT_SOURCE_3` → 17.8%  
- `EXT_SOURCE_2` → 16.8%  

👉 Lower external score = higher default risk  

---

### 2. Credit-to-Income Ratio is a Strong Risk Indicator
- Ratio > 5x → significantly higher risk  

👉 Useful as an early warning signal  

---

## 💼 Business Recommendations

### Based on External Score
- Integrate real-time credit bureau data  
- Use as early screening filter  
- Apply risk-based pricing  

### Based on Credit Ratio
- Limit loan amount (≤ 4x income)  
- Adjust loan tenor  
- Provide financial education  

---

## 🚀 Project Pipeline

Raw Data → Cleaning → Feature Engineering → Encoding → Scaling → SMOTE → Model → Evaluation

---

## 📂 Repository Structure

```
credit-risk-prediction/
│
├── assets/
├── notebooks/
├── outputs/
├── dataset_description.pdf
├── README.md
└── requirements.txt
```


---

## 📚 References

- Home Credit Default Risk  
- Scikit-learn Documentation  
- Credit Risk Modeling (Book)  

---

## ⭐ Closing

This project demonstrates how machine learning can be used to **reduce credit risk while maintaining business growth through data-driven decision-making**.
