# Hospital Length of Stay Prediction

## Project Overview

This project explores how data engineering and machine learning can be used to predict hospital Length of Stay (LOS). Accurate length-of-stay predictions can help hospitals plan bed availability, allocate resources, and support discharge planning.

The project uses a hospital dataset containing patient admission information, medical condition indicators, laboratory measurements, and length-of-stay records. It focuses on building a reproducible data preparation workflow and developing machine learning models for regression and classification.

## Business Problem

Hospitals need to manage limited beds and healthcare resources while providing appropriate patient care. Patients with longer hospital stays can increase resource demand and affect bed availability.

The objective is to use historical patient data to:

- Predict the expected hospital length of stay in days.
- Identify patients whose stays may exceed a defined threshold.
- Explore patterns in patient characteristics and hospital stay duration.
- Develop a structured, reusable data processing workflow.

## Dataset

**Dataset:** Hospital Length of Stay Dataset – Microsoft

**Source:** [Kaggle – Hospital Length of Stay Dataset](https://www.kaggle.com/datasets/aayushchou/hospital-length-of-stay-dataset-microsoft)

**Dataset size:** 100,000 records and 28 columns.

The dataset includes:

- Admission and discharge dates
- Readmission counts
- Patient gender
- Medical condition indicators
- Laboratory measurements
- Vital-sign measurements
- Hospital facility identifiers
- Length of stay in days

The dataset will be used for analysis and model development. Any dataset redistribution will follow the original source's licensing terms.

## Project Objectives

1. Inspect the dataset structure, data types, and data quality.
2. Identify missing values, duplicate records, invalid values, and potential data leakage.
3. Clean and transform the data using reproducible Python workflows.
4. Perform exploratory data analysis to understand length-of-stay patterns.
5. Build a regression model to predict length of stay.
6. Build a classification model to identify potentially extended hospital stays.
7. Evaluate model performance using appropriate metrics.
8. Document the workflow, results, limitations, and future improvements.

## Data Engineering Workflow

The project follows a structured workflow:

1. **Data ingestion:** Load the source dataset into Python using pandas.
2. **Data validation:** Inspect column types, missing values, duplicate records, and invalid values.
3. **Data cleaning:** Correct data types and handle invalid measurements.
4. **Data transformation:** Prepare features and derive the classification target.
5. **Feature preparation:** Exclude identifiers and variables that could cause target leakage.
6. **Model development:** Prepare data for regression and classification models.
7. **Evaluation:** Compare model performance and document findings.

The workflow will be organized into reusable scripts and notebooks as the project develops.

## Machine Learning Approach

### 1. Regression

The regression task predicts the number of days a patient stays in hospital.

- **Target variable:** `lengthofstay`
- **Objective:** Predict the expected length of stay in days.
- **Evaluation metrics:** Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R².

### 2. Classification

The classification task identifies whether a hospital stay is extended.

- **Target variable:** `long_stay`
- **Initial threshold:** A stay longer than 6 days is classified as an extended stay (`1`); otherwise, it is classified as not extended (`0`).
- **Evaluation metrics:** Precision, recall, F1-score, confusion matrix, and accuracy.

The classification threshold is an initial project definition and will be assessed for suitability.

## Data Quality and Leakage Prevention

The initial data exploration identified several considerations:

- The dataset contains no missing values according to the initial null-value check.
- Duplicate records were not detected in the initial checks.
- One negative glucose value was identified and marked as missing for further handling.
- The `respiration` column contains a large concentration of values at 6.5, which requires cautious interpretation.
- The `eid` identifier will not be used as a predictive feature.
- The `discharged` date will be excluded from model inputs because it directly reveals length of stay when combined with the admission date.
- The admission date will be assessed carefully before deciding whether it provides useful predictive information.

These checks help reduce data-quality problems and prevent information leakage into model training.

## Technology Stack

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook / Google Colab
- Git and GitHub

## Repository Structure

```text
hospital-length-of-stay-prediction/
│
├── README.md
├── data/
│   └── README.md
├── notebooks/
│   ├── 01_data_quality_and_eda.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_length_of_stay_regression.ipynb
│   └── 04_extended_stay_classification.ipynb
├── src/
│   ├── data_validation.py
│   ├── data_preprocessing.py
│   └── model_evaluation.py
├── reports/
│   └── figures/
└── requirements.txt
```

This is the planned structure; files will be added as each stage is completed.

## Evaluation and Results

Model training and evaluation are in progress.

The final results section will include:

- Regression performance metrics
- Classification performance metrics
- Comparison of candidate models
- Important findings from exploratory analysis
- Limitations and potential improvements

No model performance claims are made until the experiments have been completed and evaluated.

## Future Improvements

- Build a reusable and automated data validation pipeline.
- Add automated tests for data quality and transformation rules.
- Compare multiple regression and classification algorithms.
- Investigate class imbalance in the extended-stay target.
- Track experiments and model performance.
- Explore a scheduled pipeline for processing new data.
- Consider model deployment and monitoring as future extensions.

## Disclaimer

This project is for educational and portfolio purposes. Predictions are not intended to replace clinical judgment or support real-world patient-care decisions without appropriate validation, governance, and expert oversight.

## Author

**Vishvaja Umasankar**

GitHub: [Add your GitHub profile link]
