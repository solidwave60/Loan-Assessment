# End-to-end Loan Assessment ML Project

This repository contains the code and materials for a **end-to-end loan assessment machine learning project**. The project aims to determine the creditworthiness of loan applicants by predicting whether they should be granted a loan.

## Table of Contents

  - [Introduction](#introduction)
  - [Project Structure](#project-structure)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Data Preprocessing \& Feature Engineering](#data-preprocessing--feature-engineering)
  - [Modelling](#modelling)
  - [Results \& Feature Importances](#results--feature-importances)
  - [Conclusions \& Recommendations](#conclusions--recommendations)

## Introduction

**loan assessment** is the process of determining the **creditworthiness** of a loan applicant, which helps financial institutions manage risks and ensure profitability. Accurate credit underwriting decisions protect lenders from financial losses and support borrowers in accessing fair credit opportunities.

In this project, we use machine learning to model credit underwriting as a **supervised binary classification problem**, where the target variable indicates **whether a loan defaults ('Bad', 0) or not ('Good', 1)**.

## Project Structure

- `data.xlsx`: Raw dataset
- `final_data.csv`: Final dataset
- `Notebook_final.ipynb`: Jupyter notebook containing the code and analysis for the project.
- `Presentation.pdf`: Slides providing an overview of the project.

## Exploratory Data Analysis (EDA)

The dataset consists of two parts:
- **Application data** with **644 records**, detailing customer information.
- **Loan data** with **1266 records**, providing the outcome of those loans (good or bad).

These datasets were merged, resulting in a final dataset of **631 records** with **32 features**. Key points from the EDA include:
- Handling **missing values** by dropping certain columns and rows.
- Identifying and dealing with **unique values** and **low variance features**.
- Addressing the **slight class imbalance** (45% good loans vs 55% bad loans).
- Exploring and visualizing **relationships between features and the target variable**.

## Data Preprocessing & Feature Engineering

Steps taken for data preprocessing and feature engineering:
- **Standard scaling** of numerical features.
- **One-hot encoding** for nominal categorical variables.
- **Ordinal encoding** for ordinal categorical variables.
- **Creating new features** such as age, application date components, average FICO score, and various financial ratios.

## Modelling

Various machine learning models were explored, including:
- Dummy classifier (baseline)
- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting Models: XGBoost, LightGBM, CatBoost

**Model evaluation** was performed using stratified **5-fold cross-validation**, with metrics such as **balanced accuracy, precision, recall, F1-score, AUC-ROC, and AU-PRC**.

**Model selection** was done through a **combination of random search and grid search**. The final model chosen was **LightGBM**, which provided the best performance.

## Results & Feature Importances

**Permutation importance** was used to identify the most significant features for the model. The top features included:
- Average FICO score
- L2C score
- Debt-to-Income (DTI) ratio
- Age
- Monthly rent amount
- Monthly income amount

However, because of the correlations, we should be careful when interpreting those feature importances.

## Conclusions & Recommendations

Challenges faced include the small dataset size and lack of feature descriptions. Recommendations for future work:
- Collect more data or use data augmentation techniques, and then retrain the models.
- Consult domain experts for better feature understanding, which will help in the feature engineering and feature selection process.
