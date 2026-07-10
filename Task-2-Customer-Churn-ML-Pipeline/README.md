# End-to-End Customer Churn Prediction Pipeline

## Overview

This project was completed as part of the **AI/ML Engineering Internship** at **DevelopersHub Corporation**.

The objective is to build a reusable and production-ready machine learning pipeline for predicting customer churn using the IBM Telco Customer Churn dataset. The project demonstrates the complete machine learning workflow, including data preprocessing, exploratory data analysis (EDA), model development, hyperparameter tuning, evaluation, and model serialization.

---

## Objective

Develop an end-to-end machine learning pipeline capable of predicting whether a customer is likely to churn by:

- Performing data preprocessing using Scikit-learn's `Pipeline` and `ColumnTransformer`.
- Training and comparing multiple machine learning models.
- Optimizing model performance using `GridSearchCV`.
- Exporting the complete preprocessing and prediction pipeline using `joblib`.

---

## Dataset

**Dataset:** IBM Telco Customer Churn Dataset

The dataset contains customer demographic information, subscribed services, billing details, and account information used to predict customer churn.

**Target Variable**

- **Churn**
  - Yes
  - No

---

## Project Workflow

1. Data Loading
2. Data Cleaning and Preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature Engineering and Preparation
5. Train-Test Split
6. Data Preprocessing using `ColumnTransformer`
7. Logistic Regression Model
8. Random Forest Model
9. Hyperparameter Tuning using `GridSearchCV`
10. Model Evaluation
11. Model Comparison
12. Exporting the Best Pipeline using Joblib

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Jupyter Notebook

---

## Machine Learning Models

- Logistic Regression
- Random Forest Classifier
- Tuned Random Forest (GridSearchCV)

---

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|------|---------:|----------:|--------:|---------:|--------:|
| Logistic Regression | **0.8055** | 0.6572 | **0.5588** | **0.6040** | **0.8419** |
| Tuned Random Forest | 0.8048 | **0.6678** | 0.5267 | 0.5889 | 0.8412 |
| Random Forest | 0.7779 | 0.6034 | 0.4759 | 0.5321 | 0.8164 |

**Best Model:** Logistic Regression

Although hyperparameter tuning significantly improved the Random Forest model, Logistic Regression achieved the highest F1-score and ROC-AUC, making it the best-performing model for this dataset.

---

## Key Findings

- The `TotalCharges` feature required conversion from object to numeric due to blank string values.
- Approximately **26.5%** of customers in the dataset had churned, indicating a moderately imbalanced classification problem.
- Customers with **month-to-month contracts**, **higher monthly charges**, and **shorter tenure** were more likely to churn.
- Logistic Regression provided the strongest overall predictive performance among the evaluated models.
- The complete preprocessing and prediction workflow was successfully exported as a reusable Scikit-learn pipeline.

---

## Repository Contents

```
Task-2-Customer-Churn-ML-Pipeline/
│
├── Customer_Churn_ML_Pipeline.ipynb
├── customer_churn_pipeline.pkl
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
└── README.md
```

---

## How to Run

1. Clone the repository.

```bash
git clone <repository-url>
```

2. Navigate to the project directory.

```bash
cd Task-2-Customer-Churn-ML-Pipeline
```

3. Install the required dependencies.

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook.

```bash
jupyter notebook
```

5. Open **Customer_Churn_ML_Pipeline.ipynb** and run all cells.

---

## Project Highlights

- End-to-end machine learning workflow
- Automated preprocessing using `Pipeline` and `ColumnTransformer`
- Hyperparameter tuning with `GridSearchCV`
- Comprehensive model evaluation using multiple metrics
- Production-ready model export with `joblib`

---

## Future Improvements

- Apply techniques such as SMOTE or class weighting to address class imbalance.
- Evaluate advanced ensemble models such as XGBoost, LightGBM, or CatBoost.
- Deploy the trained pipeline using Streamlit or Flask.
- Incorporate automated experiment tracking and model versioning.

---

## Internship Task

**AI/ML Engineering Internship**

**DevelopersHub Corporation**

**Task 2:** End-to-End ML Pipeline with Scikit-learn Pipeline API

---