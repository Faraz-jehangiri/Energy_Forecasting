<div align="center">

# ⚡ Energy Consumption Forecasting
### Time Series Analysis · ARIMA · Prophet · XGBoost

<br>

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=for-the-badge&logo=xgboost&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

<br>

> *"Energy doesn't lie — patterns in consumption tell a story the present can't yet see."*

<br>

</div>

---

## 📌 Objective

Forecast **short-term household energy consumption** using historical time-based patterns. Three models — **ARIMA**, **Facebook Prophet**, and **XGBoost** — are compared head-to-head on a 7-day forecasting horizon using MAE and RMSE as evaluation metrics.

This project is part of the **DevelopersHub Corporation — Data Science & Analytics Advanced Internship (Task 3)**.

---

## 📂 Dataset

| Property | Detail |
|----------|--------|
| **Name** | Individual Household Electric Power Consumption |
| **Source** | [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption) |
| **Size** | ~2 million minute-level records |
| **Period** | December 2006 — November 2010 |
| **Target** | `Global_active_power` (kilowatts) |

> ⚠️ Dataset not included in this repo due to GitHub's 100MB file size limit.  
> Download it from the UCI link above and place `household_power_consumption.txt` in the root directory before running the notebook.

---

## 🧠 Approach

```
Raw Minute-Level Data (~2M rows)
   │
   ▼
Parsing & Cleaning
   │  ├── Handle missing values ('?')
   │  └── Parse datetime index
   │
   ▼
Resample to Hourly Averages
   │
   ▼
Exploratory Data Analysis
   │  ├── Hourly consumption trends
   │  ├── Day-of-week patterns
   │  └── ACF / PACF plots
   │
   ▼
Feature Engineering (for XGBoost)
   │  ├── Hour, day, month, quarter
   │  ├── Weekday / weekend flag
   │  └── Lag features (1h, 24h, 168h) + rolling stats
   │
   ▼
Model Training (last 7 days = test set)
   │  ├── ARIMA (2, 0, 2)
   │  ├── Facebook Prophet
   │  └── XGBoost Regressor
   │
   ▼
Evaluation: MAE · RMSE · Actual vs Forecast Plots
```

---

## 📊 Results

| Model | MAE (kW) | RMSE (kW) |
|-------|----------|-----------|
| ARIMA | ~0.45 | ~0.58 |
| Prophet | ~0.38 | ~0.49 |
| **XGBoost** | **~0.29** | **~0.38** |

> 🏆 **XGBoost** outperforms both traditional models by leveraging lag features and temporal patterns.

*Note: Exact values may vary slightly depending on your environment and library versions.*

---

## 🔍 Key Findings

- Peak energy usage consistently occurs between **6 PM – 9 PM**
- **Weekdays** show more predictable consumption patterns than weekends
- **XGBoost with lag features** captures short-term dependencies better than ARIMA or Prophet alone
- Prophet excels at decomposing **daily and weekly seasonality** visually

---

## 📁 Repository Structure

```
Energy_Forecasting/
│
├── Task3_Energy_Forecasting.ipynb      # Full notebook with code, plots & insights
├── .gitignore                          # Excludes large dataset file
└── README.md                           # You are here
```

---

## ⚙️ Installation & Usage

```bash
# 1. Clone the repository
git clone https://github.com/Faraz-jehangiri/Energy_Forecasting.git
cd Energy_Forecasting

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn statsmodels prophet xgboost scikit-learn

# 3. Download the dataset from UCI and place it here:
#    household_power_consumption.txt → root of this folder

# 4. Launch the notebook
jupyter notebook Task3_Energy_Forecasting.ipynb
```

---

## 🛠️ Tech Stack

- **Python 3.10+**
- **Pandas & NumPy** — data manipulation & resampling
- **Matplotlib & Seaborn** — visualizations
- **Statsmodels** — ARIMA modelling
- **Prophet** — Facebook's time series forecasting
- **XGBoost** — gradient boosting with engineered features
- **Scikit-learn** — MAE, RMSE evaluation metrics

---

## 👤 Author

**Faraz Jehangiri**
Data Science Intern @ DevelopersHub Corporation
BS Computer Science — SSUET, Karachi

[![GitHub](https://img.shields.io/badge/GitHub-Faraz--jehangiri-181717?style=flat-square&logo=github)](https://github.com/Faraz-jehangiri)

---

<div align="center">
<sub>DevelopersHub Corporation · Data Science & Analytics Internship · Task 3</sub>
</div>
