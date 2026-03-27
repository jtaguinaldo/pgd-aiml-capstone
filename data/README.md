# Data Folder

## Purpose
This folder is intended to house the dataset used by the capstone project and any other safe-to-share data-related files needed for reproducibility.

## Dataset Used
This project uses the **Credit Card Fraud Detection** dataset from Kaggle.

## Source
Source platform: Kaggle  
Dataset: Credit Card Fraud Detection

Original source page:  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## Expected File
The notebook expects the dataset file to be available as:

`data/creditcard.csv`

## Notes on Data Structure
The dataset contains:
- 284,807 transactions
- 31 variables in the original dataset
- target variable: `Class`
- predictor variables: `Time`, `Amount`, and anonymized PCA-transformed features `V1` to `V28`

The target class is highly imbalanced, with fraudulent transactions accounting for only about 0.17% of the observations.

## Practical Guidance
To reproduce the project:
1. download the dataset from the original Kaggle source
2. place the CSV file in this folder
3. ensure the filename is exactly `creditcard.csv`

## Important Note
This folder documents the data source and expected file structure for reproducibility. Users should obtain the dataset from the original source and observe the applicable usage terms.
