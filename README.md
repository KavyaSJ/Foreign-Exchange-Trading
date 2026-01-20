# Foreign-Exchange-Trading

📌 Project Overview

This project develops and evaluates a machine learning–driven trading strategy using historical market data. Multiple models—including Logistic Regression, Random Forest, LightGBM, and a Two-Stage TensorFlow Neural Network—are applied to predict trading signals (Long / No Trade / Short) while carefully avoiding data leakage through time-aware validation.

The project emphasizes robust data preparation, time-series–aware modeling, and realistic backtesting with transaction costs.

🎯 Objectives

Predict trading signals using machine learning models

Compare traditional ML models with ensemble and neural network approaches

Minimize data leakage using time-based splits and purge windows

Analyze feature importance and model interpretability

🧠 Models Implemented

Logistic Regression (baseline model)

Random Forest Classifier

LightGBM

Two-Stage TensorFlow Neural Network

Stage 1: Trade filter (−1, 0, +1)

Stage 2: Direction classifier (−1, +1)

🗂️ Dataset Description

Historical market price data at fixed time intervals

Engineered technical indicators:

RSI, ADX, ATR, volatility

ATR ratio across timeframes

Fractal dimension

Time-based cyclical features (hour_sin, hour_cos)

Target labels:

1 → Long

0 → No trade

−1 → Short

⏳ Data Splitting Strategy

Time-based splits were used to ensure realistic evaluation:

Split	Period
Train	Up to 2021-12-31
Validation	2022–2023
Test	2024–2025

16-bar purge window applied between splits to prevent leakage

Scaling fitted on training data only

⚙️ Data Preparation

Feature engineering using technical indicators

Standardization using StandardScaler

Handling missing values from rolling indicators

Class imbalance addressed via class weights and two-stage modeling

📊 Evaluation Metrics
Classification Metrics
Accuracy
Precision, Recall, F1-score

<img width="627" height="263" alt="image" src="https://github.com/user-attachments/assets/674aa7fb-5114-4b80-b90a-a757dfadf8d2" />


ROC-AUC (One-vs-Rest for multiclass)

<img width="881" height="690" alt="image" src="https://github.com/user-attachments/assets/b8b2c37d-1e0d-4ed1-90e7-15c4577f2b57" />


Trading Performance Metrics

Cumulative returns

Sharpe ratio

Strategy vs Buy-and-Hold comparison

<img width="1587" height="701" alt="image" src="https://github.com/user-attachments/assets/a2afcd6b-9498-42a4-9c79-e7e98bfddcbe" />

Feature Importance

<img width="1278" height="692" alt="image" src="https://github.com/user-attachments/assets/e57db566-cc86-43cc-9bde-c33dbd015a6f" />

Transaction cost modeling

📈 Results Summary

Ensemble models (Random Forest, LightGBM) outperformed Logistic Regression

Two-stage TensorFlow model improved trade quality by filtering low-confidence trades

Feature importance highlighted the impact of:

Volatility

ATR ratios

Time-based cyclical features

Strategy performance remained sensitive to transaction costs and trade frequency
