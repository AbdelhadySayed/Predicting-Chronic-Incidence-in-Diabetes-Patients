# Predicting Chronic Incidence in Diabetes Patients

## Overview
This project aims to predict whether a patient with Type 2 Diabetes Mellitus (DM) is at risk of developing chronic complications. The dataset includes various patient-related features such as demographics, laboratory results, and medical history. Using machine learning models, we analyze these factors and build a predictive model to assist healthcare professionals in identifying high-risk patients.

## Dataset Description
The dataset contains the following key features:
- **Unique_Identifier**: Patient tracking identifier.
- **Gender**: Male or Female.
- **Religion & Nationality**: Categorical data that was preprocessed.
- **Avg_HBA1C Results**: Average Hemoglobin A1C test results.
- **HBA1C Test Compliance**: Compliance with HBA1C testing recommendations.
- **D_Of_Birth**: Date of birth, converted to age.
- **Diagnosis_Type**: Type of diabetes diagnosis (all are Type II).
- **Acute_flag**: Indicates if the patient had acute complications.
- **ER_flag_bef_chronic & # ER_befor_Chr**: Emergency room visits before chronic complications.
- **IP_flag_bef_chr & # IP_bef_chr**: Inpatient admissions before chronic complications.
- **# OP_Bef_chr**: Number of outpatient visits before chronic complications.
- **Comorbidity**: Presence of pre-existing conditions.
- **Various chronic conditions**: Includes hypertension, obesity, stroke, etc.

## Methodology
### 1. Data Exploration & Cleaning
   - Standardized categorical variables (e.g., Religion, Nationality).
   - Converted date of birth to patient age.
   - Addressed missing values (e.g., median imputation for Avg_HBA1C Results).
   - Removed redundant and irrelevant features.

### 2. Feature Engineering
   - Created new features combining ER/IP visit flags and visit counts.
   - Removed low-variance features (e.g., Cardiovascular Diseases).

### 3. Model Development
   - Split data into training and validation sets.
   - Trained multiple machine learning models:
     - Logistic Regression
     - Random Forest (best performing model)
     - K-Nearest Neighbors (KNN)
     - Support Vector Classifier (SVC)
     - LightGBM (LGB)
     - XGBoost (XGB)
   - Evaluated using **Accuracy, F1-score, PR_AUC, ROC AUC, Recall, and Precision**.
   - Focused on improving recall for the minority class (chronic complications).
   - Hyperparameter tuning via **Random Search CV**.

### 4. Inference on Test Data
   - Applied the same preprocessing steps as training.
   - Used the trained Random Forest model for predictions.
   - Generated output as a CSV file with `Unique Identifier` and predicted `Chronic flag`.

## Results
- **Key predictive features**: Outpatient visits, Avg_HBA1C result, Acute flag, and Age.
- **Performance**: The **Random Forest** model provided the best classification for chronic complications.
- **Limitations**: Misclassification of some patients, especially the minority class.

## Deliverables
- A **Jupyter Notebook (`.ipynb`)** with full data preprocessing, model training, and evaluation.
- A **detailed report (`.pdf`)** explaining methodology, insights, and findings.
- A **CSV file** containing predictions for unseen test data.

## Future Improvements
- Additional feature engineering.
- Collecting more patient data to improve model generalization.
- Extensive hyperparameter tuning.


