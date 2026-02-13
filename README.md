# 🌡️ Daily Climate Time Series Analysis – Delhi (2013–2017)

## 📌 Project Overview

This project performs a complete **Time Series Analysis** on daily climate data of **Delhi, India** from **1st January 2013 to 24th April 2017**.

The objective of this project is to:

- Analyze trend and seasonality
- Test stationarity of the data
- Apply AR, MA, ARMA, and ARIMA models
- Understand forecasting behavior of temperature data

---

## 📂 Dataset Information

### 📍 Location:
Delhi, India  

### 📅 Time Period:
2013 – 2017 (Daily observations)

### 📊 Features:

| Feature        | Description |
|---------------|------------|
| `meantemp`    | Mean Temperature |
| `humidity`    | Humidity (%) |
| `wind_speed`  | Wind Speed |
| `meanpressure`| Atmospheric Pressure |

### 📌 Source:

Weather Underground API  

Originally developed as part of Assignment 4 – Data Analytics Course (PES University, 2019).

---

## 🔄 Data Preparation

The dataset was originally provided as:

- `train.csv`
- `test.csv`

Both datasets were combined into a single time series dataset:

```python
data = pd.concat([train, test])
data['date'] = pd.to_datetime(data['date'])
data = data.sort_values('date')
data = data.reset_index(drop=True)
data.set_index("date", inplace=True)
