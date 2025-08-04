# 📊 Credit Risk Prediction Using Machine Learning
**Case Study: Home Credit Default Risk – Rakamin Virtual Internship Project**

## 📖 Project Overview
Proyek ini bertujuan untuk memprediksi risiko gagal bayar (default) nasabah menggunakan dataset **Home Credit Default Risk**.  
Analisis dilakukan end-to-end mulai dari **EDA, Feature Engineering, Preprocessing, Modeling, Evaluation, hingga Business Insight dan Submission**.  

## 📂 Dataset
- Sumber: [Kaggle – Home Credit Default Risk](https://www.kaggle.com/competitions/home-credit-default-risk/data)  
- Jumlah Data:
  - Train: 307.511 baris, 122 kolom
  - Test: 48.744 baris, 121 kolom
- Target: `TARGET`
  - 0 = Tidak Default (92%)
  - 1 = Default (8%) → **imbalance**

## ⚙️ Pipeline
1. **Exploratory Data Analysis (EDA)**  
   - Distribusi target (imbalanced class)  
   - Missing values analysis  

2. **Feature Engineering (FE)**  
   - CREDIT_INCOME_RATIO  
   - ANNUITY_INCOME_RATIO  
   - CREDIT_TERM  
   - EMPLOYED_TO_AGE_RATIO  
   - Agregasi data bureau: BUREAU_CREDIT_MEAN, BUREAU_DEBT_SUM, BUREAU_OVERDUE_MAX  

3. **Preprocessing**  
   - Drop kolom dengan missing > 60%  
   - Imputasi missing values (median/modus)  
   - Encoding kategori (Label Encoding)  
   - Scaling (Standard Scaler)  
   - Train-validation split (80:20)  

4. **Modeling**  
   - Logistic Regression (baseline)  
   - Random Forest  
   - XGBoost (**best model**)  

5. **Evaluation**  
   - ROC-AUC, Confusion Matrix, Classification Report, ROC Curve  

6. **Business Insight**  
   - Skor eksternal (EXT_SOURCE) paling dominan  
   - Rasio cicilan terhadap income memengaruhi risiko default  
   - Usia muda & masa kerja singkat lebih berisiko  
   - Riwayat hutang (bureau) berkontribusi besar terhadap risiko  

## 📊 Results
- **Best Model:** XGBoost  
- **ROC-AUC (Validation):** ~0.77  
- **Top Features (XGBoost):**
  - EXT_SOURCE_2, EXT_SOURCE_3  
  - CREDIT_INCOME_RATIO  
  - ANNUITY_INCOME_RATIO  
  - EMPLOYED_TO_AGE_RATIO  
  - BUREAU_DEBT_SUM  

## 🚀 How to Run
### 1. Clone repository
```bash
git clone https://github.com/username/home-credit-risk.git
cd home-credit-risk
