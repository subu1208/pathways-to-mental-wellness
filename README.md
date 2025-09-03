# Prediction Models for Mental Health Analysis

This project builds and evaluates machine learning models to predict depression (binary classification) based on personal, mental health, and socioeconomic features. The dataset includes preprocessed data for 2020, 2021, and 2022.

## Dataset

This project uses the SAMHSA Mental Health Client-Level Dataset (MH-CLD), which provides comprehensive information about mental health service utilization and client characteristics.
Dataset Source: SAMHSA Mental-Health Client-Level Dataset
The MH-CLD contains client-level data on mental health treatment admissions and discharges, including demographics, diagnoses, and treatment information from facilities that receive public funding.

## Project Overview

We implemented and compared the following models:

- **Baseline Model**: A simple benchmark using the majority class
- **Random Forest (RF)**: Handles complex interactions and provides feature importance
- **Logistic Regression (LR)**: Establishes an interpretable baseline
- **XGBoost**: Optimizes performance through gradient boosting
- **Support Vector Machine (SVM)**: Effective in handling non-linear relationships but computationally intensive

## File Structure

```
├── mhcld_puf_2020.csv          # Dataset for 2020
├── mhcld_puf_2021.csv          # Dataset for 2021
├── mhcld_puf_2022.csv          # Dataset for 2022
├── Code(without SVM).ipynb     # Baseline, RF, LR, and XGBoost models
└── Code(SVM).ipynb             # SVM model implementation
```

### Code Files Description

- **`Code(without SVM).ipynb`**
  - Contains data preprocessing and implementation of Baseline, Random Forest, Logistic Regression, and XGBoost models
  - These models are computationally efficient and produce results quickly

- **`Code(SVM).ipynb`**
  - Includes only the Support Vector Machine (SVM) model implementation
  - SVM is time-consuming to train, so it was separated into its own file for workflow efficiency

## Evaluation Metrics

The following metrics were used to evaluate model performance:

| Metric | Description |
|--------|-------------|
| **Accuracy** | Measures overall correctness |
| **Precision** | Proportion of positive predictions that are correct |
| **Recall** | Proportion of actual positives correctly identified |
| **F1-Score** | Balances precision and recall |
| **Confusion Matrix** | Provides a detailed breakdown of predictions |
| **ROC Curve and AUC** | Analyzes the trade-off between sensitivity and specificity |

## Key Results

| Model | Accuracy | Key Insights |
|-------|----------|--------------|
| **Baseline Model** | ~67% | Sets a minimum benchmark |
| **Random Forest** | 81.53% | Key features: BIPOLARFLG_1, SCHIZOFLG_1, NUMMHS |
| **Logistic Regression** | 81.23% | Refined after removing dominant features |
| **XGBoost** | 82.61% | Balanced performance, key features: ANXIETYFLG_1, TRAUSTREFLG_1 |
| **SVM** | 80.03% | Good performance but computationally intensive |

## Feature Importance

Different models highlighted various important features:

- **Logistic Regression**: State Indicators (e.g., New Hampshire, South Carolina)
- **Random Forest**: Bipolar Disorder, Schizophrenia Disorder, Education, Marital Status
- **XGBoost**: Anxiety Disorder, Trauma- and Stressor-related Disorders, Education
- **SVM**: Schizophrenia Disorder, Bipolar Disorder, Other Mental Disorder, Conduct Disorder

## How to Run the Code

### Prerequisites

Install the required libraries:

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn
```

### Running the Models

1. **Run `Code(without SVM).ipynb`**
   - Processes the data and trains the Baseline, Random Forest, Logistic Regression, and XGBoost models
   - These models run relatively quickly

2. **Run `Code(SVM).ipynb`**
   - Includes the SVM model training and evaluation
   - **Note**: SVM may take longer depending on your system

## Conclusion

By splitting the code into two files, we efficiently balanced computational time and workflow. The project demonstrates how different models can provide complementary insights into feature importance and prediction accuracy.

---

**Best Performance**: XGBoost achieved the highest accuracy at 82.61%, making it the optimal model for this mental health prediction task.
