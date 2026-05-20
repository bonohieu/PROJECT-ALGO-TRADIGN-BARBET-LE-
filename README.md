# PROJECT-ALGO-TRADING-BARBET-LE

# Adaptive Sector Allocation via Regime-Switching
**Cong-Hieu LE, Marilou BARBET — Master in Finance and Banking, UPF-BSM**

Walk-forward backtest on 11 SPDR sector ETFs (2007–2024) comparing Min-Variance, Max-Sharpe, and a KMeans regime-switching portfolio.

Does a regime-switching sector portfolio - selecting Max-Sharpe in bull markets and Min-Variance otherwise, based on a walk-forward KMeans classifier - generate superior risk-adjusted returns compared to static strategies and the S&amp;P 500 over 2007-2024?


---

## Requirements

Python 3.9+ and the following packages:

```
pip install numpy pandas yfinance matplotlib scipy scikit-learn
```

---

## How to reproduce

1. Clone or download the repository
2. Open `Algo_trading_LE_BARBET-3.ipynb` in Jupyter Notebook or JupyterLab
3. Run all cells in order (Kernel → Restart & Run All)

All data is downloaded automatically from Yahoo Finance on first run — no local data files are needed. An internet connection is required.

---

## Output files

The notebook generates the following files in the working directory:

| File | Description |
|---|---|
| `fig1_cumulative.png` | Cumulative returns of each sector ETF vs SPY (2005–2024) |
| `fig2_walk_forward.png` | Walk-forward cumulative returns with regime shading |
| `fig3_drawdowns.png` | Drawdown chart for all strategies |
| `performance_metrics.csv` | Annualised return, vol, Sharpe, max drawdown, Calmar |
| `regime_breakdown.csv` | Sharpe ratios by detected regime (bear / neutral / bull) |
| `sharpe_gap.csv` | In-sample vs walk-forward Sharpe comparison |

---

## Notes

- The backtest runs from Q1 2007 to Q4 2024 with quarterly rebalancing
- Estimation window: trailing 504 trading days (~2 years) at each rebalancing date
- XLRE and XLC enter the universe dynamically once they have 504 days of history
- Transaction costs: 10 bps applied to turnover at each rebalancing
- Runtime: approximately 3–5 minutes depending on machine
