# Time Series Forecasting with the Box-Jenkins Method

Two forecasting exercises that follow the full **Box-Jenkins** workflow (identification → estimation → diagnostic checking → forecasting) with `statsmodels`.

`Python` · `statsmodels` · `pmdarima` · `scipy` · `pandas` · `matplotlib`

## 1. Identifying stochastic processes ([`01_simulated_series`](01_simulated_series/))

Six time series of unknown origin are each analysed to work out the generating process:

- descriptive statistics, skewness and kurtosis
- **ADF** test for stationarity and differencing where needed
- **ACF / PACF** to identify the AR / MA order
- **Ljung-Box** on the series and its squares (linear and non-linear dependence)
- **Shapiro-Wilk** for normality, to tell strict from weak white noise

One HTML report per series is in [`01_simulated_series/html/`](01_simulated_series/html/).

## 2. Forecasting Coca-Cola quarterly earnings ([`02_coca_cola_sarima`](02_coca_cola_sarima/))

A seasonal model for Coca-Cola's quarterly earnings:

- seasonal + regular differencing chosen with ADF tests and `pmdarima` recommendations
- final model **SARIMA(0,1,2)(0,1,1)₄**
- residual diagnostics: ADF, Ljung-Box, Shapiro-Wilk and a histogram
- out-of-sample test on the last 24 quarters: **MAPE 8.4%**
- alternatives compared in separate reports: log transform, seasonal-only differencing

## Run it

```bash
pip install pandas numpy statsmodels pmdarima scipy scikit-learn matplotlib seaborn
jupyter notebook
```

The Coca-Cola earnings CSV isn't included. Add `coca_cola_earnings.csv` (`;`-separated, `,` decimal) to `02_coca_cola_sarima/notebooks/` to re-run, or open the HTML exports to see the full results.

## Context

Group assignments for *Big Data & AI in Operations Management*.
