# ❤️ Heart Disease Prediction

Exploratory data analysis (EDA), data cleaning and preprocessing on a heart disease dataset, with the aim of building a machine learning model that predicts whether a patient has heart disease.

> **Status:** Data cleaning & preprocessing ✅ | Model building 🚧 (in progress)

---

## 📌 Project Overview

Heart disease is one of the leading causes of death worldwide. This project uses clinical features of patients (age, blood pressure, cholesterol, ECG results, etc.) to understand what factors are linked with heart disease, and prepares the data for a classification model.

**Goal:** Given a patient's clinical measurements, predict `HeartDisease` (1 = has heart disease, 0 = normal).

---

## 📂 Dataset

- **File:** `heart_data.csv`
- **Rows:** 918
- **Columns:** 12 (11 features + 1 target)
- **Duplicates:** 0
- **Missing values:** 0 (but some invalid zeros, see Data Cleaning)
- **Class balance:** 508 with heart disease (1), 410 without (0), fairly balanced

### Feature Description

| Column | Type | Description |
|---|---|---|
| `Age` | Numeric | Age of the patient (years) |
| `Sex` | Categorical | `M` = Male, `F` = Female |
| `ChestPainType` | Categorical | `TA` Typical Angina, `ATA` Atypical Angina, `NAP` Non-Anginal Pain, `ASY` Asymptomatic |
| `RestingBP` | Numeric | Resting blood pressure (mm Hg) |
| `Cholesterol` | Numeric | Serum cholesterol (mg/dl) |
| `FastingBS` | Binary | Fasting blood sugar > 120 mg/dl (1 = yes, 0 =
