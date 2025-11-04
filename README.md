# 📈 Quantitative Momentum Strategy Backtesting

## Project Overview
This repository contains a comprehensive **quantitative finance project** that explores and rigorously backtests two advanced momentum-based equity trading strategies. The analysis is performed across two major global indices: the **S\&P 500 (US)** and the **STOXX 600 (Europe)**.

The primary goal is to determine whether modifying the classic cross-sectional momentum factor (CSM) using either **return skewness** or **Time-Series Momentum (TSM)** can yield superior risk-adjusted returns and improved portfolio stability. The entire project is implemented in Python, utilizing Jupyter notebooks for clear, reproducible analysis and visualization.

---

## 🛠️ Strategies Explored

### 1. Skewness-Enhanced Momentum
This strategy refines the standard momentum factor by introducing **return skewness** as a preliminary filter.

* **Hypothesis**: Stocks exhibiting strong recent momentum that also possess **positive return skewness** (a tendency toward rare, large positive returns rather than frequent small losses) will outperform standard momentum portfolios.
* **Methodology**: A double-screening process where stocks are first filtered for favorable skewness and then the top momentum performers from that filtered pool are selected.
* **Key Finding**: The strategy demonstrated compelling CAGR but faced significant maximum drawdowns, indicating a need for strong risk management.

### 2. Dual Momentum: Time-Series + Cross-Sectional (TSM + CSM)
This strategy combines two distinct momentum signals to create a robust filtering mechanism.

* **Time-Series Momentum (TSM)**: An absolute momentum filter used first, ensuring that individual stocks are in an **absolute positive trend** relative to their own past performance (or a risk-free rate). This acts as a protective measure to avoid allocating capital during broad market downturns (market-timing).
* **Cross-Sectional Momentum (CSM)**: The classic relative momentum factor, applied only to the pool of stocks that passed the TSM filter, selecting the best-performing assets among those trending positively.
* **Key Finding**: The TSM + CSM approach proved to be the **most robust strategy overall**, especially on the **STOXX 600** dataset, achieving the highest Sharpe Ratio and the lowest maximum drawdown.

---

## 📊 Performance Summary (Best Results)

The Dual Momentum (TSM+CSM) strategy demonstrated superior performance, particularly in the European market.

| Metric | Skewness-Enhanced (S\&P 500) | Dual Momentum (TSM+CSM) – S\&P 500 | Dual Momentum (TSM+CSM) – STOXX 600 |
| :--- | :--- | :--- | :--- |
| **Strategy CAGR** | 14.16% | 14.80% | **17.07%** |
| **Strategy Volatility** | 25.56% | 24.32% | **18.06%** |
| **Sharpe Ratio** | 55.37% | 60.86% | **94.55%** |
| **Max Drawdown** | -63.78% | -61.61% | **-48.71%** |

---

## 📁 Repository Structure

The project is structured into four main Jupyter notebooks, one for each strategy/market combination:

| File | Strategy | Market | Description |
| :--- | :--- | :--- | :--- |
| `1.S&P500.ipynb` | Skewness-Enhanced Momentum | S\&P 500 (US) | Implementation and backtest on US equity data. |
| `2.Stoxx600.ipynb` | Skewness-Enhanced Momentum | STOXX 600 (Europe) | Implementation and backtest on European equity data. |
| `3.S&P500(TM&CS).ipynb` | Dual Momentum (TSM + CSM) | S\&P 500 (US) | Implementation and backtest of the combined strategy on US data. |
| `4.Stoxx600(TM&CS).ipynb` | Dual Momentum (TSM + CSM) | STOXX 600 (Europe) | Implementation and backtest of the combined strategy on European data. **(Highest Sharpe)** |

---

