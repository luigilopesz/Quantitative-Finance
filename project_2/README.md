# Project 2 — Mean-Variance Portfolio Optimization

An empirical Markowitz study on a 30-stock subset of the S&P 500, covering the tangency (max-Sharpe) portfolio, the minimum-variance portfolio, the long-only efficient frontier with its Capital Market Line, a monthly-rebalanced performance comparison, and a two-asset correlation study illustrating how diversification benefits depend on ρ.

---

## Overview

- **Universe:** Top 30 S&P 500 constituents by market cap on the first trading day of the window (same rule-based selection as Project 1).
- **Period:** Daily data, 2015 – 2024.
- **Risk-free rate:** 2% annual (flat assumption).
- **Inputs:** Annualized mean and covariance built from **simple** returns (`pct_change`), not log returns.

---

## Tasks

1. **Tangency portfolio** — long-only max-Sharpe via SLSQP, with explicit `risk_premium = μ̂ − rf`.
2. **Minimum-variance portfolio** — long-only `min w'Σw`.
3. **Monthly-rebalanced performance** — fixed-target weights snapped back to target on the first trading day of each month; report annualized return, vol, and Sharpe for Tangency vs MVP, plus a growth-of-$1 plot vs the risk-free curve.
4. **Efficient frontier** — constrained long-only frontier (60 target returns), with the CML drawn from `(0, rf)` through the tangency point.
5. **Two-asset correlation study** — parametric `(σ_p, μ_p)` curves for ρ ∈ {−1, −0.5, 0, 0.3, 1} using one high-μ/high-σ and one low-μ/low-σ name; includes the analytic check `w* = σ₂/(σ₁+σ₂)` for the ρ = −1 zero-variance point.

---

## Data

- **File:** `SPX_database_2010.xlsx`
- **Sheets used:** `prices`, `total_ret`, `mkt_cap`

> Note: The dataset is not tracked in the repository.

---

## Project Structure

```
project_2/
├── README.md       # This file
└── main.ipynb      # Analysis notebook
```

---

## Requirements

```bash
pip install pandas numpy scipy matplotlib openpyxl
```

---

## Running

Open [main.ipynb](main.ipynb) in Jupyter or VS Code and run all cells top-to-bottom.
