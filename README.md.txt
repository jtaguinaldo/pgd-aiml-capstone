# PGD-AIML Capstone Project: Credit Card Fraud Detection

## Overview
This repository contains my capstone project for the Post-Graduate Diploma in Artificial Intelligence and Machine Learning (PGD-AIML).

The project addresses a real-world fraud detection problem using supervised machine learning on a highly imbalanced transaction dataset. The objective is not simply to classify transactions accurately, but to identify an approach that balances strong fraud detection performance with acceptable operational burden and customer impact.

This repository is organized as the complete project package, including the notebook, final report, slide decks, saved model artefacts, configuration files, and reproducibility outputs.

## Business Problem
Credit card fraud remains a costly and operationally sensitive issue for financial institutions. A useful fraud detection model must help reduce fraud-related losses while avoiding excessive false positives that can overload investigation teams and inconvenience legitimate customers. In this context, missing actual fraud cases is costly, but overly aggressive fraud flagging is also impractical.

## Project Objective
This project aims to:
- develop and compare machine learning models for fraud detection
- address severe class imbalance in a structured way
- evaluate models using business-relevant performance metrics
- optimize a final model for practical use
- assess explainability, limitations, subgroup behavior, and ethical risks

## Dataset
This project uses the **Credit Card Fraud Detection** dataset from Kaggle.

### Source
Source platform: Kaggle  
Dataset: Credit Card Fraud Detection

### Important Note
The raw dataset file is not included as part of the intended public redistribution workflow. To run the notebook, place the dataset in:

`data/creditcard.csv`

Please refer to `data/README.md` for data access guidance.

## Repository Structure
The repository is organized as follows:

    .
    ├── README.md
    ├── requirements.txt
    ├── .gitignore
    ├── configs/
    ├── data/
    ├── models/
    ├── notebooks/
    ├── presentations/
    ├── report/
    ├── results/
    └── src/

### Folder Guide
- `configs/` – saved model parameter and threshold configuration files
- `data/` – dataset guidance and local dataset placement
- `models/` – saved trained model and preprocessing artefacts
- `notebooks/` – main capstone notebook
- `presentations/` – final executive and technical slide decks
- `report/` – final written report
- `results/` – exported result tables and summaries
- `src/` – helper scripts, if any are added later

## Project Workflow
The project followed a structured workflow across the following stages:
1. problem understanding and framing
2. data collection and understanding
3. data preprocessing, exploratory analysis, feature engineering, feature selection, and dimensionality reduction
4. model implementation, comparison, hyperparameter tuning, and threshold optimization
5. critical thinking, ethical AI review, explainability analysis, bias auditing, and recommendations
6. executive and technical presentation development
7. repository packaging for reproducibility and submission

## Models Implemented
The modelling workflow covered:
- Logistic Regression as the baseline model
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

These models were evaluated across three feature representations:
- selected features
- full features
- PCA-transformed features

## Final Model
The final selected model is a **tuned XGBoost model using the full feature set**, with the classification threshold optimized to **0.75**. This configuration was selected because it provided the strongest overall balance across the project’s priority metrics in an imbalanced fraud setting.

## Summary of Findings
The project found that fraud detection performance must be assessed through the business trade-off between fraud capture and operational efficiency, rather than through accuracy alone.

The final selected model was a tuned XGBoost model using the full feature set, with the operating threshold optimized to 0.75. At the final threshold, the model achieved **precision of 0.9615**, **recall of 0.7895**, and **F1-score of 0.8671** for the fraud class. On the held-out test set, this translated to **75 true positives, 20 false negatives, and 3 false positives**.

The results indicate that the final model is deliberately conservative in flagging fraud. In practical terms, it is usually correct when it flags a transaction as fraudulent, which materially reduces unnecessary investigations and customer disruption. At the same time, a portion of fraud cases remains undetected, which means the model should be complemented by additional controls and ongoing monitoring.

The analysis also showed that:
- ensemble models outperformed simpler models for this use case
- hyperparameter tuning materially improved XGBoost performance, especially precision and overall balance
- threshold optimization further improved the operating point by increasing precision while maintaining reasonably strong recall
- the model performs best when fraud signals are strong, but is less effective at detecting subtle or weak-signal fraud cases
- recall is not uniform across transaction segments, particularly across time bands, indicating subgroup performance limitations that require monitoring
- although the model is technically explainable through feature importance and SHAP, business interpretability remains constrained because the most influential predictors are anonymized PCA-derived variables

## How to Run the Project
### 1. Download or clone the repository
Save a local copy of this repository.

### 2. Install dependencies
Install the required Python packages listed in `requirements.txt`.

Main packages used in this project include:
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- xgboost
- shap
- joblib

### 3. Place the dataset
Place the dataset in:

`data/creditcard.csv`

### 4. Open the notebook
Open the notebook in the `notebooks/` folder and run the cells in sequence.

## Main Files
Key files in this repository include:
- `notebooks/John_Paul_Aguinaldo_Capstone_Project.ipynb`
- `report/John_Paul_Aguinaldo_Capstone_Report.pdf`
- `presentations/` final executive and technical presentation files
- `models/` saved model and preprocessing artefacts
- `configs/step4_best_params.json`
- `configs/final_model_threshold_config.json`

## Reproducibility Notes
This repository includes the main artefacts required to reproduce the modelling workflow:
- saved trained models
- saved preprocessing artefacts
- saved parameter and threshold configuration files
- exported result tables from model comparison, tuning, and threshold optimization

The notebook uses a structured workflow in which:
- train-test split is performed before transformations
- scaling is fit on training data only
- feature selection and PCA follow the same train-first logic
- saved artefacts are exported to `models/`, `configs/`, and `results/` for reuse and auditability

## Author
**John Paul Aguinaldo**  
PGD-AIML Capstone Project

## Closing Note
This repository presents the capstone as an applied business and machine learning project. The value of the final model lies not only in its predictive performance, but also in how well it supports operational decision-making, interpretability, governance, and responsible deployment.