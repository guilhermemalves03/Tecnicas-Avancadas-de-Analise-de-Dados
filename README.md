# Advanced Techniques in Data Analysis

This repository contains practical projects developed for the **Advanced Techniques in Data Analysis** course. The work is divided into two main areas: Classical Statistical Analysis and Machine Learning applied to Financial Time Series.

**Authors:**
* Guilherme Alves
* Tomás Gonçalves
* Bárbara Baptista
* João Simões

---

## 1. Machine Learning Project: Stock Prediction & Algorithmic Trading (PayPal)

### 🎯 Objective
To explore the feasibility of predicting PayPal's (PYPL) stock direction and volatility using Deep Learning (LSTM) and Regression (SVR), and to develop a trading strategy focused on risk management.

### 🧠 Methodology
The project followed a rigorous Data Science pipeline:
1.  **Time Series Analysis:** Stationarity checks (ADF and KPSS tests) and autocorrelation analysis to validate data properties.
2.  **Feature Engineering:** Creation of technical indicators (RSI, MACD, Bollinger Bands) and realized volatility metrics.
3.  **Volatility Modeling (SVR):** Using *Support Vector Regression* to forecast market volatility.
4.  **Trend Classification (LSTM):** A Recurrent Neural Network to classify the next day's movement as "Up" (1) or "Down" (0).
5.  **Trading Strategy Development:** Implementation of a "Sniper Strategy" that combines the LSTM's directional predictions with the SVR's volatility forecasts to make trading decisions.

### 📊 Results and Critical Analysis
Unlike "black box" models that promise unrealistic returns, our analysis revealed the intrinsic difficulty of predicting efficient markets.

* **The Accuracy Challenge:** The LSTM model achieved a **Global Accuracy of ~48%**, statistically similar to a coin flip. This supports the *random walk* hypothesis in the short term.
* **The Value of Recall:** Despite low accuracy, we optimized the model to be sensitive to downturns, achieving an **80% Recall for the 'Down' class**.
    * *Insight:* The model rarely predicts "Up" correctly, but it is excellent at alerting when the stock will crash.
* **Trading Model Performance:**
    * We backtested a custom strategy against a Buy & Hold benchmark.
    * While it did not outperform Buy & Hold in total returns (due to transaction costs and missed upside), it successfully demonstrated potential as a **Risk Management Tool** (Hedging), avoiding significant drawdowns during bearish periods.

| Metric (Test Set) | Class 'Down' | Class 'Up' |
| :--- | :---: | :---: |
| **Precision** | 0.48 | 0.50 |
| **Recall** | **0.80** | 0.19 |
| **F1-Score** | 0.60 | 0.28 |

---

## 2. Statistics Project: Multivariate Analysis

### 🎯 Objective
Application of robust statistical methods to test hypotheses and reduce dimensionality in classic datasets (Iris Dataset and Student Performance).

### 🧪 Techniques Applied
* **MANOVA (Multivariate Analysis of Variance):** To test if there are statistically significant differences between flower species centroids considering all variables simultaneously.
* **PCA (Principal Component Analysis):** Dimensionality reduction to visualize data structure, demonstrating that most variance is explained by the first two principal components.
* **Multiple Linear Regression:** Analysis of factors influencing student performance.

---

## 🛠️ Technologies & Libraries
* **Language:** Python 3.x
* **Machine Learning/DL:** TensorFlow (Keras), Scikit-Learn, XGBoost.
* **Statistics:** SciPy, Statsmodels.
* **Visualization:** Matplotlib, Seaborn.
* **Data:** Yahoo Finance API (`yfinance`).

## ⚠️ Disclaimer
This project is for educational and academic purposes only. Nothing contained herein constitutes financial advice or investment recommendations.
