# Methodology

This document describes the end-to-end methodology used in the PM2.5 prediction project, including data acquisition, preprocessing, feature engineering, modeling, and evaluation strategy.

The study is based on the engineering thesis:
"Analysis and prediction of PM2.5 concentrations considering meteorological conditions and gaseous emissions using machine learning" (2026).

---

## 1. Study Area and Data Sources

### Study Regions

The analysis covers two Polish voivodeships:

- **Silesian Voivodeship** (Katowice, Bielsko-Biała)
- **Lublin Voivodeship** (Lublin, Zamość)

These regions differ in:

- Level of urbanization
- Industrial activity
- Emission structure
- Meteorological conditions

### Air Quality Data

Source: Polish State Environmental Monitoring (GIOŚ)

Variables:

- PM2.5 (daily averages)
- SO₂
- NO₂
- CO

Time range:

- Full year 2023

### Meteorological Data

Source: Meteostat (based on station geolocation)

Variables:

- Air temperature
- Relative humidity
- Dew point
- Wind speed
- Precipitation
- Atmospheric pressure

---

## 2. Data Preprocessing

### Data Synchronization

- Alignment of air quality and meteorological datasets by date
- Conversion to daily time resolution

### Missing Values

- Data completeness check performed
- Short gaps filled using linear interpolation
- Interpolation applied only for small consecutive missing segments

### Seasonal Segmentation

Data divided into:

- Heating season
- Non-heating season

This division reflects strong seasonal emission differences in Poland.

---

## 3. Exploratory Data Analysis (EDA)

The exploratory analysis focused on:

- Seasonal variability of PM2.5
- Daily concentration patterns
- Regional differences between voivodeships
- Correlation matrices (PM2.5 vs gaseous pollutants vs meteorological parameters)

Key findings:

- Higher PM2.5 concentrations during heating season
- Strong relationship with temperature and wind speed
- Regional variability driven by emission structure

---

## 4. Feature Engineering

Feature engineering focused on capturing temporal dependencies and atmospheric processes.

### 4.1 Time-Series Features

- Lag variables (previous-day values)
- Multi-day lag structures
- Rolling averages (moving means)

### 4.2 Seasonal Indicators

- Binary heating-season flag
- Winter vs non-winter distinction

### 4.3 Atmospheric Interaction Features

- Interactions between meteorological variables and gaseous pollutants
- Indicators of stagnation and ventilation conditions

### 4.4 Post-Feature Handling

- Removal of rows affected by lag-induced missing values
- Final feature matrix preparation for modeling

---

## 5. Modeling Approach

Multiple regression-based machine learning models were implemented and compared.

### Tree-Based Ensemble Models

- Random Forest
- XGBoost
- LightGBM

### Kernel-Based Model

- Support Vector Regression (SVR)

### Neural Network

- Multilayer Perceptron (MLP)

Models were trained using supervised learning for regression tasks.

---

## 6. Model Evaluation

Evaluation strategy included:

- Train/Test split
- K-Fold Cross-Validation
- Performance comparison across models

### Metrics Used

- RMSE (Root Mean Square Error)
- MAE (Mean Absolute Error)
- R² score

Tree-based ensemble models achieved the highest predictive performance.

---

## 7. Short-Term Forecasting

In addition to point prediction, short-term forecasting horizons were tested to assess model stability over time.

---

## 8. Reproducibility

- All analyses performed in Python
- Core libraries: pandas, NumPy, scikit-learn, XGBoost, LightGBM
- Structured pipeline for preprocessing and modeling
