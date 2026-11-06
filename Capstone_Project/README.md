# Market Regime Detection and Machine Learning-Driven Dynamic Asset Allocation

## Executive Summary

Financial markets move through periods of stability and stress, yet many investment portfolios maintain the same asset allocation regardless of changing market conditions. This project investigates whether machine learning can identify distinct market environments and support more effective portfolio allocation decisions.

Using feature engineering, Principal Component Analysis (PCA), K-Means clustering, and model validation techniques, two distinct market regimes were identified: a Normal Market Regime and a High-Volatility Regime. These regimes exhibited meaningful differences in risk, return, and asset behavior.

A regime-aware portfolio strategy was then developed by adjusting allocations based on the detected market environment. Compared to a traditional static portfolio, the regime-aware strategy increased annual returns from **10.95% to 14.63%** and improved the Sharpe Ratio from **0.91 to 1.25** while maintaining a similar risk profile.

The results suggest that machine learning-based market regime detection can provide actionable insights for portfolio management and improve risk-adjusted investment performance.

*Figure 1. Growth of $1 invested in the Static Portfolio versus the Regime-Aware Portfolio.*
<img width="1500" height="600" alt="PortfolioGrowthComparison" src="https://github.com/user-attachments/assets/11f59799-f6ff-4d82-b198-c9904d9c9d8d" />

---

## Business Problem

Most portfolio allocation strategies use fixed asset weights regardless of market conditions. While this approach simplifies portfolio management, it may fail to adapt during periods of elevated volatility and market stress.

This project explores whether machine learning-driven market regime detection can identify changing market conditions and support dynamic asset allocation decisions that improve portfolio outcomes.

### Research Question

**Can market regime detection and machine learning-driven dynamic asset allocation improve risk-adjusted portfolio performance compared to a traditional static asset allocation strategy?**

---

## Project Files

| File | Description |
|--------|-------------|
| `EDACapstoneProject.ipynb` | Exploratory Data Analysis (EDA), feature engineering, and baseline modeling |
| `ML_Driven_Dynamic_Asset_Allocation.ipynb` | Market regime detection, portfolio construction, backtesting, and evaluation |
| `README.md` | Project documentation and summary |

---

## Data and Methodology

### Data

The analysis uses six ETFs representing major asset classes:

- SPY (U.S. Equities)
- QQQ (Technology Equities)
- TLT (Treasury Bonds)
- GLD (Gold)
- VNQ (Real Estate)
- HYG (High Yield Bonds)

### Machine Learning Workflow

#### Feature Engineering

A total of 36 engineered features were created to capture market behavior, including:

- Momentum indicators
- Volatility measures
- Moving Average Ratios
- Drawdown metrics

#### Dimensionality Reduction

Principal Component Analysis (PCA) was applied to reduce dimensionality and remove redundancy among features.

- Original Features: 36
- Principal Components Retained: 11
- Variance Preserved: ~90%

#### Model Selection and Validation

K-Means clustering was used to identify market regimes.

Model selection included:

- Hyperparameter tuning using values of K from 2 to 10
- Elbow Method analysis
- Silhouette Score evaluation
- Alternative cluster configuration assessment

The final model selected **K = 2**, which achieved the highest silhouette score and produced the strongest cluster separation.

#### Model Explainability

A Random Forest feature importance analysis was performed to improve interpretability and identify the variables driving regime classification.

---

## Key Findings

### Market Regimes

- Two distinct market regimes were identified.
- The High-Volatility Regime represented approximately 16% of observations and exhibited nearly double the volatility of the Normal Market Regime.
- Drawdown, momentum, trend, and volatility indicators were the primary drivers of regime classification.

### Asset Performance

- Asset behavior varied significantly across market regimes.
- Gold (GLD) performed strongest during high-volatility environments.
- Real Estate (VNQ) experienced the largest performance deterioration during periods of market stress.
- Most assets generated stronger returns during normal market conditions.

### Portfolio Performance

| Metric | Static Portfolio | Regime-Aware Portfolio |
|----------|----------:|----------:|
| Annual Return | 10.95% | 14.63% |
| Annual Volatility | 11.99% | 11.74% |
| Sharpe Ratio | 0.91 | 1.25 |
| Maximum Drawdown | -26.17% | -26.77% |

The regime-aware portfolio outperformed the static benchmark across most evaluation metrics and delivered superior risk-adjusted returns.

---

## Recommendations

Based on the findings of this study:

- Incorporate market regime information into portfolio allocation decisions.
- Increase exposure to defensive assets during high-volatility environments.
- Monitor drawdown, momentum, and trend indicators as potential regime signals.
- Use regime-aware allocation frameworks alongside traditional strategic asset allocation approaches.

---

## Limitations and Future Work

This study was limited to six ETFs and did not incorporate transaction costs, taxes, or macroeconomic indicators. Future work could explore alternative regime detection methods, portfolio optimization techniques, and additional data sources to further enhance model performance and investment decision-making.

---

## Conclusion

This project demonstrates that machine learning techniques can identify meaningful changes in market behavior and support more adaptive portfolio allocation decisions. By combining feature engineering, PCA, hyperparameter tuning, clustering, model validation, and portfolio backtesting, a regime-aware investment framework was developed and evaluated.

The results indicate that incorporating market regime information into portfolio construction may improve both portfolio returns and risk-adjusted performance relative to a traditional static allocation approach.
