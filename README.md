# 🚨 Credit Card Fraud Detection

## 📌 Problem Statement
Financial institutions face huge losses due to credit card fraud. Fraudulent transactions are rare (≈0.17%), making detection extremely challenging.  
The goal of this project is to build a **robust, explainable, and business-relevant fraud detection system.**

---

## 📊 Dataset
- **Source:** [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)  
- **Records:** 284,807 transactions  
- **Frauds:** 492 (~0.17%)  
- **Features:** PCA-transformed transaction features + Amount + Time  
- **Target:** Fraud (1) / Legitimate (0)  

---

## ⚙️ Methods

### 1. Data Preprocessing
- Standardization of features  
- Train-test split  
- Severe class imbalance handling (**SMOTE oversampling**)  

### 2. Supervised Models (Baseline)
- Logistic Regression  
- Random Forest  
- XGBoost  

### 3. Anomaly Detection Models
- Isolation Forest  
- One-Class SVM  
- Local Outlier Factor  

### 4. Ensemble Approach
- Combined **Random Forest (SMOTE)** + **One-Class SVM** using a **rule-based boosting strategy**  
- Enhanced fraud probabilities for transactions flagged by anomaly detector  

### 5. Model Refinement
- Threshold tuning to **maximize recall** (catch as many frauds as possible)  
- Feature importance analysis for **global insights**  

---

## 📈 Results

| Model                | Recall | Precision | F1-score | ROC-AUC | PR-AUC |
|----------------------|--------|-----------|----------|---------|--------|
| Logistic Regression  | 0.92   | 0.06      | 0.11     | 0.97    | 0.08   |
| Random Forest (SMOTE)| 0.81   | 0.86      | 0.83     | 0.95    | 0.84   |
| XGBoost (SMOTE)      | 0.88   | 0.46      | 0.60     | 0.98    | 0.85   |
| One-Class SVM        | 0.72   | 0.25      | 0.37     | 0.89    | 0.20   |
| **Ensemble (Final)** | **0.86** | **0.79** | **0.82** | **0.95** | **0.85** |

✅ **Final Ensemble Model** balances recall and precision, making it the **most business-relevant choice.**

---

## 📊 Key Visualizations
- Fraud probability distribution (fraud vs non-fraud)  
- ROC & PR Curves

---

## 💡 Business Value
- **High Recall (0.86):** Fraudulent cases are rarely missed → reduces financial losses  
- **Explainability:** Fraudulent patterns identified — unusual amounts, odd timings, rapid bursts of transactions  
- **Scalability:** Approach can extend to other financial anomaly detection tasks  

---

## 🔮 Future Work
- Incorporate **cost-sensitive learning** to weigh fraud vs false alarms  
- Periodic **model retraining** as fraud patterns evolve  
- Integration into a **real-time fraud detection system** (optional deployment)  

---

## ⚒️ Tech Stack
- **Python:** scikit-learn, XGBoost, imbalanced-learn  
- **Data:** Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Development:** Google Colab 

---

👤 **Author:** Mohamed Dilrose P M  
📅 **Year:** 2025  
