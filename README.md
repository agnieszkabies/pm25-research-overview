# PM2.5 Prediction Using Meteorological Data and Machine Learning

## Project Overview

This repository presents a research project focused on the analysis and prediction of PM2.5 air pollution concentrations using meteorological and environmental data combined with machine learning methods.

The project was developed as part of an undergraduate engineering thesis investigating relationships between atmospheric conditions and particulate matter variability, as well as evaluating the predictive performance of selected ML models.

Source code is not publicly available due to planned scientific publications.  
This repository documents methodology, research design, and results.

## Objectives

The main goals of the project were:

- analysis of temporal and spatial variability of PM2.5 concentrations,
- identification of relationships between air pollution and meteorological factors,
- feature engineering for environmental time-series data,
- comparison of machine learning models for PM2.5 prediction,
- evaluation of predictive performance using statistical metrics.

Dataset

The study used environmental data from 2023 collected from air quality monitoring stations located in Poland:

- **Silesian Voivodeship:** Katowice, Bielsko-Biała
- **Lublin Voivodeship:** Lublin, Zamość

### Data sources included:

- PM2.5 daily concentrations,
- gaseous pollutants: SO₂, NO₂, CO,
- meteorological variables:
  - air temperature,
  - relative humidity,
  - wind speed,
  - precipitation,
  - atmospheric pressure.

Data preprocessing included synchronization, cleaning, handling missing values, and temporal aggregation.

## Exploratory Data Analysis (EDA)

The analysis revealed:

- strong seasonal variability of PM2.5 concentrations,
- significantly higher pollution levels during the heating season,
- negative correlation with temperature and wind speed,
- co-occurrence patterns between PM2.5 and gaseous pollutants.

These findings confirmed the influence of atmospheric stagnation conditions on pollution accumulation.

## Feature Engineering

The following features were created:

- lag variables,
- temporal aggregates,
- seasonal indicators,
- time-based features,
- interaction-related environmental predictors.

Feature engineering significantly improved model performance.

## Machine Learning Models

The following algorithms were evaluated:

- Random Forest
- XGBoost
- LightGBM
- Support Vector Regression (SVR)
- Multilayer Perceptron (MLP)

Models based on ensemble decision trees achieved the highest predictive accuracy.

## Evaluation Metrics

Models were compared using:

- RMSE (Root Mean Square Error)
- MAE (Mean Absolute Error)
- R² score

Tree-based ensemble methods demonstrated superior performance in modeling nonlinear environmental relationships.

## Key Findings

- PM2.5 variability strongly depends on meteorological conditions.
- Heating season significantly increases pollution levels.
- Machine learning models effectively capture nonlinear dependencies.
- Ensemble methods outperform classical regression approaches.

The results indicate that ML-based models can support air quality monitoring and environmental decision-making systems.

## Research Context

This project contributes to environmental data science and demonstrates practical applications of machine learning in air quality modeling and environmental analytics.

Related scientific publications based on this research are currently under review.

## Tech Stack

- Python
- pandas, NumPy
- scikit-learn
- XGBoost, LightGBM
- matplotlib / data visualization
- environmental time-series analysis

## Author

Agnieszka Głowacka

Engineering thesis project in Data Science / Environmental Machine Learning.
