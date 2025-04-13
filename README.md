# 🧠 Predicting Credit Card Account Cancellations

## 📌 Overview

This machine learning project focuses on identifying patterns that lead to customer credit card account cancellations using real-world banking data. The goal is to explore the key factors influencing cancellations and to build predictive models that estimate the likelihood of a customer closing their account in the future.

## About the dataset
The credit_card_df data frame contains information on the customers of a large U.S. bank which provides a number of financial services including multiple credit card offerings.

The bank is looking to see if it can determine the factors that lead to customers canceling their credit card account and whether it can predict if a customer will cancel their account in the future.

To maintain profits, banks must maximize the number of customers with credit lines. It is also in their best interests for customers to carry large credit card balances from month-to-month to maximize revenue from interest charges.

The bank has experienced record levels of customers closing their credit accounts in the past couple of years and this is leading to declining revenue.

The bank's goal is to become better at identifying customers at risk of canceling their account to minimize financial losses.
The data set contains a mixture of customer demographics and their financial behavior.

The outcome variable in this data is customer_status. This variable records whether a customer eventually closed their account and indicates a financial loss to the company.


The **target variable** is:
- `customer_status`: indicates whether a customer has **closed their credit card account** (`closed_account`) or not (`active_account`).

## ❓ Problem Statement

The bank aims to:
- Understand **why customers cancel accounts**.
- **Predict cancellations** with high accuracy.
- **Reduce costly errors** in churn prediction.
- Suggest actionable insights to **retain customers**.

## 🔍 Key Questions

- What customer behaviors are most associated with account cancellations?
- Can we accurately predict account closures using ML models?
- Which customers are at the highest risk?
- What strategies might prevent churn?


## 🧹 Data Cleaning & Preprocessing

Before modeling, we performed several data preparation steps to ensure high-quality inputs:

### ✅ Cleaning Steps

- **Missing Values Handling**:
  - Identified and checked for missing values across numerical and categorical columns.
  - Handled missing or null values appropriately depending on variable type (e.g., imputation or exclusion).
  
- **Filtering Data**:
  - Focused only on relevant rows by filtering for `customer_status` in `["closed_account", "active"]` to exclude incomplete or irrelevant statuses.

- **Outlier Detection and Handling**:
  - Visualized distributions (density plots) of key numerical variables such as:
    - `months_inactive_last_year`
    - `utilization_ratio`
    - `transactions_last_year`
  - Identified skewed patterns and ensured these didn’t bias the models.

- **Normalization/Scaling**:
  - Applied `StandardScaler` and `MinMaxScaler` for feature normalization to improve model performance and training consistency.

- **Encoding Categorical Variables**:
  - Converted variables like `marital_status`, `education`, `employment_status`, and `card_type` into suitable formats for modeling.
  
- **Renamed or Cleaned Columns**:
  - Ensured consistent naming for variables used in modeling and plotting.

### 📌 Visualization-Driven Quality Checks

- Used **`ggplot2`** and **`plotly`** to create:
  - Distribution plots for checking skewness and comparing churn vs active patterns
  - Bar charts for categorical variable distributions across churn status

These steps ensured we had clean, normalized, and interpretable data ready for statistical testing and model training.

## 📊 Exploratory Data Analysis (EDA)

To understand the structure and insights hidden in the data, we performed extensive EDA, including both visual and statistical summaries.

### 📌 Key EDA Highlights

- **Age Distribution & Impact**:
  - Histogram and Q-Q plots to assess distribution of `age`
  - Line graphs showing how account closure varies by age
  - Segmented `age` into bins using `cut()` for better granularity

- **Categorical Variable Analysis**:
  - Grouped and visualized:
    - `marital_status`
    - `education`
    - `employment_status`
    - `card_type`
  - Used **side-by-side bar charts** to show closed vs active accounts by category

- **Numerical Variable Distributions**:
  - Created **density plots** to compare:
    - `months_inactive_last_year`
    - `utilization_ratio`
    - `transactions_last_year`
  - Used `ggplot2` + `plotly` for interactive visuals

- **Summary Tables**:
  - Used `group_by` and `mutate` to calculate:
    - Percentage of account closures by demographic and behavioral groups
  - Created tables to highlight trends in customer churn


## 🛠️ Feature Engineering

We engineered new features and transformed existing ones to improve model performance.

### ✅ Steps Taken

- **Age Segmentation**:
  - Created a new variable `age_segment` using 5-year bins (e.g., 20–25, 25–30...)

- **Percentage Columns**:
  - Calculated churn percentages across demographics (e.g., closed_account_percent by age or dependents)

- **Categorical Variable Encoding**:
  - Prepared categorical variables (like `marital_status`, `education`, etc.) for modeling using appropriate encoding techniques.

- **Distribution Checks**:
  - Performed Q-Q plots to assess normality for numerical features and guide later transformations (used in statistical testing)

These engineered features were later used in statistical tests and machine learning models to improve interpretability and predictive power.


## 🧪 Statistical Testing & Hypothesis Analysis

We conducted multiple statistical tests to evaluate significant differences between customers who **closed their credit card accounts** vs those who remained **active**. These tests helped us validate assumptions and identify key variables influencing customer behavior.

### ✅ Tests Performed

| Test Type               | Variable(s)                           | Purpose                                                                 |
|------------------------|----------------------------------------|-------------------------------------------------------------------------|
| **Shapiro-Wilk Test**  | `age`, `dependents`, `income`          | Assess if numerical variables are normally distributed                 |
| **Two-Sample t-Test**  | `age`, `months_inactive_last_year`, `utilization_ratio`, `transactions_last_year` | Compare means between closed vs active groups                          |
| **Mann-Whitney U Test**| `dependents`, `income`                 | Compare medians when data is not normally distributed                   |
| **Chi-Squared Test**   | `marital_status`, `education`, `employment_status`, `card_type` vs `customer_status` | Assess independence between categorical variables and churn status     |

### 📌 Key Insights from Hypothesis Testing

- **Age** and **Utilization Ratio** showed statistically significant differences between customers who closed and retained accounts.
- Categorical variables like **Marital Status**, **Education Level**, and **Employment Status** were strongly associated with churn behavior.
- For non-normal distributions such as **income**, we used **non-parametric tests** to ensure reliable inference.
- These tests guided our **feature selection** and helped improve the interpretability of machine learning models.


## ⚙️ Machine Learning Models

The following models were trained and evaluated:

- **Logistic Regression**
- **Random Forest Regressor**
- **Linear Regression (for comparison)**
- Model evaluation using:
  - Mean Absolute Error (MAE)
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R² Score

We also applied **cross-validation** for reliable performance metrics.

## 📦 Libraries Used

- `pandas`, `numpy` – data manipulation
- `matplotlib`, `seaborn` – visualization
- `sklearn` – preprocessing, modeling, and evaluation
- `statsmodels` – statistical modeling
- `scipy` – transformations (Box-Cox, Yeo-Johnson)
- `pmdarima` – time series auto ARIMA (if needed in future)

## 📁 File Structure
├── ml_project.ipynb # Jupyter Notebook with complete code and analysis 
├── ml_project.html # HTML export of the notebook for easier viewing 
├── datalab_export_2024-08-11.csv # Dataset used for model training and analysis 
├── README.md # Project overview, methodology, and key results


### 💡 Notes:
- The `.ipynb` notebook is the main working file with EDA, statistical testing, and ML models.
- The `.html` version is useful for sharing or previewing without running the code.
- The `.csv` dataset includes raw data for preprocessing, visualization, and model input.


