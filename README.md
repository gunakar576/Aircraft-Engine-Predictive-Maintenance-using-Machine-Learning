# Aircraft Engine Predictive Maintenance using Machine Learning

## Overview
Predictive maintenance is an important application of machine learning in the aviation industry. Aircraft engines generate large amounts of sensor data during operation. By analyzing this data, it is possible to estimate the Remaining Useful Life (RUL) of an engine and predict failures before they occur.

This project builds a machine learning system that predicts aircraft engine failure cycles using the NASA CMAPSS turbofan engine degradation dataset. The system analyzes engine sensor readings and predicts how many operational cycles remain before the engine fails.

---

## Dataset

Dataset used: NASA CMAPSS (Commercial Modular Aero-Propulsion System Simulation)

Each dataset contains multivariate time-series data collected from multiple aircraft engines. Every engine starts in a healthy condition and gradually degrades until failure.

Each row in the dataset represents a single engine operating cycle.

### Dataset Files

train_FD001.txt  
test_FD001.txt  
RUL_FD001.txt  

### Dataset Features

engine_id – Unique identifier for each engine  
cycle – Engine operating cycle  
op1, op2, op3 – Operational settings  
sensor_1 to sensor_21 – Engine sensor measurements  

---

## Problem Statement

The goal of the project is to predict Remaining Useful Life (RUL) of aircraft engines using machine learning models.

RUL is calculated as:

RUL = Max Cycle − Current Cycle

Where:

Max Cycle = cycle where engine failure occurs  
Current Cycle = current operating cycle

The machine learning model learns degradation patterns from historical sensor data and predicts how long an engine can continue operating.

---

## Machine Learning Pipeline

The project follows a complete machine learning workflow.

### 1 Data Loading
Load the raw text dataset and assign column names.

### 2 Feature Engineering
Calculate Remaining Useful Life (RUL) for every engine cycle.

### 3 Data Cleaning
Remove constant columns that do not contribute to prediction.

Removed columns:
op3  
sensor_1  
sensor_5  
sensor_10  
sensor_16  
sensor_18  
sensor_19  

### 4 Exploratory Data Analysis
Visualize sensor distributions and correlations using:
- Histograms
- Correlation heatmaps
- Sensor trend plots

### 5 Feature Selection
Remove less useful features:

op1  
op2  
sensor_6  
sensor_9  

### 6 Feature Scaling
Apply MinMaxScaler to normalize sensor values between 0 and 1.

### 7 Train Test Split
Split the dataset into:

80% training data  
20% testing data

### 8 Model Training

The following machine learning models were trained:

Random Forest Regressor  
Gradient Boosting Regressor  
XGBoost Regressor  
Linear Regression  

### 9 Model Evaluation

Two evaluation metrics were used.

Mean Absolute Error (MAE)

MAE = mean(|Actual − Predicted|)

Root Mean Squared Error (RMSE)

RMSE = sqrt(mean((Actual − Predicted)^2))

---

## Model Performance

Random Forest  
MAE = 25.35  
RMSE = 35.91  

Gradient Boosting  
MAE = 25.50  
RMSE = 35.61  

XGBoost  
MAE = 26.87  
RMSE = 37.82  

Linear Regression  
MAE = 30.50  
RMSE = 39.67  

Random Forest performed best among the tested models.

---

## Final Test Results

Final evaluation was performed using the true RUL values from the test dataset.

MAE  = 19.37 cycles  
RMSE = 26.18 cycles  

This means the model predicts engine failure with an average error of approximately 19 operating cycles.

---

## Technologies Used

Python  
NumPy  
Pandas  
Matplotlib  
Seaborn  
Scikit-Learn  
XGBoost  

---

## Applications

Predictive maintenance models like this are widely used in:

Aircraft engine health monitoring  
Industrial equipment maintenance  
Manufacturing systems  
Automotive diagnostics  
Wind turbine monitoring  

Airlines and aerospace companies use similar systems to prevent unexpected failures and reduce maintenance costs.

---

## Future Improvements

Possible improvements for this project include:

Using deep learning models such as LSTM or GRU  
Advanced time-series feature engineering  
Hyperparameter tuning  
Building a real-time prediction dashboard  
Deploying the model using Flask or FastAPI  

---

## Author

Gunakar Soren  
NIT Rourkela
