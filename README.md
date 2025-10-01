# Credit Card Fraud Detection

A Machine Learning Approach to Minimize Fraud Losses and Investigation Costs

The project emphasizes data quality, advanced feature engineering, and model evaluation to maximize fraud detection accuracy while maintaining financial efficiency.This project develops a machine learning pipeline to detect fraudulent card transactions and reduce financial losses. Using ~98K real-world transactions, the workflow covers data cleaning, feature engineering, model training, and financial optimization.


## Repository Structure
• data_exploration.ipynb – Profiling and visualization

• cleaning_and_imputation.ipynb – Outlier handling & missing value fixes

• feature_engineering.ipynb – Derived variables creation

• feature_selection.ipynb – Filter & wrapper methods

• modeling_and_evaluation.ipynb – Model training, testing, and financial curves

## Workflow Overview:

## Data Cleaning:
• Removed extreme outliers (transactions > $3M)

• Flagged suspicious recurring amounts ($3.62)

• Filtered to valid purchases (Transtype = 'P')

• Imputed missing merchant numbers, states, and ZIPs using hierarchical mapping

## Feature Engineering:
Created 400+ derived variables to capture fraud signals, including:
• Target Encoding (fraud rates per state, day of week)

• Recency Features (days since last transaction)

• Velocity & Frequency Metrics (short/long-term activity windows)

• Amount Variability & Summaries (mean, max, standard deviation per entity)

• Anomaly Indicators (Benford’s Law deviations, suspicious patterns)

• Constructed Entities (e.g., card + state combinations)

## Feature Selection
• Filter step: Removed weak predictors based on standalone FDR@3%

• Wrapper step: Forward selection using LightGBM for incremental performance gains

• Reduced feature set to ~20–25 strong predictors

## Modeling Results: 
Evaluated multiple algorithms using Fraud Detection Rate at 3% (FDR@3%):

Logistic Regression – OOT: 0.539

Decision Tree – OOT: 0.546

Random Forest – OOT: 0.575

LightGBM – OOT: 0.580

Neural Network – OOT: 0.573

## Final Model: Random Forest, chosen for its stable and reliable performance across datasets.

#  Financial Optimization
Developed financial curves comparing fraud savings vs. false positive costs

Recommended cutoff: Top 5% of transactions

## Key Takeaway: The Random Forest model achieved strong and consistent performance, detecting over half of all fraud cases in just 3% of flagged transactions, offering significant cost savings and operational benefits.
