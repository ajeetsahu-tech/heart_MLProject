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
| `FastingBS` | Binary | Fasting blood sugar > 120 mg/dl (1 = yes, 0 = no) |
| `RestingECG` | Categorical | `Normal`, `ST` (ST-T wave abnormality), `LVH` (left ventricular hypertrophy) |
| `MaxHR` | Numeric | Maximum heart rate achieved |
| `ExerciseAngina` | Binary | Exercise-induced angina (`Y` / `N`) |
| `Oldpeak` | Numeric | ST depression induced by exercise relative to rest |
| `ST_Slope` | Categorical | Slope of the peak exercise ST segment: `Up`, `Flat`, `Down` |
| `HeartDisease` | **Target** | 1 = heart disease, 0 = normal |

---

## 🧹 What Has Been Done So Far

### 1. Data Understanding
- Checked shape, columns, data types (`df.info()`), and summary statistics (`df.describe()`)
- Checked duplicates and null values
- Checked target class distribution

### 2. Exploratory Data Analysis (EDA)
- Histograms with KDE for `Age`, `RestingBP`, `Cholesterol`, `MaxHR`
- Count plots of `Sex`, `ChestPainType`, `FastingBS` against `HeartDisease`
- Box plots / violin plots for `Cholesterol` and `Age` vs `HeartDisease`
- Correlation heatmap of numeric features

### 3. Data Cleaning
- Found **invalid zero values** in `Cholesterol` and `RestingBP` (biologically impossible)
- Replaced those zeros with the **mean of the non-zero values** of the respective column
- Very high cholesterol values (~600) were kept, as they are medically possible

### 4. Preprocessing
- **One-hot encoding** of categorical columns using `pd.get_dummies(drop_first=True)`
- **Standardization** (`StandardScaler`) of numeric columns: `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`

---

## 🚀 Next Steps: Model Building Plan

1. **Define X and y**
   ```python
   X = df_encode.drop('HeartDisease', axis=1)
   y = df_encode['HeartDisease']
   ```
2. **Train-test split** (e.g. 80/20, `stratify=y`, `random_state=42`)
3. **Scale** numeric columns (fit on train data only to avoid data leakage)
4. **Train baseline models**
   - Logistic Regression
   - K-Nearest Neighbors
   - Decision Tree
   - Random Forest
   - SVM
   - XGBoost / Gradient Boosting
5. **Evaluate** using cross-validation and on the test set:
   - Accuracy, Precision, **Recall**, F1-score, ROC-AUC
   - Confusion matrix
   - For a medical problem, **recall** (not missing real patients) is especially important
6. **Hyperparameter tuning** with `GridSearchCV` / `RandomizedSearchCV`
7. **Feature importance** analysis of the best model
8. **Save the final model** with `joblib` / `pickle`
9. *(Optional)* Build a small **Streamlit / Flask** app for predictions

---

## 🛠️ Tech Stack

- Python 3
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- Google Colab / Jupyter Notebook

---

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd <repo-folder>

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn jupyter

# 3. Place heart_data.csv in the same folder as the notebook

# 4. Open the notebook
jupyter notebook MLProject.ipynb
```

---

## 📁 Project Structure

```
├── MLProject.ipynb     # EDA, cleaning and preprocessing
├── heart_data.csv      # Dataset
└── README.md
```

---

## 📊 Results

*To be added after model training.*

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|---|---|---|---|---|
| Logistic Regression | – | – | – | – | – |
| Random Forest | – | – | – | – | – |
| … | – | – | – | – | – |

---

## ⚕️ Disclaimer

This project is for educational purposes only and must not be used for real medical diagnosis.

---

## 👤 Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)
