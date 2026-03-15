# Mean-Variance Portfolio Optimization

This project implements a long-only mean-variance portfolio optimization model in Python using daily stock return data from Yahoo Finance.

## Overview

The notebook:
- downloads 5 years of historical price data for 20 large-cap stocks
- computes daily returns
- estimates expected returns and the covariance matrix
- solves a constrained minimum-variance portfolio optimization problem
- computes the portfolio's annualized expected return and Sharpe ratio

The optimization is based on the Markowitz mean-variance framework.

## Objective

The portfolio is constructed to:

- minimize portfolio variance
- satisfy a minimum expected return constraint
- remain fully invested
- allow only long positions

Mathematically, the optimization solves:

minimize  
    wᵀ V w

subject to

    wᵀ μ ≥ r_min  
    Σ w_i = 1  
    0 ≤ w_i ≤ 1

where:

- **w** = portfolio weight vector  
- **μ** = vector of expected daily returns  
- **V** = covariance matrix of daily returns  
- **r_min** = minimum desired portfolio return

## Data

- Source: `yfinance`
- Universe: 20 diversified equities
- Frequency: daily
- Horizon: 5 years
- Prices used: adjusted close prices

## Output

The notebook reports:
- optimized portfolio weights
- annualized expected portfolio return
- annualized Sharpe ratio

It also plots:
- top 5 performers by cumulative return
- bottom 5 performers by cumulative return

## Tools Used

- Python
- NumPy
- Pandas
- yfinance
- SciPy

## Notes

- The model uses historical sample means and sample covariance estimates.
- The Sharpe ratio is computed from daily quantities and annualized using the square-root-of-time rule.

## Possible Extensions

Some natural extensions include:
- shrinkage covariance estimation
- short-selling or leverage constraints
- efficient frontier construction
