# Time Series Anomaly Detection and Forecasting
<a target="_blank" href="https://colab.research.google.com/github/Yagami11111/Tensorflow-Muti-Variate-Time-Series-Analysis/blob/main/main.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## Project Overview

This repository contains a comprehensive Tensorflow project on time series anomaly detection and forecasting for maintaining a better availability of quantuam computer. The project involves various phases such as data loading, preprocessing, anomaly detection, and time series forecasting using multiple models. The primary objective is to develop accurate models to detect anomalies in time series data from IoT sensors and forecast future values to build a forecasting boosted anomaly detection system.

## Directory Structure

- `data_loading.py`: Script for loading data.
- `data_preprocessing.py`: Script for preprocessing the data.
- `databases/`: Directory containing database files.
  - `cd230831.db`: Data start from 08/31/2023
  - `cd230926.db`: Data start from 09/26/2023
  - `cd240111.db`: Data start from 01/11/2024
- `db_definition.py`: Script defining database schema.
- `hypermodels/`: Directory for hyperparameter tuning models, containing hyperparameters and weights.
  - `lstm_ad/`
  - `lstm_forecast/`
  - `nbeats_forecast/`
- `main.ipynb`: Jupyter notebook for the main analysis.
- `naive_anomaly_detection.py`: Script for naive anomaly detection.
- `processed_datasets/`: Directory for generated datasets during processing.
- `README.md`: This README file.
- `saved_models/`: Directory for saved models.
  - `AD_model/` Trained LSTM Auto-Encoder model
    - `xgb_model.pkl`Trained XGB model
- `Technical Report.pdf`: Detailed technical report of the project.
- `visualization.py`: Script for data visualization.

## Data Description

The dataset for this project was collected from IoT sensors affixed on Quantum computers in the laboratory. Data was aggregated in real-time in an InfluxDB database, known for handling time-series data.

These databases share a common structure, containing datasets for temperature (inside the fridge), maxigauge (pressure data), and cooling (cooling water temperature). Each record includes a unique identifier, sensor location channel, measurement value, and timestamp. The cooling datasets also feature an "io" column indicating the cooling pump's input/output channel.

## Anomaly Detection

### Models and Methods

- **Naive Anomaly Detection Method:** A simple method using gradients and moving averages to detect anomalies.
- **Classification Model with Manual Labels:** A random forest model trained on manually labeled data.
- **Isolation Forest:** An unsupervised machine learning model for anomaly detection.
- **Local Outlier Factor (LOF):** A density-based anomaly detection model.
- **LSTM Auto-Encoder:** A deep learning model for detecting anomalies based on reconstruction loss.

### Benchmarks and Metrics

The performance of anomaly detection models was evaluated using Excess-Mass (EM) and Mass-Volume (MV) metrics, introduced by Nicolas(2016).

## Time Series Forecasting

### Models and Methods

- **LSTM Forecasting Model:** A model using LSTM layers to forecast future values.
- **N-BEATS:** A non-recurrent neural network architecture for time-series forecasting.
- **XGBoost:** A gradient boosting model adapted for time series forecasting.
- **ARIMA:** A classical statistical model for time series forecasting.

### Benchmarks and Metrics

The forecasting models were evaluated on unseen test data using metrics such as MAE, MSE, RMSE, and MAPE.
