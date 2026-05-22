# 📈 Time Series Forecasting — Superstore Office Supplies Sales (2014–2017)

Final project for Time Series Analysis course.  
Analyzes and forecasts monthly sales of Office Supplies from a US Superstore dataset using ARIMA and SARIMAX models.

---

## 📁 Project Structure
---

## 🚀 How to Run

> Run notebooks **in order from 01 → 05**. Each file loads data saved by the previous one.

### 1. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels pmdarima scikit-learn
```

### 2. Download dataset

Download the dataset from Kaggle and place it at:
🔗 [Superstore Dataset on Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

### 3. Run notebooks in order

| File | Description |
|------|-------------|
| `01_data_cleaning.ipynb` | Load raw data, filter Office Supplies, resample to monthly, export `.pkl` |
| `02_eda.ipynb` | Visualize trends, seasonality, decomposition, ACF/PACF |
| `03_stationarity.ipynb` | ADF & KPSS tests, compare 4 stationarity methods |
| `04_modeling.ipynb` | Auto-ARIMA, fit ARIMA + SARIMAX, export models |
| `05_evaluation_forecast.ipynb` | Compare models, MAPE/MAE/RMSE, 12-month future forecast |

---

## 📊 Results Summary

| Model | MAPE | MAE | RMSE |
|-------|------|-----|------|
| ARIMA(3,2,1) | ~125% | — | — |
| SARIMAX(2,2,0)×(1,1,0,12) | lower | — | — |

> SARIMAX outperforms ARIMA by capturing seasonal patterns (Q4 peaks each year).

---

## 🛠 Tech Stack

- Python 3.11
- pandas, numpy, matplotlib, seaborn
- statsmodels (ARIMA, SARIMAX, decomposition)
- pmdarima (auto_arima)
- scikit-learn (metrics)
