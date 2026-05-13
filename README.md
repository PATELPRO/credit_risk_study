# Benchmarking State-of-the-Art Machine Learning Algorithms for Reproducible Credit Risk Modeling

## Project Workflow

---

# 1. Problem Statement

The project focuses on benchmarking and evaluating multiple machine learning algorithms for credit risk prediction across diverse financial datasets.

## Datasets Used
- German Credit Dataset
- Australian Credit Dataset
- Credit Score Classification Dataset
- Give Me Some Credit Dataset

This multi-dataset approach enabled:
- Cross-domain validation of modeling strategies
- Better generalization analysis
- Improved reliability of conclusions

---

# 2. Data Cleaning

Significant effort was invested in ensuring data quality and consistency.

## Text Cleaning
- Standardization of categorical labels
- Case normalization and formatting corrections
- Removal of inconsistencies and redundant representations

## Handling Duplicates & Structural Issues
- Group-level consistency checks for customer-based datasets
- Validation of repeated attributes such as income across grouped records

## Missing Value Imputation
- Group-based imputations
- Statistical imputations based on feature distribution and datatype

## Outlier Detection & Treatment
- Domain-driven thresholding strategies
- Distribution-aware outlier handling
- Preservation of financially meaningful extreme values

---

# 3. Data Preprocessing

A modular and experimental preprocessing strategy was implemented.

## Imputation Strategies
- Mean / Median Imputation
- KNN Imputation
- Group-wise Imputation
- Strategy selection based on feature behavior and distribution

## Encoding Techniques
- Ordinal Encoding for ordered categorical variables
- One-Hot Encoding for nominal variables
- Prevention of dummy variable trap

## Feature Scaling
- Logarithmic transformations for skewed variables
- Standard Scaling for distance-sensitive algorithms

---

# 4. Feature Analysis & Selection

Statistical and diagnostic techniques were used to improve feature quality and model stability.

## Statistical Tests
- Chi-Square Test for categorical feature relevance
- ANOVA for numerical feature significance

## Exploratory Analysis
- Feature distribution analysis
- Skewness and kurtosis analysis
- Correlation analysis

## Multicollinearity Analysis
- Variance Inflation Factor (VIF)
- Removal of redundant features

### Outcomes
- Reduced noise
- Improved interpretability
- Better model generalization

---

# 5. Pipeline Engineering

One of the key strengths of the project was the development of reusable and modular ML pipelines.

## Pipeline Framework
- Built modular preprocessing pipelines
- Exported and reused pipelines across notebooks
- Maintained consistent transformations across datasets

## Benefits
- Reproducibility
- Cleaner workflow separation
- Scalable experimentation

## Custom Transformer Module
Developed a custom Python module encapsulating:
- Imputation logic
- Outlier handling
- Feature transformations

---

# 6. Model Training

## Data Splitting Strategy
- Standard Train-Test Split
- Group-based splitting to prevent data leakage

## Model Development Workflow
- Imported preprocessing pipelines
- Applied feature selection
- Trained baseline and advanced models

## Algorithms Used
- Logistic Regression
- Decision Trees
- Random Forest
- XGBoost
- Additional classical ML algorithms for benchmarking

---

# 7. Hyperparameter Optimization

Multiple optimization strategies were used to improve model performance.

## Optimization Techniques
- RandomizedSearchCV
- GridSearchCV
- Optuna

## Objectives
- Efficient hyperparameter exploration
- Improved generalization
- Reduced overfitting
- Better compute utilization

---

# 8. Model Evaluation

A comprehensive evaluation framework was implemented to assess predictive performance and model reliability.

## Performance Evaluation
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- PR-AUC
- KS Statistic

## Advanced Evaluation
### Overfitting Analysis
- Train vs Test performance comparison
- Variance detection across models

### Precision-Recall Tradeoff
- Important for imbalanced credit datasets
- Focused on minimizing false negatives in risk-sensitive scenarios

---

# Key Observations

- Random Forest and XGBoost consistently achieved the best predictive performance across datasets.
- Logistic Regression provided strong calibration and interpretability despite lower predictive power.
- Ensemble methods outperformed standalone classifiers in most benchmark scenarios.
- Model performance varied significantly depending on dataset imbalance and feature distribution.
- Calibration quality and minority-class detection were critical for reliable credit risk assessment.

---

# Note

Hyperparameter optimization was primarily performed using **ROC-AUC** as the objective function.  
Depending on business requirements, optimization objectives such as **Recall** or **Precision** can be prioritized to improve performance on specific classes.
