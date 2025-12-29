<div align="center">
  <img width="180px" src="https://img.icons8.com/fluency/240/artificial-intelligence.png"/>
</div>

<h1 align="center">Loan Approval Prediction</h1>
<h3 align="center">CRISP-DM Machine Learning Portfolio</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python"/>
  <img src="https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikitlearn"/>
  <img src="https://img.shields.io/badge/Imbalanced--Learn-SMOTE-green"/>
  <img src="https://img.shields.io/badge/Status-Build%20Passing-brightgreen"/>
</p>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">📌 Business Understanding</h2>
      <p>
        Proyek ini berfokus pada permasalahan <strong>persetujuan pinjaman (loan approval)</strong> yang umum dihadapi oleh institusi keuangan.
        Keputusan kredit yang tidak akurat dapat menyebabkan <strong>risiko gagal bayar</strong> atau <strong>kehilangan calon nasabah potensial</strong>.
      </p>
      <p>
        Tujuan utama dari proyek ini adalah membangun <strong>model klasifikasi yang akurat, stabil, dan seimbang</strong> untuk membantu
        pengambilan keputusan kredit berbasis data.
      </p>

<h4>🎯 Business Objectives</h4>
<ul>
  <li>Memprediksi status persetujuan pinjaman (Approved / Unapproved)</li>
  <li>Menangani data imbalance secara profesional</li>
  <li>Menyediakan model yang siap untuk deployment</li>
</ul>

<h4>📈 Success Metrics</h4>
<ul>
  <li>F1-Score (Weighted)</li>
  <li>ROC-AUC</li>
  <li>Stabilitas cross-validation</li>
  <li>Interpretabilitas fitur</li>
</ul>
    </td>
  </tr>
</table>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">📊 Data Understanding</h2>

<p><strong>Dataset:</strong> <code>loan_data.csv</code></p>
<p><strong>Target Variable:</strong> <code>loan_status</code> (0 = Unapproved, 1 = Approved)</p>

<h4>Key Features</h4>
<ul>
  <li><code>person_age</code></li>
  <li><code>person_income</code></li>
  <li><code>credit_score</code></li>
  <li><code>loan_amnt</code></li>
  <li><code>loan_int_rate</code></li>
  <li><code>loan_percent_income</code></li>
</ul>

<div align="center">
  <img width="420" src="loan_status_pie.png" alt="Loan Status Distribution"/>
</div>
    </td>
  </tr>
</table>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">🛠️ Data Preparation</h2>

<ul>
  <li><strong>Outlier Treatment:</strong> IQR-based trimming</li>
  <li><strong>Imbalance Handling:</strong> SMOTE</li>
  <li><strong>Scaling:</strong> RobustScaler</li>
  <li><strong>Feature Engineering:</strong>
    <ul>
      <li>Credit Utilization</li>
      <li>Income-to-Loan Ratio</li>
      <li>Credit Risk Category</li>
    </ul>
  </li>
</ul>

<div align="center">
  <img width="500" src="heatmap.png" alt="Correlation Heatmap"/>
</div>
    </td>
  </tr>
</table>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">🤖 Modeling</h2>

<p>Beberapa algoritma Machine Learning diuji dan dibandingkan:</p>

<ul>
  <li>Logistic Regression</li>
  <li>Random Forest</li>
  <li>Gradient Boosting</li>
  <li>Support Vector Machine (SVM)</li>
  <li>K-Nearest Neighbors (KNN)</li>
</ul>

<p>
Seluruh model dituning menggunakan <strong>GridSearchCV</strong> dengan
<strong>5-Fold Cross Validation</strong> untuk memastikan generalisasi model.
</p>
    </td>
  </tr>
</table>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">✅ Evaluation</h2>

<div align="center">
  <img width="600" src="model_comparison.png" alt="Model Comparison"/>
</div>

<div align="center">
  <img width="600" src="roc_curve.png" alt="ROC Curve"/>
</div>

<div align="center">
  <img width="400" src="cm.png" alt="Confusion Matrix"/>
</div>

<div align="center">
  <img width="600" src="cr.PNG" alt="Classification Report"/>
</div>

<p align="center">
Model terbaik dipilih berdasarkan keseimbangan antara <strong>Recall</strong>,
<strong>Precision</strong>, dan <strong>ROC-AUC</strong>.
</p>
    </td>
  </tr>
</table>

---

<table align="center">
  <tr>
    <td width="1200">
      <h2 align="center">🚀 Deployment & Next Steps</h2>

<ul>
  <li>Menyimpan model dan scaler menggunakan <code>joblib</code></li>
  <li>Deploy melalui <strong>Flask / FastAPI</strong></li>
  <li>Monitoring data drift dan imbalance baru</li>
  <li>Menambahkan explainability dengan <strong>SHAP / Permutation Importance</strong></li>
</ul>
    </td>
  </tr>
</table>

---

<p align="center">
<strong>📌 This project is designed as a production-ready Machine Learning portfolio using CRISP-DM.</strong>
</p>
