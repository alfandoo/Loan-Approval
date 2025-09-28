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

---

## 📂 Struktur Project  
```\nloan-approval-prediction/\n│── data/\n│   └── loan_data.csv\n│── notebook/\n│   └── loan_prediction.ipynb\n│── models/\n│   └── loan_best_model.joblib\n│── assets/\n│   ├── loan_status_pie.png\n│   ├── heatmap_corr.png\n│   ├── model_comparison.png\n│   ├── roc_curve.png\n│   └── conf_matrix.png\n│── README.md\n```\n\n---\n\n## 🔗 Notebook Colab\n👉 [Open in Google Colab](https://colab.research.google.com/) *(upload notebook di sini)*\n\n```\n\n---\n\n📌 Saran: setelah running di Colab, kamu **screenshot grafik (pie, heatmap, barplot, ROC, confusion matrix)** lalu taruh di folder `assets/` agar README jadi lebih hidup.  \n\nMau aku bikinkan juga template **.ipynb notebook siap upload ke GitHub/Colab** biar langsung sinkron sama README?
