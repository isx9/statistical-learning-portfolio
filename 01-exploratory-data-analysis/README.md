# Exploratory Data Analysis & Unsupervised Learning

![R](https://img.shields.io/badge/R-4.x-276DC3?style=flat-square)
![status](https://img.shields.io/badge/status-academic%20project-d2691e?style=flat-square)

Exploratory data analysis, principal component analysis, and K-means clustering on a dataset of 1,002 students, examining how study habits, lifestyle, and demographic factors relate to academic performance.

## Dataset

`student_habits_performance.csv` — 1,002 observations, 16 variables:

- **Numeric:** age, study hours/day, social media hours/day, Netflix hours/day, attendance %, sleep hours/day, exercise sessions/week, self-reported mental health rating (0–10), exam score (0–100)
- **Categorical:** gender, part-time job status, diet quality, parental education level, internet quality, extracurricular participation

## Approach

1. **Data cleaning** — 7 missing values in `diet_quality` (<1% of the data), examined for a pattern before imputing with the mode.
2. **Univariate & bivariate analysis** — descriptive statistics, frequency tables, and correlation structure across numeric and categorical variables.
3. **Principal Component Analysis** — 12 components needed to explain 84% of total variance, reflecting the complexity of student behavior. The first two components were interpretable:
   - **PC1 — academic performance & engagement.** Separates students by exam score, study hours, and mental health rating (positive) against social media/Netflix use and part-time work (negative).
   - **PC2 — lifestyle & demographics.** Driven by gender, internet quality, and sleep on one side vs. exercise frequency and parental education on the other — unrelated to academic outcomes, but capturing who students are rather than how they perform.
4. **K-means clustering** — cluster count selected via silhouette analysis (optimal at k=3). The resulting clusters are visibly separated along PC1 and PC2, indicating distinct student subgroups beyond simple performance tiers.

## Key findings

- Study hours per day and self-reported mental health are the strongest predictors of exam performance — attendance alone does not guarantee high scores.
- Part-time job status, parental education, and extracurricular participation showed little to no relationship with academic outcomes, contrary to initial expectations.
- Clustering revealed three distinguishable student groups, suggesting meaningful behavioral segmentation independent of performance level alone.

## Tools

R, tidyverse, psych, corrplot, fastDummies, FactoMineR, factoextra

## Running it

Open `eda_student_habits.Rmd` in RStudio and knit, or run chunk-by-chunk interactively. Requires the packages listed above (all available on CRAN).
