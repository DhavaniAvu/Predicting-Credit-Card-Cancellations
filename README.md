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

## 📊 Data Exploration & Preprocessing

We performed:
- **Exploratory Data Analysis (EDA)** using Seaborn and Matplotlib.
- **Missing value treatment** and **outlier detection**.
- **Feature scaling** using StandardScaler and MinMaxScaler.
- **Encoding** of categorical variables.
- 
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


