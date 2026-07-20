# Biometric Analysis: Modeling the Relationship Between Height and Weight

## 1. Executive Summary
This project is an inferential statistical study aimed at modeling and analyzing the linear relationship between human Height (Dependent Variable) and Weight (Independent Variable) using Simple Linear Regression. Built with Python, this project serves as a foundational biometric case study, focusing heavily on validating core statistical assumptions rather than just model fitting.

## 2. Methodology & Statistical Validation
To ensure the statistical integrity of the regression model, a sequential econometric pipeline was implemented to test key baseline assumptions:
* **Linearity:** Inspected using scatter plots to confirm a linear baseline trend between variables.
* **Normality of Residuals:** Validated using Q-Q plots and the Jarque-Bera test to ensure error terms follow a normal distribution.
* **Homoscedasticity:** Checked using the White test and residual vs. fitted plots to ensure constant error variance across all observation levels.

## 3. Key Findings & Interpretation
* **Statistical Significance:** The Weight coefficient was highly statistically significant ($p < 0.05$), confirming a strong positive relationship with Height.
* **Goodness of Fit:** The model achieved an $R^2$ of **0.855**, indicating that **85.5%** of the variance in Height is explained by Weight.
* **Practical Interpretation:** 
  * **Intercept ($\beta_0$):** **48.4779** (The baseline mathematical constant).
  * **Slope ($\beta_1$):** For every 1-unit increase in Weight, Height is expected to increase by **0.1108** units.

## 🛠️ Tech Stack
* **Python** (`Pandas`, `NumPy`, `Statsmodels`, `Matplotlib`, `Seaborn`)
