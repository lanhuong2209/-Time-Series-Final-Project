# 📈 Time Series Forecasting — Superstore Office Supplies Sales (2014–2017)

Final project for Time Series Analysis course.  
Analyzes and forecasts monthly Office Supplies sales from a US Superstore dataset using ARIMA and SARIMAX models.

---

## 📁 Project Structure
---

## 🚀 How to Run

> Run notebooks **in order from 01 → 05**. Each file loads data saved by the previous one via pickle files.

### 1. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels pmdarima scikit-learn scipy
```

### 2. Place dataset

Put the CSV file at:
### 3. Run notebooks in order

| File | Description |
|------|-------------|
| `01_data_clean.ipynb` | Load raw data, filter Office Supplies, resample to monthly, export `cleaned_data.pkl` |
| `02_eda.ipynb` | Visualize trends, seasonality, decomposition, ACF/PACF |
| `03_stationarity.ipynb` | ADF & KPSS tests, compare 4 stationarity transformation methods |
| `04_modeling.ipynb` | Auto-ARIMA, fit ARIMA + SARIMAX, export `models.pkl` |
| `05_evaluation_forecast.ipynb` | Compare models, MAPE/MAE/RMSE, 12-month future forecast |

---

## 📊 Results

| Model | MAPE | MAE ($) | RMSE ($) |
|-------|------|---------|---------|
| ARIMA(3,2,1) | 125.48% | 783.18 | 831.16 |
| **SARIMAX(0,1,1)×(0,1,1,12)** | **24.32%** | **199.40** | **282.18** |

> SARIMAX outperforms ARIMA by ~5x on MAPE, capturing the strong Q4 seasonal demand peak present in Office Supplies sales every year.

---

## 🛠 Tech Stack

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![statsmodels](https://img.shields.io/badge/statsmodels-0.14-green)
![pmdarima](https://img.shields.io/badge/pmdarima-2.0-green)

- **pandas, numpy** — data manipulation
- **matplotlib, seaborn** — visualization  
- **statsmodels** — ARIMA, SARIMAX, decomposition, ADF/KPSS tests
- **pmdarima** — auto_arima for automated model selection
- **scikit-learn** — MAPE, MAE, RMSE evaluation metrics

---

## 🔑 Key Findings

- Office Supplies sales show a clear **upward trend** from 2014–2017
- Strong **annual seasonality** — Q4 (Nov–Dec) consistently peaks ~2x above Q1
- First-order differencing (`d=1`) achieves stationarity (ADF p < 0.001)
- **SARIMAX(0,1,1)×(0,1,1,12)** — known as the "Airline Model" — best captures seasonal patterns
- 12-month forward forecast projects continued seasonal growth into 2018
