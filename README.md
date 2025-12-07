# horse-race-times-ml
Machine Learning project exploring variables in horse racing.

horse-race-times-ml

This project predicts horse racing finishing times using a cleaned and engineered dataset derived from Raceform data. I used exploratory data analysis, feature engineering, and several machine learning models to evaluate which methods best explain variation in race outcomes. This repository contains the full work completed for the Machine Learning (Fall 2025) capstone.

Repository Structure

01_exploration.ipynb – Data cleaning, feature engineering, and exploratory data analysis
modeling.ipynb – Full modeling pipeline, experiments, model comparison, and results
rf_model.pkl – Saved Random Forest model
requirements.txt – Project dependencies
README.md – Project documentation

Data Source

The dataset used in this project is raceform_small.csv, stored in the repository under the data folder. It contains approximately 50,000 horse races with variables including:

distance
going (track condition)
weight
age
time
course
jockey and trainer
performance metrics (OR, RPR, ts)

Feature Engineering

Several preprocessing steps were applied:

time_to_seconds: converts race times from formats such as "m s" or "mm:ss" into total seconds

convert_distance: standardizes distances by converting miles and furlongs into total furlongs

weight_to_lbs: converts weight from stones-pounds format into total pounds

high-missing columns were dropped

the final modeling dataset includes distance_f, age, weight_lbs, going, and course

the target variable is ts (Timeform speed rating)

Machine Learning Models

The modeling notebook compares six supervised learning models:

Linear Regression

Ridge Regression

Lasso Regression

k-Nearest Neighbors

Random Forest

Gradient Boosting Regressor

Additional experiments include:

a baseline mean-target predictor

3-fold cross-validation on a sample of the training data

evaluation on a held-out test set

an ablation study comparing different feature subsets

a robustness check for short, medium, and long race distances

Random Forest diagnostics (predicted vs actual, residuals, and feature importance)

The Random Forest model is saved as rf_model.pkl.

How to Run

Open and run all cells in 01_exploration.ipynb. This notebook handles initial cleaning and exploratory analysis.

Open and run all cells in modeling.ipynb. This notebook runs the full modeling pipeline, generates comparison tables and plots, and saves the final model.

Requirements

Install the required packages with:

pip install -r requirements.txt

The requirements file contains:

pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
shap

Notes

All preprocessing is handled with a single ColumnTransformer for numeric and categorical variables. The experiments are reproducible and meet the capstone expectations for modeling depth, analysis, and documentation.
