# HPV_Prevalence_Project
# 🧬 HPVPrevalenceAI: Predicting HPV Prevalence for World wide and different states using limited and missing data,

A machine learning pipeline designed to predict the prevalence of HPV-associated cervical lesions (NCC, Low CIN, and High CIN) across Indian states using global and regional datasets, leveraging SMOGN for imbalanced regression and XGBoost for optimized prediction.

---

## 📌 Short Description

HPVPrevalenceAI is a data science project developed under **RBCDSAI, IIT Madras**. It focuses on predicting cervical lesion prevalence caused by **HPV-16** and **HPV-18**. The pipeline integrates scraped health data, advanced feature engineering, SMOGN-based data balancing, and optimized XGBoost regression models to support targeted cervical cancer screening and vaccination strategies.

---

## ⚙️ Tech Stack

- 🐍 **Python** – Core language for scraping, preprocessing, modeling  
- 📚 **Pandas, NumPy** – Data manipulation and numerical ops  
- 🔍 **BeautifulSoup, PDFMiner** – For scraping NCDIR reports and scientific PDFs  
- 🧹 **Scikit-learn** – Regression models, imputation, scaling  
- 📦 **XGBoost** – Main regression algorithm used for prediction  
- ⚙️ **Optuna** – Hyperparameter tuning (TPE search)  
- 🌐 **SMOGN** – Balancing imbalanced regression targets  
- 📈 **Matplotlib, Seaborn** – Visualization and evaluation plots

---

## 🗃️ Data Source

Data was curated from multiple reputable sources:

- 📑 **NCDIR Reports** – Indian cancer registry (state-wise)  
- 🌍 **WHO Statistics** – Female population and incidence data  
- 📖 **Scientific Literature** – Peer-reviewed sources to fill missing prevalence/mortality values  

Extracted Features:
- Cu.Rate%, Cu.Risk  
- Cancer incidence/deaths by site and age group  
- TB, Diabetes, Hypertension rates  
- Male circumcision categories  
- STI rates (syphilis, gonorrhea, chlamydia)  
- Screening program start year  

**Target Variables:**
- `NCC Combined`: Average prevalence of NCC-16 and NCC-18  
- `Low CIN Combined`: Low-grade CIN due to HPV-16 and 18  
- `High CIN Combined`: High-grade CIN due to HPV-16 and 18

---

## 🌟 Features & Highlights

### 🚨 Problem Statement

Estimating HPV prevalence across regions is challenging due to missing and highly imbalanced data. Accurate predictions are crucial for early diagnosis, vaccination strategy, and public health interventions.

### 🎯 Goals

- Predict HPV lesion prevalence across Indian states  
- Address missing data through feature engineering and imputation  
- Handle target imbalance using SMOGN  
- Support localized screening/vaccination planning with data-backed insights

---

## 🔁 Workflow Overview

### 📥 Data Collection & Scraping

- Scraped data from **NCDIR PDFs**, **WHO**, and **scientific articles**
- Extracted cancer incidence, STI rates, population estimates, and comorbidities

### 🧼 Data Preprocessing

- Cleaned redundant/irrelevant columns  
- Created engineered features like:
  - `Disease Incidence Score` (TB, diabetes, hypertension)
  - `STI Burden Score` (syphilis, gonorrhea, chlamydia)
  - `Screening Coverage Start Year` (converted to numeric)
  - `Male Circumcision Binning` (Low/Medium/High)
- Applied:
  - Min-Max normalization
  - Median/mode imputation
  - One-hot encoding for categorical variables

### 🤖 Modeling

- Models tested:
  - Random Forest Regressor  
  - Ridge Regression  
  - Support Vector Regressor  
  - XGBoost Regressor  
- Used **SMOGN** to balance rare high-prevalence cases  
- Applied **Optuna** for hyperparameter tuning  
- Trained separate models for:
  - `NCC Combined`
  - `Low CIN Combined`
  - `High CIN Combined`

---

## 🧪 SMOGN: Synthetic Oversampling for Regression

- Combines:
  - **SmoteR** (interpolation between neighbors)
  - **Gaussian Noise** (synthetic samples in sparse zones)
- Enhances prediction for underrepresented high-risk areas
- Uses a **relevance function** to decide which samples to oversample

---

## 📈 Visuals & Evaluation

- 📊 Prevalence distributions before/after SMOGN  
- 📈 Model performance metrics: **R²**, **MSE**, **cross-validation** results  
- 🗺️ Indian State-wise predicted HPV burden (maps & heatmaps)  

---

## 💡 Insights & Impact

- **Better Sensitivity**: Improved prediction for rare high-prevalence zones  
- **Data-Driven Decisions**: Enables policymakers to allocate resources more effectively  
- **Research Utility**: Supports future epidemiological modeling and public health strategies

---


