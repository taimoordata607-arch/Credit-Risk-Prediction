# 📉 Credit Risk Prediction

## Project Objective

The primary objective of this project is to build and evaluate machine learning models to **predict whether a loan applicant is likely to default on a loan**. This is a critical task for financial institutions to minimize risk and improve lending efficiency.

---

## 🛠️ Methodology and Models

This project implements a standard machine learning workflow, including data preprocessing, feature engineering, and training two primary classification models.

### Data Overview and Preprocessing

* **Dataset:** The analysis uses a dataset with 367 rows and 12 columns.
* **Missing Value Handling:** Missing categorical values (`Gender`, `Dependents`, `Self_Employed`) were imputed using the **mode**, while missing numerical values (`LoanAmount`, `Loan_Amount_Term`, `Credit_History`) were imputed using the **median**.
* **Feature Engineering:** A new feature, `Total_Income`, was created by summing `ApplicantIncome` and `CoapplicantIncome` to capture the total financial capacity of the applicant.
* **Data Splitting:** The data was split into training (293 samples) and testing (74 samples) sets, with a `test_size=0.2` and `random_state=42` for reproducibility.

### Models Implemented

Two distinct classification algorithms were trained and evaluated:

1.  **Logistic Regression**
2.  **Decision Tree Classifier**

---

## 📊 Summary of Results and Key Findings

The models were evaluated based on **Accuracy** and their ability to correctly classify both the default (Class 0.0) and non-default (Class 1.0) cases, as indicated by the **Confusion Matrix**.

| Model | Accuracy (on Test Set) | Performance Insight |
| :--- | :--- | :--- |
| **Logistic Regression** | **0.7432** | **Flawed:** This model exclusively predicted the majority class (Class 1.0) for all test instances. Its high accuracy is misleading, as it completely failed to identify any instances of the target risk class (Class 0.0). |
| **Decision Tree Classifier** | **0.6757** | **Robust Baseline:** Achieved lower accuracy but demonstrated a more **balanced** classification ability, correctly identifying True Negatives (Class 0.0). |

### Detailed Classification Breakdown

| Metric | Logistic Regression | Decision Tree Classifier |
| :--- | :--- | :--- |
| Confusion Matrix | `[[ 0 19], [ 0 55]]` | `[[ 7 12], [12 43]]` |
| Class 0.0 Recall | 0.00 | 0.37 (7 True Negatives / 19 Actual Negatives) |

---

## 📈 Next Steps and Future Work

Based on the current results, the following next steps are recommended to improve the predictive power and reliability of the risk model:

* **Address Class Imbalance:** The Logistic Regression model's failure to predict Class 0.0 suggests significant class imbalance. Implementing techniques like **SMOTE** (Synthetic Minority Over-sampling Technique) or adjusting **class weights** is crucial.
* **Hyperparameter Tuning:** Fine-tuning the Decision Tree model's parameters (e.g., max depth, min samples split) could significantly improve its accuracy and generalization.
* **Explore Ensemble Methods:** Moving beyond simple models, investigating **Random Forest** or **Gradient Boosting** is recommended, as these often provide better performance in imbalanced classification tasks.

---

## 🚀 Installation and Setup

To run the Jupyter Notebook (`Task 2.ipynb`) and replicate the analysis, follow these steps.

### Prerequisites

You need **Python 3.x** and a package installer like `pip`.

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <your-repository-name>
