
<h3>This code performs an Ordinary Least Squares (OLS) regression analysis on a sales dataset and conducts hypothesis testing.<h3>
<h5>How to run this code:
  <p> 1. Download Anaconda</p>
  <p> 2. Run Jupyter in the default Browser through the Anaconda prompt</p><h5>


<h6>1. Data Loading and Exploration :

    Imports libraries like pandas (pd), NumPy (np), statsmodels (sm), and SciPy (sc).
    Reads data from an Excel file using pd.read_excel.
    Prints the first few rows of the data using data.head().

2. Model Fitting:

    Defines the dependent variable (Y) as the "sales" column.
    Defines the independent variables (X) as a DataFrame containing "price" and "advert" columns.
    Adds a constant term to X using sm.add_constant for intercept calculation.
    Fits the OLS model using sm.OLS(Y, X).fit().
    Prints the model summary using Model.summary().

3. Hypothesis Testing for Individual Coefficients:

    Performs t-tests for the coefficients of "price" and "advert" using Model.t_test.
    Defines the null hypothesis (H0) for each coefficient: it's equal to zero.
    Calculates the critical t-value for a 5% significance level using SciPy.
    Compares the absolute values of the t-statistic and critical t-value to reject or fail to reject H0 for each coefficient.

4. F-Test for Overall Significance:

    Performs an F-test using Model.f_test to assess the joint significance of all coefficients (including the intercept).
    Calculates the critical F-value for a 5% significance level using SciPy's f.
    Compares the absolute values of the F-statistic and critical F-value to reject or fail to reject H0 (all coefficients are zero).

5. R-squared Calculation:

    Calculates R-squared (coefficient of determination):
        From the model summary using Model.rsquared.
        Using Explained Sum of Squares (ESS) and Total Sum of Squares (TSS).
        Using Residual Sum of Squares (RSS) and TSS.

6. Variance Inflation Factor (VIF) Calculation:

    Calculates VIF for each independent variable using statsmodels.stats.outliers_influence.variance_inflation_factor.
    VIF indicates multicollinearity:
        1: No correlation
        1 < VIF < 5: Low multicollinearity
        VIF > 5: High multicollinearity (variables might be highly correlated)

7. Breusch-Pagan Test for Heteroscedasticity (commented out):

    This test checks for unequal variance of residuals (heteroscedasticity).
    Uses statsmodels.stats.diagnostic.het_breuschpagan to perform the test.
    Analyzes the LM statistic and p-value to assess the presence of heteroscedasticity.<h6>


