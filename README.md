# Quantitative Risk Engine: Brent Crude Oil 🛢️

This project implements an asymmetric volatility forecasting engine using **GJR-GARCH** models to estimate dynamic **Value-at-Risk (VaR)** on Brent Crude Oil.

---

## 📋 Executive Summary

Energy markets are characterized by extreme volatility, fat tails, and asymmetric reactions to shocks (leverage effect). Traditional risk models often underestimate downside risk by assuming normal distributions and constant variance.

**Objective:** Build a Python-based engine to forecast daily volatility and validate a 99% VaR model for the *United States Brent Oil Fund (BNO)* over a 10-year horizon.

**Methodology:** The project compares standard GARCH approaches with asymmetric extensions (GJR-GARCH) to capture the leverage effect often observed in commodity markets.

---

## ⚙️ Methodology

### 1. Data Analysis & Stylized Facts
* **Data Source:** Yahoo Finance (Ticker: `BNO`), 10-year daily history.
* **Preprocessing:** Log-returns transformation to ensure stationarity.
* **Diagnostics:** Statistical testing for **Volatility Clustering** (Ljung-Box test) and **Heavy Tails** (Kurtosis analysis).

### 2. Econometric Modeling
We evaluate standard GARCH(1,1) against asymmetric extensions to find the best fit for oil price dynamics.
* **Models Tested:** GARCH, GJR-GARCH.
* **Distributions:** Normal vs. Student-t (to account for leptokurtosis).
* **Selection Criteria:** AIC/BIC information criteria and residual diagnostics.

### 3. Risk Management (VaR)
* **Metric:** Dynamic 99% Conditional Value-at-Risk (1-day horizon).
* **Validation:** The model is stress-tested using out-of-sample backtesting techniques, including the **Kupiec POF Test**, to verify that the frequency of losses exceeding the VaR is consistent with the confidence level.

---

## 📊 Expected Outcomes

The project aims to demonstrate:
1.  **Asymmetry:** Whether market crashes induce higher volatility than rallies (Leverage Effect).
2.  **Robustness:** The ability of the GJR-GARCH model to provide a more accurate safety buffer than Gaussian models during market stress.
3.  **Risk Calibration:** A breach rate close to the theoretical 1% target on out-of-sample data.


## 🤝 Contact

Open to feedback and collaboration opportunities! Feel free to reach out via https://www.linkedin.com/in/giannimarchetti/ or open an issue if you have questions about the methodology.
