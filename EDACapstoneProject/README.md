# Market Regime Detection and ML-Driven Dynamic Asset Allocation
### Overview

Traditional portfolio allocation approaches often rely on historical relationships between asset classes and may not adapt effectively to changing market conditions. This project investigates whether machine learning techniques can be used to identify market regimes and support dynamic asset allocation decisions.

Jupyter Notebook : https://github.com/ajaysisodia-Apps/AjayMLAI/blob/main/EDACapstoneProject/EDA-CapstoneProject.ipynb

### Research Question

Can market regime detection and machine learning techniques improve dynamic asset allocation compared to traditional static portfolio allocation approaches?

### Dataset

The analysis uses daily adjusted closing prices from the following ETFs:

- SPY (U.S. Equities)
- QQQ (Technology Equities)
- TLT (Treasury Bonds)
- GLD (Gold)
- VNQ (Real Estate)
- HYG (High Yield Bonds)

The dataset spans January 2015 through October 2026 and contains approximately 2,973 daily observations.

## Methodology
### Exploratory Data Analysis (EDA)

The following analyses were performed:

- Data quality assessment and missing value analysis
- Price trend analysis
- Normalized performance comparison
- Return statistics and risk-return analysis
- Correlation analysis
- Rolling volatility analysis
- Drawdown analysis
- Return distribution analysis

### Feature Engineering

The following features were created:

- 20-Day Momentum
- 50-Day Momentum
- 20-Day Volatility
- 50-Day Volatility
- Moving Average Ratio (20-Day / 50-Day)
- Drawdown

A total of 36 engineered features were generated.

### Baseline Model

A Random Forest Classifier was developed to predict future volatility regimes:

High Volatility Regime = 1
Low Volatility Regime = 0

This model serves as a baseline benchmark for future model development.

## Results

Key findings from the exploratory analysis include:

- QQQ generated the highest returns but also exhibited the greatest volatility.
- TLT experienced the deepest and most persistent drawdown during the study period.
- GLD demonstrated relatively low correlations with other asset classes, providing diversification benefits.
- Rolling volatility and drawdown patterns revealed evidence of distinct market environments.

The baseline Random Forest model achieved an accuracy of 50.6%, indicating limited predictive power but establishing a benchmark for comparison with more advanced models.
Future Work

## Conclusion and Future Work :
This exploratory data analysis provided a comprehensive examination of a multi-asset ETF dataset and revealed meaningful differences in return, risk, correlation, volatility, and drawdown characteristics across asset classes. The analysis identified distinct periods of market stress and stability, suggesting that asset behavior varies under changing market conditions and supporting the research question's focus on dynamic asset allocation. Feature engineering was performed to create momentum, volatility, trend, and drawdown indicators, resulting in a set of predictive variables for machine learning analysis.

As an initial benchmark, a Random Forest classifier was developed to predict future volatility regimes. The model achieved an accuracy of 50.6%, establishing a baseline for future comparison. While the predictive performance was limited, the results provide a foundation for subsequent modeling efforts. Future work will focus on applying market regime detection techniques, evaluating additional machine learning models, and refining the feature set to determine whether regime-aware portfolio allocation strategies can improve risk-adjusted investment outcomes relative to traditional static approaches.

Next steps :
- Market regime detection using clustering techniques
- Dimensionality reduction methods such as PCA
- Advanced machine learning model development and optimization
- Dynamic asset allocation strategies informed by detected market regimes
- Comparison of regime-aware portfolios against traditional allocation approaches
