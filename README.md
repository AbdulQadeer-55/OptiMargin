# OptiMargin

A Bayesian approach to price elasticity estimation and margin optimization for webshop products, built using Python, PyMC, and scikit-learn. This project analyzes a dataset of webshop transactions to estimate demand sensitivity to price changes and recommend optimal margin percentages to maximize a custom reward function.

## Project Overview

**Objective**:  
Estimate price elasticities with confidence intervals and recommend optimal margin percentages (0–90%) for webshop products to maximize the reward function:  
`Reward = 0.2 * Margin * # put into basket + 0.8 * Margin * # purchased`.

**Dataset**:  
- Source: `Dataset Price optimization RL.xlsx` (175,630 rows)
- Features: `Price`, `MarginPercent`, `Brand`, `Category`, `VisitorSource`, `VisitorOS`, `VisitorReturning`
- Targets: Binary purchase indicator (`Purchased`), basket and purchase counts

**Approach**:  
1. Preprocess data with aggregation by `ProductID` and one-hot encoding.
2. Fit a Bayesian logistic regression model with hierarchical effects for `Brand` and `Category`.
3. Calculate price elasticities with 95% credible intervals.
4. Optimize margins using the reward function.
5. Validate results with accuracy and AUC-ROC metrics.

## Installation

### Prerequisites
- Python 3.10+
- Git

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/OptiMargin.git
   cd OptiMargin
