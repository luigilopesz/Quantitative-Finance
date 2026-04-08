# Project 1 — Portfolio Construction & Diversification

An empirical study on portfolio construction, rebalancing, and the benefits of diversification using S&P 500 constituents.

---

## Overview

This project explores two classic exercises in quantitative portfolio management:

- **Part A** — Build and evaluate value-weighted vs. equally-weighted portfolios from a 30-stock subset of the S&P 500.
- **Part B** — A Monte Carlo style experiment demonstrating how portfolio variance decays as the number of holdings grows.

---

## Part A — Value-Weighted vs. Equally-Weighted Portfolios

### Setup
- **Universe:** 30 stocks selected from the S&P 500.
- **Period:** Daily data, 2015 – 2024 (10 years).
- **Rebalancing:** On the first trading day of each month, using information from the last trading day of the previous month (1-day lag).

### Tasks
1. Construct both a **value-weighted** and an **equally-weighted** portfolio.
2. Identify which portfolio exhibits the **highest turnover**.
3. Compute daily portfolio returns.
4. Compute performance statistics:
   - Annualized average return
   - Annualized standard deviation
   - Sharpe ratio
   - Information ratio (vs. S&P 500)
5. Plot cumulative returns for:
   - Value-weighted portfolio
   - Equally-weighted portfolio
   - S&P 500 benchmark
   - Risk-free rate

---

## Part B — Diversification Experiment

A simulation designed to illustrate how idiosyncratic risk is diversified away as portfolio size increases.

### Procedure
1. **(a)** Choose `n` stocks at random from the 30-stock universe (or enumerate all combinations).
2. **(b)** Compute ex-post returns of an equal-weighted portfolio where `wᵢ = 1/n`.
3. **(c)** Compute the variance of returns from the sample.
4. **(d)** Repeat steps (a)–(c) ~10 times.
5. **(e)** Repeat (a)–(d) for `n = 1, 2, 3, …, 30`.

### Goal
Plot average portfolio variance as a function of `n` and interpret the result in the context of **systematic vs. idiosyncratic risk**.

---

## Data

- **File:** `SPX_database_2010.xlsx`
- **Sheets:** `prices`, `total_ret`, `mkt_cap`
- Contains historical prices, total returns, and market capitalizations for S&P 500 constituents.

> Note: The dataset is not included in the repository.

---

## Project Structure

```
project_1/
├── README.md                  # This file
├── main.ipynb                 # Analysis notebook (Parts A & B)
└── SPX_database_2010.xlsx     # Data (not tracked)
```

---

## Requirements

```bash
pip install pandas numpy matplotlib openpyxl jinja2
```

---

## Running

Open [main.ipynb](main.ipynb) in Jupyter or VS Code and run all cells.
