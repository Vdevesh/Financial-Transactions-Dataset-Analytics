# Project Overview

This project provides a comprehensive analysis of a banking dataset containing information about users and their credit/debit cards. The analysis spans across data cleaning, exploratory data analysis (EDA), and advanced statistical modeling to uncover relationships between user demographics and financial behaviors.
The goal is to understand the factors influencing credit limits, card brand preferences, and the overall distribution of card types among different user segments.

# Project Structure
* **users_data.ipynb**: Focused on user-level data processing and demographic exploration using high-performance libraries like Polars.
* **card_data.ipynb**: Analysis of card-specific features including brands, types, and account history.
* **relationship_analysis.ipynb**: Advanced statistical testing, including ANOVA, Chi-Square tests, and Linear Regression to find correlations between variables.

# Tech StackData
* **Manipulation**: Pandas, Polars, NumPy
* **Visualization**: Matplotlib, Seaborn
* **Statistical Analysis**: SciPy, Statsmodels

# Data Preprocessing & Feature Engineering
Before analysis, the raw data underwent several transformation steps:
* **Currency Cleaning**: Converted string-based currency columns (e.g., credit_limit, per_capita_income) into numerical formats by removing symbols ($) and commas.
* **Date Formatting**: Normalized account opening dates for time-series analysis.
* **Feature Creation**:
  * Calculated Age based on birth year and month.
  * Derived Retirement Status based on age thresholds.
* **Data Integration**: Merged user and card datasets using a Left Join to create a unified view for OLAP (Online Analytical Processing).

# Key Insights from EDA
1. **Card Distribution**
* **Card Brands**:Analysis of the market share of major brands like Visa, Mastercard, and Amex.
* **Card Types**: Distribution of Credit, Debit, and Prepaid cards across the user base.
* **Account Trends**: Identified the oldest account (dating back to 1991) and the most recent account (2020).

2. **Demographic Trends**
* Visualized the average number of cards held per client.
* Explored how retirement status and age groups correlate with financial limits.

# Statistical Analysis & Modeling
1. **Association Testing (Categorical Variables)**
We used **Chi-Square tests** to determine if demographic factors like Gender influence:
* Choice of **Card Brand** (e.g., Do men prefer Visa over Mastercard?).
* Preference for **Card Type** (Credit vs. Debit).

2. **Analysis of Variance (ANOVA)**
Performed ANOVA to compare the means of numerical variables across different categorical groups, such as comparing yearly income or **credit scores** across different **card brands**.

3. **Regression Analysis: Income vs. Credit Limit**
A Linear Regression model was built to predict the credit_limit based on yearly_income.
* **Hypothesis**:
  * **$H_0$**: There is no relationship between yearly income and credit limit.
  * **$H_a$**: There is a significant relationship between yearly income and credit limit.
* **Results**:
  * The model **rejected the Null Hypothesis** ($p < 0.05$).
  * **Conclusion**: There is strong statistical evidence that an increase in yearly income leads to a higher credit limit.
  * **R-squared**: Used to measure the proportion of variance in credit limit explained by income.

 # Conclusion
 The analysis demonstrates that while card brand preference is widely distributed, financial capacity (income) remains the primary predictor of credit accessibility. These insights can help banks target specific   demographics with tailored card products.
