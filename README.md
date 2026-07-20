# Time Series Analysis: Modeling Stock Return Volatility for ADX and BAX Markets (2018–2023)

## 1.  Executive Summary
This repository contains two projects dedicated to modeling and analyzing the conditional volatility of stock returns for the Abu Dhabi Securities Exchange (**ADX**) and the Buenos Aires Stock Exchange (**BAX**). The analysis covers the period from January 2, 2018, to December 31, 2023, utilizing daily log returns calculated from historical market data. 

To capture complex financial phenomena, a suite of advanced conditional heteroskedasticity models was deployed, including **GARCH**, **EGARCH**, and **TGARCH**. Based on strict information criteria and rigorous diagnostic testing, the **EGARCH** model emerged as the most efficient and robust framework for both markets. The model demonstrated high statistical significance across all core structural parameters and successfully captured the **Leverage Effect**, revealing that negative market shocks (bad news) exert a significantly stronger impact on conditional variance than positive shocks of equal magnitude.

>  **Methodological Note:** Instead of focusing on standard directional price forecasting, these projects emphasize **structural, diagnostic, and explanatory analysis**. The core objective is to map out the mathematical components of market risk, test variance stability, and understand the long-memory properties of volatility clusters during periods of macroeconomic stress.
> 
> **Additionally,** a baseline ARIMA model was initially fitted to evaluate the mean process, and its residuals were tested using the ARCH-LM test to confirm significant heteroskedasticity. Following the failure of ARIMA to handle volatility dynamics, standalone GARCH, EGARCH, and TGARCH models were applied directly to the daily returns.

---

## 2.  Methodology & Econometric Diagnostics
To ensure a mathematically sound interpretation of the historical time series, a rigorous, sequential econometric pipeline was implemented:

*  **Data Integrity:** The dataset was audited and cleaned to eliminate any missing values across all core trading metrics (*Open, High, Low, Close, Adjusted Close, and Volume*), ensuring a continuous, gap-free chronological sequence.
*  **Stationarity Testing:** The Augmented Dickey-Fuller (**ADF**) test was applied to determine whether historical price levels were stationary or followed a non-stationary random walk requiring first-differencing (transformation into log returns).
*  **Autocorrelation Analysis:** Autocorrelation Function (**ACF**) and Partial Autocorrelation Function (**PACF**) plots were generated to map the memory of the series and identify the optimal lag structures for the mean model.
*  **Residual & Variance Diagnostics:**
  * The **Ljung-Box** test was executed on both standardized residuals and their squared values to confirm that all systematic information was successfully extracted, transforming the residuals into independent white noise.
  * The **ARCH-LM** test was applied to evaluate homoscedasticity, ensuring that the final conditional volatility model left no remaining ARCH effects.

---

## 3.  Key Empirical Findings & Financial Impact
* **Non-Stationarity of Raw Prices:** The ADF test confirmed that historical raw stock prices were non-stationary $I(1)$, reflecting the permanent nature of structural shocks on price levels. Conversely, the log returns exhibited complete stationarity at the $I(0)$ level.
* **Presence of Volatility Clustering:** The ARCH-LM test on the mean model's residuals statistically confirmed conditional heteroskedasticity. It successfully mapped historical phases of high-risk and intense market turbulence between 2018 and 2023, justifying the transition to the GARCH framework.
* **Structural Superiority of EGARCH:** The empirical evidence highlighted the superiority of the exponential, log-linear formulation of the EGARCH model. It provided fully significant parameters capable of accommodating non-linear dynamics and sharp market jumps far better than standard linear GARCH models.

 **Conclusion:** This empirical framework translates complex, chaotic market movements into precise, quantifiable metrics. It provides risk managers and financial analysts with a robust mathematical toolset to understand stock behavior and calculate Value-at-Risk (VaR) under realistic heavy-tailed distributions (e.g., Student's t-distribution).

---

##  Tech Stack & Software Environments
The modeling, diagnostic testing, and baseline comparisons were executed using the following programming environments:
* **Python** (`Pandas`, `Statsmodels`, `Arch Library`, `pmdarima`, `Matplotlib`, `SciPy`)
