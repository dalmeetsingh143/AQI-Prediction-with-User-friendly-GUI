# AQI Prediction Tool with User Alerts

A machine learning tool that forecasts Air Quality Index (AQI) and individual pollutant levels for Chennai, India using SARIMAX time series models. Includes a power plant impact simulator and a tkinter-based GUI for date-based forecasting.

Over 5000 lives are taken daily because of
illnesses related to pollution and continues to be an
important issue worldwide. Air pollution is considered a
major problem in some cities such as Dammam, Lahore,
Delhi. This study uses machine learning techniques, with a
focus on ARIMAX, Auto-ARIMA, SARIMAX to predict
air pollution using advances in information and computing
technology. The datasets used here contain daily pollutant
data such as Particle matter 2.5 (PM2.5), Particle Matter
10(PM10), Ozone 3(O3), Carbon Monoxide (CO), Sulfur
Dioxide (SO2), and Nitrogen Dioxide (NO2) for predicting
the air quality predictions of overall India and a particular
city. During data analysis the dataset showed a clear
seasonality and trend during some months. Assuming
evaluating models like ARIMA, Auto-ARIMA,
SARIMAX, the project concluded that SARIMAX is the
best model. Statistical calculations like Root mean square
error (RMSE) and mean absolute error (MAE) are used to
check the SARIMAX’S prediction accuracy. Beyond AQI
prediction, the group introduced an additional assignment
that examines the possible impacts of pollution when an
industry, power plants and factory is established in a
particular city or all over India. The study promises to
provide a complete understanding about the environmental
and health effects by increasing the scope to include the
effects of industries. Using the user-friendly Tkinter
interface helps accessibility when showing AQI forecasts
and recommendations

---

## Overview

| Detail | Value |
|---|---|
| Dataset | India AQI 2015–2020 (CPCB — cpcb.nic.in) |
| City focus | Chennai |
| Model | SARIMAX (Seasonal ARIMA with Exogenous variables) |
| Forecast horizon | Up to December 2025 |
| Language | Python 3 |
| Interface | tkinter GUI |

---

## What it does

**Prediction tool** — Enter any date (YYYY-MM-DD) and get forecasted values for AQI, PM2.5, PM10, O3, SO2, NO2, and CO, along with health-based recommendations.

**Power plant impact simulator** — Applies EU 2030 power plant emission guidelines to the predicted pollutant levels and shows how adding a plant to the city would shift the AQI.

**AQI calculator** — Enter raw pollutant concentrations and calculate AQI per India's national standards.

---

## Models and Results

Individual SARIMAX models trained per pollutant on monthly-averaged Chennai data (80/20 train/test split).

| Model | RMSE |
|---|---|
| AQI | 20.06 |
| PM10 | 19.02 |
| PM2.5 | 12.98 |
| NO2 | 5.15 |
| SO2 | 5.15 |
| O3 | 3.37 |
| CO | 1.77 |

Models saved as `.pkl` files and loaded at runtime.

---

## Installation

```bash
git clone https://github.com//.git
cd 

pip install -r requirements.txt
```

**Key dependencies:** `statsmodels`, `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `pickle`, `tkinter`

---

## Usage

**Forecasting + power plant impact GUI:**
```bash
python aqi_forecast_gui.py
```
Enter a date in `YYYY-MM-DD` format. Results show predicted pollutant levels and modified levels if a power plant is added.

**AQI calculator GUI:**
```bash
python aqi_calculator_gui.py
```
Enter raw pollutant concentrations to calculate the AQI rating per Indian standards.

---

## Data

Source: Central Pollution Control Board India (cpcb.nic.in) — India AQI dataset 2015–2020, 628,458 instances across major Indian cities.

Preprocessing steps: daily-to-monthly resampling, backward fill for missing values, city filtering (Chennai), feature selection (City, Date, AQI, pollutant columns).

---

## AQI Categories (India standard)

| AQI Range | Category |
|---|---|
| 0–50 | Good |
| 51–100 | Satisfactory |
| 101–200 | Moderate |
| 201–300 | Poor |
| 301–400 | Very Poor |
| 401–500 | Severe |

---

## Academic Context

Case Study — Intelligent Systems  
Technische Hochschule Deggendorf | January 2024

