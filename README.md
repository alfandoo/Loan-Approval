# 🧠 Loan Approval Prediction — CRISP-DM Portfolio  

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)  
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikitlearn)  
![Imbalanced-Learn](https://img.shields.io/badge/Imbalanced--Learn-SMOTE-green)  
![Status](https://img.shields.io/badge/Build-Passing-brightgreen)  

---

## 📌 Business Understanding  
- **Problem**: Menentukan apakah aplikasi pinjaman akan **disetujui** atau **tidak**.  
- **Goal**: Membangun model klasifikasi yang **akurat & seimbang** untuk membantu keputusan kredit.  
- **Success Metrics**: F1 Score (weighted), ROC-AUC, interpretasi fitur.  

---

## 📊 Data Understanding  
- Dataset: `loan_data.csv`  
- Target: `loan_status` (0 = Unapproved, 1 = Approved)  
- Fitur utama: `person_age`, `person_income`, `credit_score`, `loan_amnt`, `loan_int_rate`, `loan_percent_income`.  

Contoh distribusi target:  

![Loan Status Distribution](assets/loan_status_pie.png)  

---

## 🛠️ Data Preparation  
- **Outlier trimming** dengan IQR.  
- **SMOTE** untuk menangani imbalance.  
- **RobustScaler** agar lebih tahan terhadap outlier.  
- **Feature Engineering**: credit utilization, income-to-loan ratio, credit risk category.  

Heatmap korelasi:  

![Heatmap](assets/heatmap_corr.png)  

---

## 🤖 Modeling  
Model yang digunakan:  
- Logistic Regression  
- Random Forest  
- Gradient Boosting  
- Support Vector Machine (SVM)  
- KNN  

Tuning dengan **GridSearchCV (5-fold CV)**.  

---

## ✅ Evaluation  
- Evaluasi pakai **Accuracy, F1 Score, ROC-AUC, CV Score**.  
- Visualisasi hasil:  

![Model Comparison](assets/model_comparison.png)  

- ROC Curve model terbaik:  

![ROC Curve](assets/roc_curve.png)  

- Confusion Matrix:  

![Confusion Matrix](assets/conf_matrix.png)  

---

## 🚀 Deployment & Next Steps  
- Simpan model & scaler (`joblib`) → deploy via **Flask/FastAPI**.  
- Monitoring: pantau data drift & imbalance baru.  
- Explainability: tambahkan **SHAP/Permutation Importance**.  
