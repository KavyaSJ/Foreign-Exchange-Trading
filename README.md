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

ROC-AUC (One-vs-Rest for multiclass)

Trading Performance Metrics

Cumulative returns

Sharpe ratio

Strategy vs Buy-and-Hold comparison

Transaction cost modeling

📈 Results Summary

Ensemble models (Random Forest, LightGBM) outperformed Logistic Regression

Two-stage TensorFlow model improved trade quality by filtering low-confidence trades

Feature importance highlighted the impact of:

Volatility

ATR ratios

Time-based cyclical features

Strategy performance remained sensitive to transaction costs and trade frequency
