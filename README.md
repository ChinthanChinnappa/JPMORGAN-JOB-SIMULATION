# Credit Risk Modeling & Pricing System

### Probability of Default (PD), Expected Loss (EL) & FICO Quantization

This project implements an **end-to-end credit risk modeling pipeline** used in financial systems to evaluate borrower risk and support lending decisions.

It combines **machine learning, statistical modeling, and credit scoring techniques** to transform raw borrower data into actionable risk metrics.

---

# 🚀 Project Overview

The system performs three core functions:

* Predicts **Probability of Default (PD)** using ML models
* Estimates **Expected Loss (EL)** for financial exposure
* Optimizes **FICO score segmentation** into risk-based rating buckets

This reflects how banks and fintech platforms build **risk-adjusted lending and pricing strategies**.

---

# 🏗 Project Architecture

```
credit-risk-model/
│
├── loan_pd_expected_loss_model.py
├── fico_rating_quantization.py
├── customer_loan_data.csv
└── README.md
```

---

# 📊 Key Features

## 1. Probability of Default (PD) Modeling

Implemented using:

* Logistic Regression
* Random Forest

✔ Automatic model selection based on **ROC-AUC score**
✔ Outputs calibrated probability of default for each borrower

---

## 2. Expected Loss (EL) Estimation

Implements the standard financial risk formula:

```
Expected Loss = PD × Loss Given Default × Exposure
```

✔ Estimates potential loss for each borrower
✔ Incorporates exposure and recovery assumptions

Example:

```
Predicted PD: 0.083
Expected Loss: $7470
```

---

## 3. FICO Rating Quantization

Transforms continuous credit scores into discrete risk buckets using:

### • Equal Frequency Bucketing

Ensures equal distribution of borrowers per bucket

### • K-Means Clustering

Minimizes intra-group variance (MSE-based segmentation)

### • Log-Likelihood Optimization (Advanced)

Uses dynamic programming to maximize likelihood of default separation
✔ Inspired by techniques used in **banking risk frameworks (Basel)**

---

# 🛠 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Machine Learning
* Credit Risk Modeling

---

# ⚙️ Installation

```bash
git clone https://github.com/yourusername/credit-risk-model.git
cd credit-risk-model
pip install pandas numpy scikit-learn
```

---

# ▶️ Usage

## Train Model

```python
from loan_pd_expected_loss_model import LoanPDModel

model = LoanPDModel()
model.train("customer_loan_data.csv")
```

---

## Predict Risk

```python
borrower = {
    "income": 50000,
    "total_loans_outstanding": 20000,
    "credit_score": 650,
    "years_employed": 5
}

pd = model.predict_pd(borrower)
expected_loss = model.expected_loss(borrower, exposure=100000)
```

---

## Generate FICO Buckets

```python
from fico_rating_quantization import FICORatingQuantizer

quantizer = FICORatingQuantizer(n_buckets=5)
quantizer.fit_log_likelihood(fico_scores, defaults)

ratings = quantizer.transform(fico_scores)
```

---

# 📁 Dataset Format

Required fields:

```
income
total_loans_outstanding
credit_score
years_employed
default
fico_score
```

Where:

```
default = 1 → borrower defaulted  
default = 0 → borrower did not default  
```

---

# 🌍 Real-World Applications

* Credit scoring systems
* Loan approval engines
* Risk-adjusted pricing models
* Portfolio risk analysis
* Fintech lending platforms
* Banking risk & Basel-style modeling

---

# 🔮 Future Improvements

* Gradient Boosting (XGBoost / LightGBM)
* Feature engineering pipelines
* Model explainability (SHAP)
* Portfolio simulation models
* REST API deployment
* Real-time credit scoring

---

# 👤 Author

**Chinthan Chinnappa P T**


Computer Science Engineering Student

Interests:

* Data Science
* Quantitative Finance
* Risk Modeling
* Machine Learning Systems
