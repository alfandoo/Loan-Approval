# 📌 Loan Approval Prediction using Machine Learning

---

## 1. Executive Summary
Proyek ini bertujuan membangun sistem prediksi persetujuan pinjaman
(*loan approval*) menggunakan machine learning berbasis data historis peminjam.
Masalah utama yang diangkat adalah proses evaluasi kredit yang masih manual,
memakan waktu, dan berisiko tidak konsisten.

Dengan pendekatan data-driven, proyek ini menghasilkan model klasifikasi
yang mampu membedakan pengajuan pinjaman **Approved** dan **Unapproved**
secara objektif serta berpotensi digunakan sebagai *decision support system*
pada proses underwriting kredit.

---

## 2. Business Problem
Lembaga keuangan menghadapi tantangan dalam menilai kelayakan kredit pemohon
secara cepat dan akurat. Ketergantungan pada evaluasi manual dapat meningkatkan
risiko kredit macet dan memperlambat proses bisnis.

Jika masalah ini tidak ditangani, dampak bisnis yang muncul meliputi:
- Tingginya risiko *non-performing loan*
- Waktu persetujuan pinjaman yang lambat
- Penurunan kepercayaan dan kepuasan nasabah

---

## 3. Objectives
Tujuan utama proyek:
- Membangun model klasifikasi untuk memprediksi status persetujuan pinjaman
- Mengidentifikasi fitur paling berpengaruh terhadap keputusan kredit
- Membandingkan performa beberapa algoritma machine learning

Target model:
- Model dengan performa stabil berdasarkan **Accuracy, F1 Score, dan ROC-AUC**

---

## 4. Dataset
- **Sumber data**:  
  Dataset publik dari Kaggle  
  *Loan Approval Classification Data*  
  https://www.kaggle.com/datasets/taweilo/loan-approval-classification-data

- **Jumlah data**: **45.000 baris**
- **Target variable**: `loan_status`
  - 1 = Approved
  - 0 = Unapproved

**Fitur utama**:
- **Demografi**:
  - `person_age`
  - `person_gender`
  - `person_education`
  - `person_home_ownership`

- **Finansial**:
  - `person_income`
  - `loan_amnt`
  - `loan_int_rate`
  - `loan_percent_income`
  - `credit_score`

- **Riwayat kredit**:
  - `cb_person_cred_hist_length`
  - `previous_loan_defaults_on_file`

- **Tujuan pinjaman**:
  - `loan_intent`


---

## 5. Data Understanding
Dataset terdiri dari kombinasi fitur numerik dan kategorikal.
Pemeriksaan awal menunjukkan adanya:
- Outlier pada fitur numerik
- Ketidakseimbangan kelas target (Approved vs Unapproved)
- Variasi kuat pada skor kredit dan pendapatan pemohon

---

## 6. Data Preprocessing
Tahapan preprocessing meliputi:
- Outlier trimming menggunakan metode **IQR**
- Feature engineering:
  - `credit_utilization`
  - `income_to_loan_ratio`
  - `credit_risk_category`
- Encoding fitur kategorikal menggunakan **Label Encoding**
- Penanganan ketidakseimbangan kelas dengan **SMOTE (train only)**
- Scaling fitur numerik menggunakan **RobustScaler**

---

## 7. Exploratory Data Analysis (EDA)
EDA dilakukan untuk memahami hubungan antar fitur dan target, dengan hasil utama:
- Credit score memiliki korelasi kuat terhadap status persetujuan pinjaman
- Rasio pinjaman terhadap pendapatan berpengaruh signifikan terhadap risiko
- Pemohon dengan riwayat gagal bayar sebelumnya cenderung ditolak

---

## 8. Modeling
Model yang digunakan:
- Logistic Regression (baseline)
- Random Forest Classifier
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Gradient Boosting Classifier

Seluruh model dituning menggunakan **GridSearchCV (5-fold CV)** dengan
metrik utama **accuracy**.

---

## 9. Model Evaluation
Evaluasi dilakukan pada data test menggunakan metrik berikut:
- Accuracy
- F1 Score (weighted)
- ROC-AUC
- Confusion Matrix
- Classification Report

Ringkasan performa model pada data test:

| Model | Accuracy | F1 Score | AUC | Cross-validation Score |
|------|----------|----------|-----|------------------------|
| Gradient Boosting | 0.9284 | 0.9275 | **0.9744** | 0.9416 |
| Random Forest | 0.9090 | 0.9105 | 0.9657 | 0.9390 |
| SVM | 0.8699 | 0.8770 | 0.9453 | 0.9040 |
| KNN | 0.8585 | 0.8662 | 0.9044 | 0.9160 |
| Logistic Regression | 0.8499 | 0.8601 | 0.9429 | 0.8846 |

Model terbaik dipilih berdasarkan **ROC-AUC tertinggi**, 
dengan **Gradient Boosting Classifier** sebagai model terbaik
karena menghasilkan performa paling konsisten pada data test
dan cross-validation.

---

## 10. Results & Insights
**Model terbaik**: **Gradient Boosting Classifier**

Insight utama:
- Credit score dan rasio pendapatan terhadap pinjaman menjadi fitur paling dominan
- Model mampu memisahkan peminjam berisiko tinggi dan rendah dengan baik
- SMOTE meningkatkan kemampuan model dalam mendeteksi kelas minoritas

Dampak bisnis:
- Mengurangi risiko persetujuan pinjaman bermasalah
- Mempercepat proses seleksi awal pemohon
- Mendukung keputusan kredit berbasis data

---

## 11. Recommendations
- Gunakan model sebagai alat *pre-screening*, bukan pengganti keputusan manusia
- Integrasikan model ke sistem underwriting internal
- Lakukan retraining model secara berkala dengan data terbaru

---

## 12. Tools & Technologies
- **Programming Language**: Python
- **Libraries**:
  - Pandas, NumPy
  - Scikit-learn
  - Imbalanced-learn (SMOTE)
  - Matplotlib, Seaborn
- **Tools**:
  - Google Colab
  - GitHub

---


---

## 13. Conclusion
Proyek ini menunjukkan bahwa pendekatan machine learning yang dikombinasikan
dengan preprocessing dan feature engineering yang tepat dapat membantu
memprediksi persetujuan pinjaman secara akurat. Model yang dihasilkan
berpotensi digunakan sebagai sistem pendukung keputusan dalam industri keuangan.

