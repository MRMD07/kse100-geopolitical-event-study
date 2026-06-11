# KSE-100 Geopolitical Event Study: Quantifying Risk Premium and Mean Reversion

This repository contains an open-source quantitative time-series pipeline designed to isolate, measure, and analyze the market efficiency of the Karachi Stock Exchange (KSE-100) benchmark index during high-stakes geopolitical shifts. 

Specifically, this study models the structural market anomaly and capital flight tracking the regional diplomatic mediation timelines of April 2026.

---

## 📊 Project Overview

Traditional macroeconomic commentary frequently relies on retrospective, qualitative narratives to explain market fluctuations. This project introduces statistical objectivity to frontier market analysis by establishing an empirical data pipeline using **Python, Pandas, NumPy, and Matplotlib**. 

By calculating a historical baseline volatility threshold ($\sigma$), this architecture maps how institutional capital panics, de-risks, and stabilizes in response to weekend high-stakes diplomatic shocks.

---

## 🛠️ Key Features

* **Vectorized Data Cleaning:** Programmatic ingestion of historical index price files, stripping formatting anomalies, and ordering time-series data chronologically.
* **Statistical Anomaly Isolation:** Vectorized calculations of daily percentage returns and standard deviation channels without a single slow Python `for` loop.
* **Dual-Panel Dashboard Generation:** A professional, production-grade visualization system charting the index price alongside moving average baselines, while simultaneously tracking daily percentage return breaches against mathematical noise thresholds.

---

## 📐 Mathematical Framework

The data engine establishes daily asset percentage returns $R_t$ utilizing a vectorized price change formula:

$$R_t = \left( \frac{P_t - P_{t-1}}{P_{t-1}} \right) \times 100$$

Where $P_t$ represents the index closing point on trading day $t$.

To separate systemic geopolitical anomalies from ordinary background market chatter, the baseline historical volatility is calculated using the standard deviation ($\sigma$) of the return series across the tracking matrix:

$$\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(R_i - \bar{R})^2}$$

Where $N$ represents the total number of trading observations and $\bar{R}$ denotes the mean historical return.

---

## 📈 Empirical Findings & Results

The global data pipeline established a baseline daily market volatility threshold ($\sigma$) of **2.37%**. Statistically, any daily return swinging within the $[-2.37\%, +2.37\%]$ boundary represents standard background noise. 

When the event window surrounding the weekend diplomatic talks was unmasked, the market displayed an asymmetric, back-to-back structural breach of this noise channel:

| Trading Day ($t$) | Calendar Date | Closing Price (Points) | Daily Percentage Return ($R_t$) | Volatility Condition |
| :--- | :--- | :--- | :--- | :--- |
| $t-1$ | 2026-04-10 | 165,823.88 | $+1.01\%$ | Normal Noise Floor |
| **$t+1$ (Shock)** | **2026-04-13** | **159,211.95** | **$-3.95\%$** | **Systemic Breach ($>1.6\sigma$)** |
| $t+2$ (Reversion) | 2026-04-14 | 164,212.23 | $+3.14\%$ | Systemic Breach ($>1.3\sigma$) |
| $t+3$ | 2026-04-15 | 167,072.05 | $+1.74\%$ | Normal Noise Floor |

### The Theoretical Takeaway
The data demonstrates that institutional capital treated the mediation timeline strictly as a high-stakes volatility hurdle to clear and de-risk, rather than an organic growth catalyst for domestic industries. Because the sharp $+3.14\%$ recovery on Tuesday failed to kick off a sustained expansionary breakout above the 5-day Simple Moving Average (SMA) and instead moved sideways, the event is classified as a classic speculative **Mean Reversion** rather than a structural macroeconomic regime shift.

---

## 📁 Repository Structure

```text
├── data/
│   └── kse100_historical.csv        # Cleaned chronological time-series data
├── src/
│   └── market_event_study.py        # Core NumPy/Pandas processing & plotting script
├── output/
    └── kse100_geopolitical_analysis.png     # High-resolution generated dashboard export
├── README.md                        # Project documentation and whitepaper
└── requirements.txt                 # Project environment dependencies
