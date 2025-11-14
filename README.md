# Introduction to Quantitative Finance

> *"In theory, there is no difference between theory and practice. In practice, there is."*

A comprehensive educational notebook that introduces quantitative finance concepts through real market data analysis and strategy development.

## 📚 Overview

This notebook is part of the **Enode Quant Education Program**, designed for students, junior researchers, and aspiring quantitative analysts. It provides an end-to-end workflow for analyzing financial time series and developing trading strategies using Apple (AAPL) and Amazon (AMZN) as case studies.

## 🎯 What You'll Learn

### Core Concepts
- **Data Processing**: Working with OHLCV data and handling time series alignment
- **Return Calculations**: Understanding arithmetic vs logarithmic returns
- **Statistical Analysis**: Computing and interpreting the four moments of distributions
- **Volatility Measurement**: Rolling statistics and annualized volatility
- **Risk Metrics**: Value-at-Risk (VaR) estimation and limitations
- **Correlation Analysis**: Static and time-varying correlation structures
- **Spread Trading**: Construction and normalization of mean-reverting spreads
- **Strategy Development**: Building and backtesting a simple mean-reversion strategy

### Real-World Considerations
- **Fat Tails**: Why return distributions violate Gaussian assumptions
- **Regime Shifts**: How volatility and correlation change over time
- **Execution Risk**: Gap risk, slippage, and transaction costs
- **Signal Decay**: Why theoretical edges diminish in practice

## 📊 Notebook Structure

### 1. Data Loading and Preparation
- Fetching OHLCV data from PostgreSQL database
- Timezone-aware datetime handling
- Date alignment across multiple assets
- Common trading calendar construction

### 2. Return Analysis
- Arithmetic returns: $r_t = (P_t / P_{t-1}) - 1$
- Log returns: $r_t = ln(P_t) - ln(P_{t-1})$
- Comparison of statistical properties

### 3. Exploratory Data Analysis
- Price series visualization
- Return distribution analysis
- Volatility clustering identification
- Outlier detection

### 4. Statistical Moments
- Mean (expected return)
- Variance (dispersion)
- Skewness (asymmetry)
- Kurtosis (tail heaviness)
- QQ-plots and normality testing

### 5. Volatility Analysis
- Rolling 20-day volatility
- Rolling 60-day volatility
- Annualization using √252 factor
- Regime identification

### 6. Value-at-Risk (VaR)
- Parametric (Gaussian) VaR computation
- 95% confidence level estimation
- Discussion of model limitations

### 7. Correlation Analysis
- Static correlation coefficients
- 60-day rolling correlation
- Time-varying co-movement patterns

### 8. Spread Construction
- Linear spread: $s_t = AAPL_t - β·AMZN_t$
- Beta estimation via regression
- Mean-reversion properties

### 9. Z-Score Normalization
- Rolling mean and standard deviation
- Z-score computation: $z_t = (s_t - μ_{60d}) / σ_{60d}$
- Overbought/oversold identification

### 10. Mean-Reversion Strategy
**Entry Rules:**
- Short when z > +1
- Long when z < -1

**Exit Rules:**
- Close when z returns to 0

**Execution Model:**
- Next-day open execution
- Slippage costs
- Transaction costs
- Gap risk simulation

### 11. Performance Evaluation
- Strategy returns calculation
- Turnover analysis
- Cost-adjusted performance
- Theoretical vs realized edge

## 🔑 Key Insights

### Why Naive Approaches Fail
1. **Non-Normal Returns**: Real distributions have fat tails and negative skew
2. **Unstable Parameters**: Volatility and correlation are regime-dependent
3. **Execution Costs**: Slippage and gaps erode theoretical profits
4. **Signal Decay**: Statistical relationships weaken over time

### Mathematical Foundations
- Logarithmic transformations
- Z-score standardization
- Rolling window statistics
- Linear regression
- Hypothesis testing

## 🚀 Intended Audience

This notebook is ideal for:
- Quantitative finance students
- Members of student-run quant funds
- Junior researchers and analysts
- Anyone learning statistical arbitrage
- Aspiring quantitative traders

## 📈 Extensions and Next Steps

The notebook prepares you for advanced topics:
- **Cointegration Testing**: Engle-Granger and Johansen methods
- **GARCH Models**: Time-varying volatility forecasting
- **Stochastic Volatility**: More sophisticated vol models
- **Real-Time Execution**: Order book dynamics and market microstructure
- **Portfolio Optimization**: Multi-asset strategies
- **Risk Management**: Position sizing and drawdown control

## 🛠️ Technical Requirements

- **Data Source**: Enode AWS RDS PostgreSQL database
- **Python Libraries**: pandas, numpy, matplotlib, scipy, statsmodels
- **Time Period**: Covers full overlapping trading history of AAPL and AMZN
- **Frequency**: Daily OHLCV data

## ⚠️ Important Notes

- This is an **educational tool**, not production-ready code
- Real trading requires more sophisticated risk management
- Past performance does not guarantee future results
- Always paper trade before deploying capital

## 🎓 Learning Outcomes

By completing this notebook, you will:
1. Understand how quantitative analysts think about markets
2. Know how to properly analyze financial time series
3. Recognize common pitfalls in strategy development
4. Appreciate the gap between theory and practice
5. Build a foundation for advanced quantitative research

---

**Part of the Enode Quant Education Program**
*Building the next generation of quantitative researchers*
