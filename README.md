## Multi-factor Model

## AI for Trading Nano Project

In this project, we will build a statistical risk model using PCA. We'll use this model to build a portfolio along with 5 alpha factors. We’ll create these factors, then evaluate them using factor-weighted returns, quantile analysis, sharpe ratio, and turnover analysis. At the end of the project, We’ll optimize the portfolio using the risk model and factors using multiple optimization formulations. For the dataset, we'll be using the end of day from Quotemedia and sector data from Sharadar.

## Introduction

A multi-factor model is a financial model that employs multiple factors in its calculations to explain market phenomena and/or equilibrium asset prices. A multi-factor model can be used to explain either an individual security or a portfolio of securities. It does so by comparing two or more factors to analyze relationships between variables and the resulting performance.

- Alpha (α) is a term used in investing to describe an investment strategy's ability to beat the market, or its "edge." Alpha is thus also often referred to as “excess return” or “abnormal rate of return,” which refers to the idea that markets are efficient, and so there is no way to systematically earn returns that exceed the broad market as a whole. Alpha is often used in conjunction with beta (the Greek letter β), which measures the broad market's overall volatility or risk, known as systematic market risk.
- Multifactor models describe the return on an asset in terms of the risk of the asset with respect to a set of factors. Such models generally include systematic factors, which explain the average returns of a large number of risky assets. Such factors represent priced risk—risk for which investors require an additional return for bearing.
- In statistical factor models, statistical methods are applied to a set of historical returns to determine portfolios that explain historical returns in one of two senses. In factor analysis models, the factors are the portfolios that best explain (reproduce) historical return covariances. In principal-components models, the factors are portfolios that best explain (reproduce) the historical return variances.

## Instructions and Install Packages

The Jupyter nodebook must be run under python 3.6.  Type the below commands in the Terminal to  to create and activate a conda environment.

```
conda create -n py36 python=3.6 anaconda
activate py36 #if on Windows
source activate py36 #if on Linux or MacOS
```

## Package Conflicts

Before running `project_4.ipynb`, you need to install all packages in `requirements.txt`. However, it turns out that these packages doesn't work very well with this notebook. If the below error pops out, `No module named 'pandas.util._decorators'`, then you need go to the local  folder:`C:\anaconda3\envs\py36\lib\site-packages\pandas\util`, and rename the file`decorators.py` as `_decorators.py`. 

After that, run the main notebook `project_4.ipynb` using the above local environment.

### Main Files: Jupyter Structure

```
├── Build statistical risk model using PCA
    ├── Fit a PCA model to the returns data
    ├── Calculates the factor exposures from Scikit-Learn's PCA() class
    ├── Calculates the factor returns from Scikit-Learn's PCA() class
    ├── Calculate the annualized factor covariance matrix
    ├── Calculate the Idiosyncratic Risk Matrix
    ├── Calculate the Idiosyncratic variance Vector
    └── Predict using the Risk Model
├── Build Alpha Model
    ├── Create 5 Alpha Factors
        ├── Momentum 1 Year Factor
        ├── Mean Reversion 5 Day Sector Neutral Factor
        ├── Mean Reversion 5 Day Sector Neutral Smoothed Factor
        ├── Overnight Sentiment Factor
        └── Overnight Sentiment Smoothed Factor
    ├── Quantile Analysis
    ├── Turnover Analysis
    └── Calculate the sharpe ratio of factor returns
├── The Combined Alpha Vector: simply averaging the scores from each alpha
└── Optimal Portfolio Constrained by Risk Model: find a portfolio that trades as close as possible to the alpha model but 		limiting risk as measured by the risk model
	├── Optimize with a Regularization Parameter
	└── Optimize with a Strict Factor Constraints and Target Weighting
```

### Authors

Jinjin Liang authored the main functions in `project_4.ipynb`, and this README. All other project files were created by [Udacity](https://www.udacity.com/).

