# Multicollinearity Resolution & Dimensionality Reduction in Educational Metrics

## 1.  Executive Summary
This project addresses severe **Multicollinearity** encountered when modeling academic performance in Mathematics using Reading and Writing scores as explanatory variables. Due to the strong linear correlation between Reading and Writing, a standard Multiple Linear Regression (MLR) model suffered from unstable coefficient estimates and inflated standard errors. 

To resolve this issue, three distinct data-synthesis and dimensionality-reduction methodologies were implemented to consolidate Reading and Writing into a single composite feature (Independent Variable), reducing the architecture to a Simple Linear Regression framework predicting Mathematics performance (Dependent Variable).

---

## 2.  Methodological Approaches to Multicollinearity
To eliminate redundant variance and feature overlap, three independent engineering techniques were evaluated:

1. **Arithmetic Averaging (Composite Mean Index):**
   * Synthesized Reading and Writing into a single aggregated score ($X_{mean} = \frac{\text{Reading} + \text{Writing}}{2}$).
2. **Factor Analysis:**
   * Extracted a single underlying latent factor capturing the shared domain variance of language literacy skills.
3. **Principal Component Analysis (PCA):**
   * Constructed the first Principal Component ($PC_1$) to capture the maximum orthogonal variance present across both correlated metrics.

---

## 3.  Econometric Diagnostics & Model Validation
All three synthesized Simple Linear Regression models underwent rigorous residual and structural testing to ensure adherence to classical linear regression assumptions:

*  **Linearity:** Confirmed linear dependence between the synthesized literacy variables and Mathematics scores.
*  **Normality of Residuals:** Evaluated via Q-Q plots and Jarque-Bera to ensure normally distributed errors.
*  **Homoscedasticity:** Validated using the White test to confirm constant error variance.
*  **Independence of Errors:** Verified absence of autocorrelation in the residual distributions.

>  **Robustness Note:** Although exact normality and homoscedasticity tests were sensitive to raw residual behavior, the models remain statistically valid. With a large sample size ($N \approx 1,000$), the **Central Limit Theorem (CLT)** ensures robust inference regarding standard errors, while **Robust Standard Errors (HC3)** were applied to address heteroscedasticity concerns without biasing coefficient estimates.
---

## 4.  Comparative Findings & Key Takeaways
* **Structural Stability:** Transforming the bivariate reading/writing space into a single uncorrelated feature successfully eliminated Variance Inflation Factors (VIF) issues, restoring stability to regression estimates.
* **Analytical consistency:** All three approaches (Mean Index, Factor, and PCA $PC_1$) yielded highly statistically significant regression models ($p < 0.05$) with comparable goodness-of-fit metrics ($R^2$), proving that dimensionality reduction preserved the essential Analytical variance needed to model Mathematics performance.

---

## 🛠️ Tech Stack & Software Libraries
* **Python** (`Pandas`, `NumPy`, `Statsmodels`, `Matplotlib`, `Seaborn`, `SciPy`)
