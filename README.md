# Airline Passenger Demand Forecasting using ARIMA

## 📌 Project Overview
Airline passenger demand forecasting is a critical task for optimizing aircraft allocation, workforce planning, and route scheduling.  
This project implements an **ARIMA (AutoRegressive Integrated Moving Average)** model to forecast **monthly airline passenger demand** using historical time series data.

The dataset exhibits a **long-term upward trend**, making it **non-stationary**. To address this, appropriate differencing techniques are applied before building the ARIMA model.

---

## 🎯 Problem Statement
An airline company wants to forecast monthly passenger demand to improve:
- Aircraft utilization
- Workforce planning
- Route scheduling
- Revenue forecasting  

Forecasting directly on non-stationary data leads to unreliable results.  
This project demonstrates how ARIMA effectively handles **non-stationary time series data**.

---

## 🧠 Approach & Methodology

### 1. Data Understanding
- Dataset contains monthly airline passenger counts
- Column used: `#Passengers`
- Time index generated manually (monthly frequency)

### 2. Exploratory Data Analysis
- Visualized passenger demand over time
- Identified upward trend → non-stationarity

### 3. Stationarity Check
- Applied **Augmented Dickey-Fuller (ADF) Test**
- Result showed non-stationarity (p-value > 0.05)

### 4. Differencing
- Applied **first-order differencing**
- Series became stationary (p-value < 0.05)
- Selected `d = 1`

### 5. Parameter Selection
- Used **ACF & PACF plots**
- Selected:
  - `p = 1`
  - `q = 1`

### 6. Model Building
- Built ARIMA(1,1,1) model
- Split data into training and testing sets

### 7. Model Evaluation
- Evaluated using:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)

### 8. Forecasting
- Generated forecasts for:
  - Test period
  - Next 12 months (future demand)

---

## 🛠️ Technologies Used
- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn

---

## 📁 Dataset Information
- Source: Classic Airline Passenger Dataset
- Column Used: `#Passengers`
- Frequency: Monthly
- Time Period: 1949 – 1960 (144 observations)

---

## 📊 Model Used
**ARIMA(1,1,1)**

| Component | Description |
|---------|-------------|
| AR (p) | Captures relationship with past values |
| I (d) | Differencing to remove trend |
| MA (q) | Handles noise and residual errors |

---

## 📈 Results
- Model successfully captured the upward trend
- Forecasts align well with actual passenger data
- Demonstrates effectiveness of ARIMA on non-stationary data

---

## ⚠️ Limitations
- ARIMA does not handle seasonality explicitly
- Performance may degrade for long-term forecasts
- Assumes linear relationships

---

## 🚀 Future Improvements
- Implement **SARIMA** for seasonality
- Use **Auto-ARIMA** for parameter tuning
- Compare with **LSTM / Prophet**
- Add confidence intervals to forecasts

---

## 👨‍💻 How to Run the Project
1. Clone the repository
2. Open Jupyter Notebook
3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib statsmodels scikit-learn
