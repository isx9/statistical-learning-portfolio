![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
# Statistical Learning Portfolio

This statistical portfolio comprises three projects built for the Statistical Learning and Data Analysis course, each combining theoretical grounding with hands-on implementation across the following topics: exploratory data analysis and unsupervised learning, probability model theory and simulation, regression with regularisation and non-linear methods.

## Projects

### 1. Exploratory Data Analysis & Unsupervised Learning
`01-exploratory-data-analysis/`

Full EDA pipeline on a dataset of 1002 students linking lifestyle habits to academic performance (study hours, social media and Netflix use, sleep, attendance, mental health rating, exam score). Covers missing data handling, univariate and bivariate analysis, correlation structure, PCA and clustering to uncover behavioral groupings among students.

**Tools:** R, tidyverse, FactoMineR, factoextra

### 2. Probability Model Theory and Simulation
`02-probability-models/`

Theoretical comparison of the Poisson and Exponential distributions: parameters, moments, and their asymptotic convergence to the Gaussian via the Central Limit Theorem and the Gamma distribution. Validated through simulation, then applied to a real-world scenario by modeling the frequency and timing of cybersecurity intrusion attempts.

**Tools:** Python, NumPy, SciPy, Matplotlib, Seaborn

### 3. Regression with Regularisation and Non-Linear Methods
`03-regression-simulation/`

Simulated sparse linear regression (n=300, p=10) with OLS estimation and full diagnostics (leverage, Cook's distance, DFFITS, studentized residuals), followed by Ridge, Lasso, and Elastic-Net regression with cross-validated hyperparameter selection. A separate bias-variance experiment compares polynomial regression against splines and LOESS on a non-linear (sinusoidal) generating function.

**Tools:** Python, scikit-learn, statsmodels, SciPy

## Structure

statistical-learning-portfolio/
├── 01-exploratory-data-analysis/
│ ├── eda_student_habits.Rmd
│ └── data/student_habits_performance.csv
├── 02-probability-models/
│ └── poisson_exponential_comparison.ipynb
└── 03-regression-simulation/
└── regression_shrinkage_bias_variance.ipynb

## Running the notebooks

- **R project:** open `eda_student_habits.Rmd` in RStudio and knit, or run interactively. Requires `tidyverse`, `psych`, `corrplot`, `fastDummies`, `FactoMineR`, `factoextra`.
- **Python projects:** each notebook runs standalone with a standard scientific Python stack (`numpy`, `pandas`, `scipy`, `scikit-learn`, `statsmodels`, `matplotlib`, `seaborn`).
