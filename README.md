# ConnectTel Customer Churn Prediction

> End-to-end customer churn prediction for ConnectTel Telecom — EDA, feature engineering, and model comparison (Logistic Regression, Random Forest, XGBoost) with SHAP explainability and actionable retention strategies. Best model: Random Forest at AUC-ROC 0.8423, Recall 80%.

---

## 📌 Problem Statement

Customer churn is one of the costliest challenges in telecoms. Acquiring a new customer costs **5–25× more** than retaining one, yet the industry sees **15–25% annual churn**. This project builds a machine learning pipeline that identifies at-risk customers early — giving the business time to act before revenue is lost.

---

## 📂 Project Structure

```
ConnectTel_Customer_Churn_Project/
├── Source_Code/
│   ├── churn_prediction.ipynb       ← Main analysis notebook
│   └── data/
│       └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── Presentation/
│   └── ConnectTel_Presentation.pptx
├── Report/
│   └── ConnectTel_Churn_Report.pdf
├── LINKS.txt
└── README.md
```

---

## 📊 Dataset

| Property | Detail |
|---|---|
| Source | IBM Telco Customer Churn (Kaggle) |
| Customers | 7,043 rows |
| Raw Features | 21 |
| Engineered Features | 32 |
| Target | `Churn` — Yes / No (26.5% positive class) |

**Feature Groups:** Demographics · Account info (tenure, contract, charges) · Services (internet, phone, add-ons) · Engineered (`TotalChargesPerTenure`, `ServiceCount`)

---

## ⚙️ Notebook Workflow

1. **Data Loading & Inspection** — shape, dtypes, missing values, class balance  
2. **EDA** — churn rates by contract type, internet service, tenure, and charges  
3. **Preprocessing** — encoding, scaling, 80/20 stratified train/test split  
4. **Modelling** — Logistic Regression, Random Forest, XGBoost (GridSearchCV tuned)  
5. **Evaluation** — AUC-ROC, Recall, Precision, F1, Confusion Matrix  
6. **SHAP Explainability** — global beeswarm + individual waterfall plots  
7. **Retention Recommendations** — business strategies tied to model insights  

---

## 🏆 Results

| Model | AUC-ROC | Recall | Precision | F1 |
|---|---|---|---|---|
| Logistic Regression | 0.8417 | 78% | 50% | 0.61 |
| **Random Forest** ✅ | **0.8423** | **80%** | **53%** | **0.64** |
| XGBoost (Tuned) | 0.8423 | 80% | 51% | 0.62 |

**Random Forest** is the winning model — highest F1 and best Recall for catching at-risk customers.

---

## 🔍 Key EDA Findings

- **Contract type** is the #1 churn driver — Month-to-Month customers churn at ~42% vs ~3% for Two-Year contracts
- **Fiber Optic** internet users churn at ~42%, the highest of any service type
- **~50% of churners** leave within their first 12 months — early onboarding is critical

---

## 💡 SHAP Top Features (Random Forest)

| Rank | Feature | Direction |
|---|---|---|
| 1 | Contract: Month-to-Month | ⬆ Increases risk |
| 2 | tenure | ⬇ Longer = safer |
| 3 | InternetService: Fiber Optic | ⬆ Increases risk |
| 4 | TotalChargesPerTenure | ⬆ Higher cost = higher risk |
| 5 | OnlineSecurity: No | ⬆ Increases risk |

---

## 📋 Retention Recommendations

1. **Contract Migration Campaign** — offer discounted annual contracts to Month-to-Month subscribers with tenure < 12 months and churn probability > 0.60
2. **Fiber Optic Satisfaction Programme** — proactive surveys + bundled add-ons to reduce Fiber churn from ~42% to ~28%
3. **First-Year Onboarding & Nurture** — automated retention touchpoints at 3 and 6 months to reduce early drop-off

---

## 🚀 Getting Started

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap jupyter

# Launch the notebook
jupyter notebook Source_Code/churn_prediction.ipynb
```

---

## 🛠️ Tech Stack

`Python` · `Pandas` · `NumPy` · `Scikit-learn` · `XGBoost` · `SHAP` · `Matplotlib` · `Seaborn` · `Jupyter Notebook`

---

*Dataset: IBM Telco Customer Churn — publicly available via Kaggle.*
