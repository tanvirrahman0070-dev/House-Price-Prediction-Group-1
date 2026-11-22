# House Price Prediction (Group 1)

[![Open In Colab](https://shields.io)](https://google.com)


## Overview
This project focuses on predicting residential house prices using supervised Machine Learning regression techniques on the classic **Boston Housing Dataset** (Harrison & Rubinfeld, 1978). It explores how structural and neighborhood characteristics relate to median home values to build accurate, reproducible predictive models.

Two regression algorithms—**Simple Linear Regression** (using average number of rooms) and **Multiple Linear Regression** (using all 13 housing features)—are implemented and evaluated to compare their predictive performance.

## Objectives
* Analyze housing data to identify key factors influencing residential property prices.
* Apply reproducible data preprocessing, including duplicate and missing value checks, outlier removal (506 to 466 records), an 80/20 train-test split, and feature scaling.
* Build, evaluate, and compare Simple and Multiple Linear Regression models using standard error and accuracy metrics.

## Machine Learning Algorithms
* **Simple Linear Regression (Baseline):** Models the linear relationship between a single predictor—the average number of rooms per home—and median house price to establish a simple benchmark.
* **Multiple Linear Regression (Full Model):** Models the combined effect of all 13 structural, environmental, and neighborhood predictors on median house price to capture real-world pricing patterns.

## Methodology
1. **Data Acquisition & Inspection:** Loaded the 506-record, 14-variable Boston Housing dataset (OpenML ID: 531) and verified data types, summary statistics, missing values (0 found), and duplicate rows (0 found).
2. **Outlier Filtering:** Applied the Interquartile Range (IQR) rule to median home values, removing 40 extreme upper-end outliers and retaining **466 clean records**.
3. **Train-Test Split:** Divided the cleaned dataset into **80% training (372 rows)** and **20% testing (94 rows)** using a fixed random seed (42) for reproducibility.
4. **Leak-Free Feature Scaling & Modeling:** Standardized input features inside Scikit-learn pipelines so scaling parameters are learned strictly from training data before fitting both regression models.

## Evaluation
Both models are evaluated on the unseen test set (94 homes) using four standard regression metrics:
* **MAE (Mean Absolute Error):** Average absolute difference between predicted and actual house prices.
* **MSE (Mean Squared Error):** Average squared prediction error, which penalizes larger mistakes.
* **RMSE (Root Mean Squared Error):** Average prediction error measured in thousands of dollars.
* **R² (Coefficient of Determination):** Percentage of variation in house prices explained by the model.

| Model | MAE ($1000s) | MSE | RMSE ($1000s) | R² Score |
| :--- | :---: | :---: | :---: | :---: |
| **Simple Linear Regression (Rooms Only)** | 4.3005 | 33.6584 | 5.8016 | 0.1610 |
| **Multiple Linear Regression (All Features)** | **2.2310** | **9.9293** | **3.1511** | **0.7525** |

* **Key Result:** Multiple Linear Regression explains **75.25%** of house price variation (up from **16.10%**) and lowers average prediction error from **5,802 USD** down to **3,151 USD**.

## Repository Contents
* **Group1_House_Price_Prediction.ipynb** — Complete Python notebook with code, visualizations, and analysis.
* **Group1_House_Price_Prediction.pdf** — Formatted PDF report of the project.
* **BostonHousing.csv** — Dataset file ([OpenML Data ID: 531](https://openml.org)).
