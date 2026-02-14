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
├── Random Forest Regressor (feature importance analysis)
├── XGBoost Regressor (gradient boosting optimization)
└── Support Vector Regressor (non-linear pattern capture)
         │
         ▼
Ridge Meta-Learner (optimal ensemble weighting)
```

### Feature Engineering
- **35+ WorldQuant-style alpha factors**
- Price momentum, volatility, cross-sectional ranking
- Kalman filtering for signal denoising
- Wavelet transforms for multi-scale analysis
- PCA-based factor extraction

### Validation Strategy
- **TimeSeriesSplit cross-validation** (prevents data leakage)
- 5-fold walk-forward validation
- 90-day rolling window (~2,000 data points per asset)
- Out-of-sample testing on unseen symbols

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
| **WebSocket Latency** | <1 second |
| **Trade Execution Time** | Sub-second |
| **Model Retrain Frequency** | Every 1 hour (automated) |

### Risk-Adjusted Performance
- **Reward:Risk Ratio**: Improved from 2:1 → **4.67:1**
- **Dynamic TP/SL Range**: 2-8% (GARCH-driven vs. fixed 5%)
- **Position Sizing**: Kelly Criterion with portfolio constraints
- **Risk Metrics**: VaR, CVaR, Factor model decomposition

**[View detailed performance analysis →](docs/performance_metrics.md)**

---

## 🛡️ Risk Management System

### Advanced Risk Controls
- **GARCH(1,1) Volatility Modeling**: Dynamic stop-loss/take-profit adjustment
- **Value at Risk (VaR)**: Parametric, Historical, and Monte Carlo methods
- **Expected Shortfall (CVaR)**: Tail risk quantification
- **Kelly Criterion**: Optimal position sizing under uncertainty
- **Factor Risk Decomposition**: Multi-factor portfolio risk attribution
- **Liquidity Risk Assessment**: Bid-ask spread and volume analysis

### Market Regime Detection
- Bull market: Wider TP, tighter SL
- Bear market: Tighter TP, wider SL  
- Normal market: Balanced TP/SL levels

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

---

## 🎓 Academic Context

**Project Details:**
- **Institution**: Georgia State University, Department of Computer Science
- **Program**: Bachelor of Science in Computer Science
- **Author**: Sineshaw Tesfaye
- **Expected Graduation**: May 2026
- **Purpose**: Senior capstone project demonstrating ML engineering, quantitative finance, and production system design

**Skills Demonstrated:**
- Advanced machine learning (ensemble methods, time series)
- Software architecture (refactoring, modular design)
- Quantitative finance (risk management, portfolio theory)
- Real-time systems (WebSocket, sub-second latency)
- Production engineering (CI/CD, testing, monitoring)
- Technical writing (research paper, documentation)

---

## 💼 For Recruiters & Employers

**Full codebase available upon request for technical interviews.**

I'm happy to:
- 📹 **Walk through the system architecture** in a technical screen
- 🔓 **Grant temporary read access** to the private repository
- 💻 **Live code review** of specific modules or algorithms
- 📊 **Demonstrate the system** with live data

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
