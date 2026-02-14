# 🤖 ML-Driven Cryptocurrency Trading System

> **Portfolio Demonstration** | Built by Sineshaw Tesfaye  
> BS in Computer Science | Georgia State University  
> Contact: steswfaye4@student.gsu.edu

[![License](https://img.shields.io/badge/License-Custom%20Source%20Available-red.svg)](LICENSE)  
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)  
[![Machine Learning](https://img.shields.io/badge/ML-Ensemble%20Stacking-green.svg)](docs/ml_pipeline.md)

---

## ⚠️ Important Notice

**This repository is for portfolio demonstration purposes only.**

The core trading algorithms, production code, and proprietary risk management systems are **not included** in this public repository. Full codebase available to potential employers upon request during technical interviews.

See [LICENSE](LICENSE) for usage terms.

---

## 🎯 Project Overview

Advanced machine learning trading platform that combines quantitative finance, real-time data processing, and ensemble modeling to achieve **86% of cryptocurrency symbols with F1-score ≥ 0.90**.

### Key Achievements
- 🎯 **Mean BUY F1-score: 0.949** (median: 0.978)
- ⚡ **Sub-second trade execution** via Coinbase Advanced Trade API
- 📊 **Real-time processing** of 10+ WebSocket price feeds (<1s latency)
- 🔄 **Automated model retraining** every hour with walk-forward validation
- 🛡️ **Dynamic risk management** using GARCH volatility modeling

---

## 📸 System Screenshots

### Live Trading Dashboard
*Real-time portfolio monitoring with P&L tracking, position management, and trade history*
- Portfolio Value: **$516.10**
- Total P&L: **$22.98**
- Open Positions: **31 active trades**
- Features: Avoid Trading detection, risk categorization, emergency stop button

### ML-Driven Trading Chart
*Live BTC-USD chart with ML analysis showing 100% BUY confidence*
- Current Price: **$69,812.01** (+$926.13, +1.33%)
- ML Signal: **BUY** with **100% confidence**
- Position Recommendation: 0.286501 BTC
- R/R Ratio: **3.00**
- Take Profit: **$71,902.01**
- Stop Loss: **$69,109.70**
- Kelly Fraction: **25.0%**

### ML Model Management
*Model training interface, ensemble performance comparison, and feature importance analysis*
- **Model Evaluations**:
  - AB-USD: **80.0%** accuracy
  - ACX-USD: **100.0%** accuracy
  - 00-USD: **91.1%** accuracy
  - AAVE-USD: **94.4%** accuracy

- **Ensemble Comparison**:
  - Random Forest: MAE 676.9157, RMSE 6763.0636, **67.5%** hit rate, IC 0.9672
  - XGBoost: MAE 1417.4939, RMSE 1474.1181, **73.5%** hit rate, IC 0.9729
  - SVR: MAE 1419.3029, RMSE 1427.0962, **48.8%** hit rate, IC 0.5615
  - Meta-Learner (Ridge): MAE 10131.2217, RMSE 10183.9956, **44.0%** hit rate, IC 0.8134

- **Meta Weights Distribution**: RF 63.5%, XGB -0.043%, SVR 34%

- **Advanced Diagnostics**:
  - Drift Severity: **red** (feature distribution drift detected)
  - Max PSI: 0.0000, Mean PSI: 0.0000
  - CPCV: 57.1% PRO, 15 CV Paths, Mean OOS Score: -1802.3683, WFO Efficiency: 53.989
  - SHAP Feature Importance analysis available

### Risk Analytics Dashboard
*Comprehensive risk metrics including VaR, CVaR, drawdown analysis, and position sizing*
- **VaR & Tail Risk (BTC-USD)**:
  - VaR (95%): **-4.56%**
  - CVaR (95%): **-7.13%**
  - Observations: 89
  - Tail Risk Statistics: Skewness -0.3505 (unfavorable return tail)

- **VaR Model Validation (Kupiec POF)**:
  - Basel Traffic Light: **RED**
  - Breaches: 4 / 1.5 expected
  - Kupiec LR: 3.073
  - p-value: **0.0796** (model adequate)

- **Drawdown Analysis**:
  - Max Drawdown: **-35.24%**
  - Avg Drawdown: **-8.96%**
  - Current Drawdown: **-27.97%**
  - Calmar Ratio: **-2.838**
  - Time underwater: 33.3% (Duration: 6 days)

- **Position Sizing Recommendations**:
  - Recommended Size: **0.28645083 BTC**
  - Max Size: **0.01432254 BTC**
  - Risk Per Trade: **2.0%**
  - Kelly Fraction: **25.0%**
  - R/R Ratio: **3.00**

- **TP/SL Analysis**:
  - Current Price: $69,812.00
  - Take Profit: $71,902.01 (Target)
  - Stop Loss: $69,109.70
  - Factor Breakdown: 
    - tc_percentage: 3.0000
    - sl_percentage: 1.5000
    - reward_risk_ratio: 2.0000
    - confidence_score: 0.5740

### Quantitative Backtesting
*Professional-grade backtesting with walk-forward validation, Monte Carlo simulation, and rolling performance analysis*
- **Configuration**:
  - Symbols: BTC-USD, ETH-USD, SOL-USD, DOGE-USD
  - Strategy: **ML Auto-Trading** (Full ML pipeline with momentum scan + stacking ensemble + TP/SL)
  - Date Range: 06/14/2025 - 02/13/2026
  - Initial Capital: **$10,000**
  - Max Positions: **3**

- **Features**:
  - Live Performance Metrics (fetch from live trading database)
  - Monte Carlo Simulation
  - Rolling Performance Ratios
  - Trade Analytics

### Technical Analysis & Auto-Trading
*Automated trading system with opportunity detection, confidence thresholds, and execution tracking*
- **Strategic Auto-Trader**: 
  - Status: **Running** (Green indicator)
  - Running Since: Feb 14, 02:14 PM
  - Opportunities: 0 detected
  - Trades Executed: 0
  - Total Savings: +$0.00

- **Configuration**:
  - Scan Interval: 0s
  - Investment Range: $0 - $0
  - Min Confidence: NaN%

- **Analyze Opportunity**:
  - Symbol: BTC-USD
  - Investment: $100
  - Analyze button for technical analysis

### Futures Trading Interface
*Perpetual futures trading with leverage control (1x-10x), risk categorization, and position management*
- **Futures Overview**:
  - Active Positions: **0**
  - Unrealized P&L: **+$0.00**
  - Risk Summary: Low: 0, Medium: 0, High: 0, Critical: 0

- **Available Perpetual Contracts**:
  - BTC-PERP: **0.4557%** funding rate
  - ETH-PERP: **0.7701%** funding rate
  - SOL-PERP: **-0.5145%** funding rate
  - AVAX-PERP: **0.1694%** funding rate

- **Execute Trade**:
  - Symbol: BTC-PERP-INTX
  - Side: Long / Short toggle
  - Investment: $100
  - Leverage slider: 1x - 10x (currently 1x)
  - Get Optimal Leverage button
  - Execute LONG Trade button

- **Opportunities**: No opportunities detected

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Flask Dashboard (Port 8052)               │
│                     HTTP API + Web UI                        │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                   Core Trading Engine                        │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │ Data Fetcher │  │  ML Pipeline  │  │Trading Engine│      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │Risk Manager  │  │  Portfolio DB │  │  WebSocket   │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              Coinbase Advanced Trade API                     │
│        Real-time Prices | Order Execution | Account Data    │
└─────────────────────────────────────────────────────────────┘
```

**[View detailed architecture →](docs/architecture.md)**

---

## 🧠 Machine Learning Pipeline

### Ensemble Architecture
```
Base Learners:
├── Random Forest Regressor (67.5% hit rate, feature importance)
├── XGBoost Regressor (73.5% hit rate, gradient boosting)
└── Support Vector Regressor (48.8% hit rate, non-linear patterns)
         │
         ▼
Ridge Meta-Learner (44.0% hit rate, optimal weighting: RF 63.5%, XGB -0.043%, SVR 34%)
```

### Feature Engineering
- **35+ WorldQuant-style alpha factors**
- Price momentum, volatility, cross-sectional ranking
- Kalman filtering for signal denoising
- Wavelet transforms for multi-scale analysis
- PCA-based factor extraction
- SHAP values for model interpretability

### Advanced ML Diagnostics
- **Model Health Monitoring**: Drift severity detection, PSI/threshold tracking
- **Cross-validation**: 15 CV paths, 57.1% PRO score, moderate overfitting risk
- **Ensemble Comparison**: MAE, RMSE, Hit Rate, and IC metrics for each model
- **Feature Importance**: SHAP analysis showing top predictive features
- **Overfitting Detection**: CPCV with mean OOS score -1802.3683

### Validation Strategy
- **TimeSeriesSplit cross-validation** (prevents data leakage)
- 5-fold walk-forward validation
- 90-day rolling window (~2,000 data points per asset)
- Out-of-sample testing on unseen symbols
- CPCV (Combinatorial Purged Cross-Validation) for overfitting detection

**[View ML pipeline details →](docs/ml_pipeline.md)**

---

## 📊 Performance Metrics

| Metric | Value |
|--------|-------|
| **Symbols Evaluated** | 55 (filtered from 60 total) |
| **Mean BUY Precision** | 0.950 |
| **Mean BUY Recall** | 0.951 |
| **Mean BUY F1-Score** | 0.949 (median: 0.978) |
| **F1 ≥ 0.90 Success Rate** | 86% (47/55 symbols) |
| **Directional Accuracy** | >62% (out-of-sample) |
| **XGBoost Hit Rate** | 73.5% |
| **Random Forest Hit Rate** | 67.5% |
| **SVR Hit Rate** | 48.8% |
| **WebSocket Latency** | <1 second |
| **Trade Execution Time** | Sub-second |
| **Model Retrain Frequency** | Every 1 hour (automated) |

### Model Evaluation Examples
- **AB-USD**: 80.0% accuracy
- **ACX-USD**: 100.0% accuracy
- **00-USD**: 91.1% accuracy
- **AAVE-USD**: 94.4% accuracy

### Risk-Adjusted Performance
- **Reward:Risk Ratio**: Improved from 2:1 → **4.67:1**
- **Dynamic TP/SL Range**: 2-8% (GARCH-driven vs. fixed 5%)
- **Position Sizing**: Kelly Criterion with portfolio constraints (25% Kelly Fraction)
- **Value at Risk (95%)**: -4.56%
- **CVaR (Expected Shortfall)**: -7.13%
- **Maximum Drawdown**: -35.24%
- **Current Drawdown**: -27.97%
- **Calmar Ratio**: -2.838

**[View detailed performance analysis →](docs/performance_metrics.md)**

---

## 🛡️ Risk Management System

### Advanced Risk Controls
- **GARCH(1,1) Volatility Modeling**: Dynamic stop-loss/take-profit adjustment
- **Value at Risk (VaR)**: Parametric, Historical, and Monte Carlo methods
  - VaR (95%): -4.56%
  - CVaR (95%): -7.13%
  - 89 observations analyzed
- **Kupiec Backtesting**: Model validation with p-value: 0.0796 (model adequate)
- **Drawdown Analysis**: 
  - Max: -35.24%
  - Average: -8.96%
  - Current: -27.97%
  - Duration: 6 days underwater
- **Kelly Criterion**: Optimal position sizing under uncertainty
- **Factor Risk Decomposition**: Multi-factor portfolio risk attribution
- **Liquidity Risk Assessment**: Bid-ask spread and volume analysis
- **Stress Testing**: Market crash scenario simulation available

### Position Sizing Recommendations
- **Recommended Size**: 0.28645083 BTC
- **Max Size**: 0.01432254 BTC
- **Risk Per Trade**: 2.0%
- **Kelly Fraction**: 25.0%
- **R/R Ratio**: 3.00
- **Take Profit**: $71,902.01
- **Stop Loss**: $69,109.70

### Market Regime Detection
- Bull market: Wider TP, tighter SL
- Bear market: Tighter TP, wider SL  
- Normal market: Balanced TP/SL levels
- Real-time regime classification with confidence scores

### TP/SL Analysis (BTC-USD Example)
- **Factor Breakdown**: 
  - tc_percentage: 3.0000
  - sl_percentage: 1.5000
  - reward_risk_ratio: 2.0000
  - confidence_score: 0.5740
- **Current Price**: $69,812.00
- **Take Profit**: $71,902.01 (3.0% upside)
- **Stop Loss**: $69,109.70 (1.5% downside)

**[View risk management details →](docs/risk_management.md)**

---

## 🔧 Technical Stack

| Component | Technology |
|-----------|-----------|
| **Backend** | Python 3.9+, Flask |
| **ML Framework** | Scikit-learn, XGBoost, SciPy |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Plotly Dash, Matplotlib |
| **Database** | SQLite (production-ready schema) |
| **Real-time Data** | WebSocket (Coinbase Advanced Trade) |
| **API Integration** | REST (Coinbase, custom JWT auth) |
| **Testing** | Pytest, Coverage.py |
| **CI/CD** | GitHub Actions (lint, test, security scan) |
| **Documentation** | LaTeX (research paper), Markdown |

---

## 📂 System Features

### Dashboard Modules
- ✅ **Dashboard**: Portfolio value ($516.10), P&L tracking ($22.98), 31 open positions
- ✅ **Charts**: Live candlestick charts with ML overlays and technical indicators (RSI, MACD)
- ✅ **ML Models**: Model training, evaluation (80-100% accuracy), ensemble comparison, SHAP analysis
- ✅ **Risk**: VaR/CVaR analysis, drawdown tracking, position sizing, stress testing
- ✅ **Technical**: Opportunity analysis, strategic auto-trader with configuration
- ✅ **Futures**: Perpetual futures trading with 1x-10x leverage, funding rate display
- ✅ **Sentiment**: Market sentiment analysis
- ✅ **Backtest**: Quantitative backtesting with Monte Carlo simulation
- ✅ **Ledger**: Transaction history and audit trail
- ✅ **Sessions**: Trading session management
- ✅ **Settings**: System configuration and API credentials

### Key Capabilities
- **Automated Trading**: Strategic auto-trader running since Feb 14, 02:14 PM
- **ML Predictions**: 100% confidence BUY/SELL signals with reasoning
- **Risk Categorization**: Low (0), Medium (0), High (0), Critical (0)
- **Multi-Asset Support**: BTC, ETH, SOL, DOGE, and 50+ other cryptocurrencies
- **Real-time Monitoring**: System OK, Trading Active status indicators
- **Model Health**: Drift detection, concept drift monitoring, retrain recommendations

---

## 📂 Module Architecture

**System decomposed into 7 focused modules** (refactored from 7,824-line monolith):

| Module | Purpose | Lines |
|--------|---------|-------|
| `data_fetcher.py` | Coinbase API, price caching, account queries | 723 |
| `feature_engine.py` | Technical indicators, momentum analysis | 183 |
| `ml_models.py` | Model training, predictions, evaluation | 526 |
| `trading_engine.py` | Trade execution, order management, TP/SL | 1,130 |
| `market_scanner.py` | Opportunity detection, signal generation | 378 |
| `portfolio_db.py` | Database management, position tracking | 1,006 |
| `websocket_handler.py` | Real-time price feeds, JWT auth | 433 |

---

## 🔒 Proprietary Components (Not Included)

The following are **not included** in this public repository:

- ❌ Stacking ensemble implementation & hyperparameters
- ❌ Trading execution logic & order placement algorithms
- ❌ GARCH volatility model parameters & calibration
- ❌ Risk management calculation methods
- ❌ Database schemas & production configurations
- ❌ API authentication credentials & key management
- ❌ WebSocket message parsing & price update logic
- ❌ Feature engineering transformations & alpha factors
- ❌ Model training pipelines & cross-validation setup
- ❌ Production deployment configurations
- ❌ SHAP feature importance calculation methods
- ❌ Kelly Criterion position sizing formulas
- ❌ VaR/CVaR calculation implementations
- ❌ Drift detection algorithms
- ❌ Futures leverage optimization methods

---

## 🎓 Academic Context

**Project Details:**
- **Institution**: Georgia State University, Department of Computer Science
- **Program**: Bachelor of Science in Computer Science
- **Author**: Sineshaw Tesfaye
- **Expected Graduation**: May 2026
- **Purpose**: Senior capstone project demonstrating ML engineering, quantitative finance, and production system design

**Skills Demonstrated:**
- Advanced machine learning (ensemble methods, time series, SHAP analysis, drift detection)
- Software architecture (refactoring, modular design, MVC pattern)
- Quantitative finance (risk management, portfolio theory, derivatives, futures trading)
- Real-time systems (WebSocket, sub-second latency, event-driven architecture)
- Production engineering (CI/CD, testing, monitoring, logging)
- Technical writing (research paper, documentation, API specs)
- Financial mathematics (GARCH, VaR, Kelly Criterion, Sharpe/Calmar ratios, Kupiec backtesting)

---

## 💼 For Recruiters & Employers

**Full codebase available upon request for technical interviews.**

I'm happy to:
- 📹 **Walk through the system architecture** in a technical screen
- 🔓 **Grant temporary read access** to the private repository
- 💻 **Live code review** of specific modules or algorithms
- 📊 **Demonstrate the system** with live data
- 🎥 **Screen share the dashboard** with real-time trading

**Contact:** steswfaye4@student.gsu.edu

---

## 🤝 Collaboration & Licensing

Interested in:
- 🏢 **Commercial licensing** of this technology?
- 🚀 **Collaborating** on a trading platform startup?
- 🎓 **Research partnership** or co-authorship?

**Get in touch:** steswfaye4@student.gsu.edu

---

## 📚 Documentation

- **[System Architecture](docs/architecture.md)** - Detailed component design
- **[ML Pipeline](docs/ml_pipeline.md)** - Model training & validation methodology
- **[Performance Metrics](docs/performance_metrics.md)** - Results & statistical analysis
- **[Risk Management](docs/risk_management.md)** - Quantitative risk framework

---

## 🔗 Connect

- 💼 **LinkedIn**: [Connect with me on LinkedIn](https://linkedin.com)
- 📧 **Email**: steswfaye4@student.gsu.edu
- 🎓 **University**: Georgia State University
- 📍 **Location**: Atlanta, GA (open to relocation)

---

## 📖 Citation

If you reference this work, please cite:

```bibtex
@misc{tesfaye2026crypto,
  author = {Tesfaye, Sineshaw},
  title = {Advanced Modular Cryptocurrency Trading & Analytics Platform: 
           A Comprehensive Machine Learning Framework},
  year = {2026},
  institution = {Georgia State University, Department of Computer Science},
  url = {https://github.com/shawtes/coinbase-trading-portfolio}
}
```

---

## ⚖️ License

This project is licensed under a **Custom Source-Available License**.

- ✅ View for educational/portfolio purposes
- ❌ No commercial use, redistribution, or deployment

See [LICENSE](LICENSE) for full terms.

---

## 🙏 Acknowledgments

- **Georgia State University** Department of Computer Science
- **Co-development assistance**: Claude (Anthropic AI)
- **API Provider**: Coinbase Advanced Trade API
- **Inspiration**: Quantitative finance literature, WorldQuant alpha research

---

**Last Updated:** February 2026

---

*This is a portfolio demonstration. Core algorithms are proprietary.*  
*Full system available to employers during interview process.*