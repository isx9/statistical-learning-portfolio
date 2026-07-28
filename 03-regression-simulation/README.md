# Regression with Regularisation and Non-Linear Methods

![python](https://img.shields.io/badge/python-3.11%2B-306998?style=flat-square)
![status](https://img.shields.io/badge/status-academic%20project-d2691e?style=flat-square)

Simulated regression study covering OLS diagnostics, shrinkage methods, and the bias-variance trade-off, using fully controlled synthetic data so that estimated effects can be checked against known ground truth.

## Contents

### 1. Linear regression & diagnostics
Simulated a dataset (n=300, p=10) from a known linear model with a mix of strong, weak, and null-effect predictors (true coefficients: 3.7, 0.2, 0, 0, -2.3, 0, 0.1, 0, 3.1, 0). Fit OLS and confirmed it correctly recovered all statistically significant predictors matching the true non-zero coefficients (R² = 0.996). Ran full residual diagnostics: residuals vs. fitted, Q-Q plot, scale-location. Flagged high-leverage points, outliers, and influential observations using leverage, Cook's distance, DFFITS and studentized residuals (15 of 300 observations flagged as influential by at least one rule; only 1 true outlier).

### 2. Shrinkage and regularization
Applied Ridge, Lasso, and Elastic-Net to the same dataset, each with cross-validated hyperparameter selection:
- **Ridge** shrinks all coefficients toward zero without eliminating any — null predictors stay small but non-zero.
- **Lasso** performs automatic variable selection, correctly zeroing out 4 of 5 true-null predictors (one false positive) while retaining all true signal variables.
- **Elastic-Net** cross-validation selected α=1.0, collapsing to a pure Lasso solution — indicating multicollinearity wasn't severe enough to benefit from Ridge's L2 component.

### 3. Non-linear regression & bias-variance trade-off
Simulated a sinusoidal generating function (y = 1 + 3sin(x) + ε) at two sample sizes to isolate the bias-variance trade-off:
- **n=10:** a degree-10 polynomial interpolates all points exactly (training MSE ≈ 0) but oscillates wildly between them — a textbook overfitting case. A degree-3 polynomial has higher training error but tracks the true function far more closely.
- **n=200:** the same degree-10 polynomial stabilizes substantially, showing how more data constrains an otherwise over-flexible model.
- **Model comparison** on the n=200 set: spline regression (test MSE ≈ 1.30), smoothing splines (≈1.33), and LOESS (≈1.39) all outperformed the degree-10 polynomial (≈1.57), which suffered from boundary oscillations (Runge's phenomenon).

## Key takeaways

- With a well-specified model and n=300, OLS reliably distinguishes real signal from noise, even for weak effects but a handful of influential points can still meaningfully affect estimates.
- Lasso and Elastic-Net perform near-identical, principled variable selection here since the CV-selected α showed no benefit from Ridge's shrinkage.
- Model flexibility is only an asset when matched to available data: the same degree-10 polynomial is a cautionary tale at n=10 and a reasonable fit at n=200. Spline-based methods handled the non-linear structure more robustly at both scales.

## Tools

Python, scikit-learn, statsmodels, SciPy, pandas

## Running it

Open `regression_shrinkage_bias_variance.ipynb` in Jupyter. Requires `numpy`, `pandas`, `scipy`, `scikit-learn`, `statsmodels`, `matplotlib`, `seaborn`.
