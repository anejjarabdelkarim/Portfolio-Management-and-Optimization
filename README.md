# 📈 Portfolio Management & Optimization

A Python-based study applying **Modern Portfolio Theory** to analyze asset returns and optimize a multi-asset portfolio using classical finance metrics.

---

## 📌 Overview

This notebook covers two main parts:

1. **Statistical Study — Prices vs. Returns**  
   A comparative analysis of the statistical properties of price and return series to determine which is more appropriate for portfolio management.

2. **Portfolio Optimization**  
   Construction of the efficient frontier and performance evaluation of a portfolio composed of four major stocks (Tesla, Apple, Netflix, Amazon) using CAPM-based metrics.

---

## 📂 Notebook Structure

### Part I — Statistical Study (TSLA, 2020)

| Step | Description |
|------|-------------|
| Data Import | Daily closing prices of Tesla (TSLA) over 2020 via `yfinance` |
| Log-Returns | Computation of daily log-returns: $\log(S_t / S_{t-1})$ |
| Descriptive Statistics | Summary statistics for both price and return series |
| Stationarity Test | Augmented Dickey-Fuller (ADF) test |
| Autocorrelation | ACF/PACF correlograms |
| Normality Test | Histogram visualization + Shapiro-Wilk test |

**Conclusion:** The returns series is stationary, exhibits no autocorrelation, and is more suitable for portfolio modeling than the price series.

---

### Part II — Portfolio Optimization (TSLA, AAPL, NFLX, AMZN — 2021)

| Step | Description |
|------|-------------|
| Data Import | Daily closing prices of 4 assets over 2021 |
| Return & Risk Functions | `portfolio_return()` and `portfolio_std()` |
| Efficient Frontier | Monte Carlo simulation of 8,000 random portfolios |
| Sharpe Ratio | Excess return per unit of total risk — identifies the market (tangency) portfolio on the CML |
| Treynor Ratio | Excess return per unit of systematic risk (β), using S&P 500 as benchmark |
| Jensen's Alpha | CAPM-adjusted excess return — measures over/under-performance vs. the benchmark |

---

## 🛠️ Requirements

```bash
pip install yfinance pandas numpy matplotlib statsmodels scipy
```

| Library | Usage |
|---------|-------|
| `yfinance` | Fetching historical stock data |
| `pandas` / `numpy` | Data manipulation and numerical computations |
| `matplotlib` | Visualization |
| `statsmodels` | ADF test, ACF/PACF plots |
| `scipy` | Shapiro-Wilk normality test |

---

## 🚀 Getting Started

```bash
git clone https://github.com/anejjarabdelkarim/portfolio-optimization.git
cd portfolio-optimization
pip install -r requirements.txt
jupyter notebook Portfolio_optimization_management.ipynb
```

---

## 📊 Key Results

- **Stationarity:** Price series → non-stationary | Return series → stationary (ADF test)
- **Autocorrelation:** Prices are autoregressive (up to lag 21); returns show no memory
- **Normality:** Both series reject normality (Shapiro-Wilk), consistent with financial stylized facts
- **Efficient Frontier:** 8,000 simulated portfolios plotted on the risk–return plane; minimum-variance portfolio identified
- **Performance:** All portfolios exhibit negative Jensen's Alpha relative to the S&P 500 benchmark, suggesting underperformance in 2021

---

## 📐 Key Formulas

**Sharpe Ratio:**
$$R_S = \frac{E(R_p) - r_f}{\sigma(R_p)}$$

**Treynor Ratio:**
$$R_T = \frac{E(R_p) - r_f}{\beta_p}$$

**Jensen's Alpha:**
$$\alpha_p = E(R_p) - \left[ r_f + \beta_p \left( E(R_M) - r_f \right) \right]$$

---

## 📄 License

This project is for educational purposes. Feel free to fork and adapt it.
