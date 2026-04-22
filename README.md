# Momentum-Driven Capital Preservation Portfolio
## FIN 7053 Algorithmic Trading — Final Project — Spring 2026

### Strategy Overview
Systematic momentum strategy applied to the 20 largest S&P 500 
constituents, with CVXPY minimum variance optimization and a 
VIX-triggered circuit breaker for capital preservation.

### Performance Summary (Backtest 2021–2026)
| Metric | Strategy | SPY |
|--------|----------|-----|
| Total Return | 46.33% | 55.31% |
| CAGR | 9.51% | 11.08% |
| Sharpe Ratio | 0.867 | 0.646 |
| Sortino Ratio | 1.120 | 1.007 |
| Max Drawdown | -11.89% | -17.32% |

### Key Parameters
- Universe: Top 20 S&P 500 by market cap
- Signal: 4-month momentum (Jegadeesh & Titman 1993)
- Optimizer: CVXPY minimum variance, 2% floor, 25% cap
- VIX Trigger: 23 → BIL | Re-entry: 18
- Rebalance: Biweekly

### Data Sources
- Alpaca Markets IEX feed — price data and execution
- yfinance — VIX index data (Alpaca does not carry index data)

### Requirements
pip install alpaca-py cvxpy yfinance pandas numpy matplotlib

### How to Run
1. Open notebook in Google Colab
2. Add Alpaca API keys to Cell 1
3. Run all cells in order (1 through 8)
4. Cell 7 backtest data fetch takes approximately 2 minutes

### References
- Fama, E. F., & French, K. R. (1996). Multifactor explanations 
  of asset pricing anomalies. Journal of Finance, 51(1), 55-84.
- Jegadeesh, N., & Titman, S. (1993). Returns to buying winners 
  and selling losers. Journal of Finance, 48(1), 65-91.

### Disclaimer
Paper trading only. Not financial advice.
