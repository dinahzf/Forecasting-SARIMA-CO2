# Time Series Forecasting of CO₂ Concentrations Using SARIMA

## Overview
This project analyzes and forecasts monthly atmospheric CO₂ concentration levels recorded at the Mauna Loa Observatory, Hawaii, using the Seasonal Autoregressive Integrated Moving Average (SARIMA) method. Atmospheric CO₂ is one of the most important indicators of global climate change, and the Mauna Loa record (collected continuously since 1958) is widely regarded as the benchmark dataset for tracking long-term greenhouse gas trends. The goal of this project is to build a statistically sound forecasting model that captures both the long-term upward trend and the recurring seasonal cycle present in the data.

## Objectives
- Analyze the monthly pattern of CO₂ concentration data and identify trend and seasonal components.
- Build candidate SARIMA models based on stationarity testing, ACF/PACF identification, and parameter significance testing.
- Select the best-performing model through residual diagnostics and out-of-sample error evaluation.
- Produce a one-step-ahead forecast for January 2024 based on the selected model.

## Dataset
- **Source:** National Oceanic and Atmospheric Administration (NOAA) Global Monitoring Laboratory (https://gml.noaa.gov/)
- **Period:** January 2010 – December 2023 (168 monthly observations)
- **Split:** 156 observations for training (2010–2022) and 12 observations for testing (2023)
- **Variable:** Monthly average CO₂ concentration (parts per million, ppm)

## Methodology
1. Descriptive statistics and time series visualization to understand the overall pattern.
2. Stationarity testing in variance (Box-Cox) and in mean (ACF/PACF inspection).
3. Regular differencing (d = 1) to remove the trend and seasonal differencing (D = 1, S = 12) to remove the annual cycle.
4. Model identification from ACF/PACF plots of the differenced series.
5. Parameter significance testing (Minitab, α = 0.05) across multiple candidate SARIMA orders.
6. Residual diagnostic checks: normality test and residual independence (white noise) test.
7. Model comparison using MAPE, MSE, MAD, and AIC on both training and testing data.
8. Forecast computation using the selected model's difference equation.

## Key Results
- Two candidate models passed all diagnostic assumptions: SARIMA(4,1,0)(0,1,1)₁₂ and SARIMA(4,1,0)(0,1,3)₁₂.
- SARIMA(4,1,0)(0,1,3)₁₂ was selected as the best model, with the lowest testing-data error: MAPE = 0.0672%, MSE = 0.0970, MAD = 0.2827.
- The forecasted CO₂ concentration for January 2024 was **422.72 ppm**, consistent with the observed long-term upward trend.

## Tools & Libraries
- Minitab (model identification, parameter estimation, diagnostic testing)
- Microsoft Excel (manual forecast calculation and data organization)

## Repository Contents
- `SARIMA-CO2.csv` — monthly CO₂ concentration data (2010–2023)
- `SARIMA-CO2.ipynb` — full analysis workflow (or equivalent statistical software output)
- `README.md` — this documentation

## Conclusion
This project demonstrates a complete time series forecasting workflow, from raw data collection through stationarity transformation, model identification, statistical validation, and final forecasting. The resulting SARIMA(4,1,0)(0,1,3)₁₂ model provides a reliable short-term forecast of CO₂ concentration and can serve as a foundation for further climate-related analytical work.
