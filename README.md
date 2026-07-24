# 🧬 Colorectal Cancer Survival Analysis

![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-data%20wrangling-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-numerical-013243?style=flat-square&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-hypothesis%20testing-8CAAE6?style=flat-square&logo=scipy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-modeling-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-charts-11557C?style=flat-square&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-visualization-4C72B0?style=flat-square)
![Jupyter](https://img.shields.io/badge/Jupyter-notebook-F37626?style=flat-square&logo=jupyter&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-dashboard-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-styling-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-interactivity-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-docx%20report-339933?style=flat-square&logo=node.js&logoColor=white)

> 🩺 Exploratory Data Analysis · 🧪 Statistical Hypothesis Testing · 🤖 Predictive Modeling

A full analytical pipeline applied to a colorectal cancer patient dataset — built to predict **survival status** from demographic, clinical, and lifestyle factors. The project walks through EDA, hypothesis testing, and two classification models, and reports an honest, evidence-backed conclusion rather than forcing a narrative onto the numbers.

---

## 🔍 Key Finding

> **No variable in this dataset shows a statistically reliable relationship with survival.**

| 📊 Metric | Value |
|---|---|
| 👥 Patients analyzed | 89,945 |
| 🧬 Variables tested | 28 |
| ✅ Baseline / model accuracy | 74.87% |
| 📈 Best ROC-AUC achieved | 0.5055 *(≈ random guessing)* |
| 🚩 Features significant at p < 0.05 | 1 of 28 *(consistent with chance)* |

Both **Logistic Regression** and **Random Forest** converge to predicting the majority class ("Survived") for nearly every patient — confirmed across a single train/test split *and* 5-fold cross-validation.

---

## 🛠️ Tools & Tech Stack

| | Tool / Library | Role |
|---|---|---|
| 🐍 | **Python** | Core language for the entire pipeline |
| 🐼 | **pandas** | Data loading, cleaning, aggregation |
| 🔢 | **NumPy** | Numerical operations, histogram binning |
| 🧪 | **SciPy** | Chi-Square tests, Welch's t-tests |
| 🤖 | **scikit-learn** | Preprocessing, Logistic Regression, Random Forest, cross-validation, metrics |
| 📊 | **Matplotlib** | Static chart generation for the report |
| 🌊 | **Seaborn** | Statistical visualizations in the notebook |
| 📓 | **Jupyter Notebook** | EDA, modeling, and narrative documentation |
| 🌐 | **HTML5 / CSS3 / JavaScript** | Interactive dashboard (hand-rolled SVG charts, no chart libraries) |
| 📝 | **docx (Node.js)** | Automated Word report generation |
| 🎭 | **Playwright** | Headless-browser QA of the dashboard before delivery |

---

## 📂 Repository Structure

```
📦 colorectal-cancer-survival-analysis
├── 📓 colorectal_cancer_prediction_solved.ipynb    # Full EDA + stats + modeling notebook
├── 📊 colorectal_cancer_survival_dashboard.html    # Interactive single-file dashboard
├── 📝 colorectal_cancer_survival_report.docx       # Formal Word report
├── 📄 colorectal_cancer_prediction.csv             # Source dataset
└── 📖 README.md                                    # You are here
```

---

## 🗺️ Analysis Pipeline

1. **🔎 Data Exploration** — load, inspect shape/dtypes, check for missing values *(none found)*
2. **🧹 Preprocessing** — label-encode binaries, ordinal-map ordered categories, one-hot encode nominal categories, standardize numerics
3. **📈 EDA** — survival split, age/BMI distributions, survival rate by subgroup (stage, tumor aggressiveness, smoking, recurrence, etc.)
4. **🧪 Hypothesis Testing** — Chi-Square tests (25 categorical features) + Welch's t-tests (3 numerical features) against `Survival_Status`
5. **🤖 Modeling** — Logistic Regression + Random Forest, evaluated via accuracy, ROC-AUC, confusion matrix, and 5-fold stratified cross-validation
6. **✅ Verdict** — evidence-based conclusion with recommended next steps

---

## 📈 Results Snapshot

| Model | Accuracy | ROC-AUC | Beats baseline? |
|---|---|---|---|
| ⚪ Baseline (majority class) | 74.87% | 0.5000 | — |
| 📐 Logistic Regression | 74.87% | 0.5055 | ❌ No |
| 🌳 Random Forest | 74.87% | 0.5055 | ❌ No |

🔬 **24 of 25** Chi-Square tests and **all 3** t-tests came back non-significant at α = 0.05. The single exception (`Radiotherapy_Received`, p = 0.044) falls within the range expected from chance alone across 28 independent tests.

---

## 🚀 Next Steps

- 🔁 Verify the data-generation process for an intended feature–outcome relationship
- ➕ Engineer interaction features (e.g. `Stage × Tumor_Aggressiveness`)
- ⚡ Try gradient boosting (XGBoost / LightGBM) with hyperparameter tuning as a final check
- ⚖️ Apply SMOTE or class-weighting if a genuine signal turns up in a revised dataset

---

## 💡 Why Report a Null Result?

Reporting an honest null result — backed by hypothesis testing, multiple models, and cross-validation — is a more defensible analytical outcome than forcing a narrative onto a 74.9% accuracy figure that merely reflects class imbalance. 🎯

---

## 👤 Author
# Mayank

Built as a **data science & analyst portfolio project** exploring the full EDA → statistics → modeling → reporting workflow, including translating findings into an interactive dashboard and a client-ready Word report.

⭐ If you found this useful, consider starring the repo!
