# Deep Option Hedging Using Risk-Averse Contextual Bandit Learning

This is the one-ipynb repo for our course project in MSBA7021 Prescriptive Analytics at HKU Business School. 

## Intro

Our work mainly utilizes Contextual Multi-Armed Bandit (CMAB) model and Bayesian linear regression with Thompson Sampling to conduct risk-aware option hedging under the Profit & Loss (P&L) formulation, where the stock price is characterized by Geometric Brownian Motion (GBM), the option is priced via Black-Scholes Model (BSM),
and short-selling is allowed.

## Model Design

Four learning agents are evaluated in the experiments:
- Bayesian Neural Bandit
- Neural Greedy Bandit
- Naïve Bandit
- PTO with SARIMAX

Benchmarked against:
- Oracle
- Random pulls

## Findings

- Replication strategies (both w./w.o. short-selling) in the presence of risk and market friction fall within the modeling capabilities of Contextual Multi-Armed Bandits
- Deep Neural Networks representation learning and Bayesian Linear Regression with Thompson Sampling technique can significantly improve bandit performance, balancing exploration and exploitation, but are sensitive to outliers and not desirably robust w.r.t. hyperparameters  
- Times Series models do well in modeling the variance in market simulation, successfully mitigating losses in face of outliers, and are more robust in terms of hyperparameter settings 
- Approximation of objective function greatly varies model convergence
- Bandits typically pay great attention to time-to-maturity and converge to Oracle’s behavior as the hedging process comes to the end
- Bandits are prone to short-selling to maximize rewards when stock/option prices are declining, while largely missing out the opportunities to hedge as stock/option prices go up

## Limitations

- Our agents are trained and tested on simulated data generated from standard methods, the simulation strategy can have great impacts on model performance
- Some approximations of the objective function may not have guaranteed global convergence
- Agents warrant further hyperparams tuning, given limited time and computation resources
- It’s worthy of continuing research and more experiments to fully investigate the scope of the agents’ modeling capabilities and reasons behind variant agent behaviors under different formulations of the problem and combinations of hyperparameters

## 

Read the notebook and references for more details.

#### This project mainly builds upon the following two references:
- Cannelli, L., Nuti, G., Sala, M., & Szehr, O. (2020). Hedging using reinforcement learning: Contextual k-Armed Bandit versus Q-learning. arXiv:2007.01623. 
- Riquelme, C., Tucker, G., & Snoek, J. (2018). Deep bayesian bandits showdown: An empirical comparison of bayesian deep networks for thompson sampling. arXiv:1802.09127.
