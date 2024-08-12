# -Analysis of Credit Card Account Closures-
This file contains a project of predicting credit card cancellations using R programming.

This project aimed to analyze the factors influencing credit card account closures to enhance customer retention strategies. The objective was to pinpoint key variables linked to account closures, evaluate the performance of predictive models, and offer actionable recommendations to the bank for reducing customer churn.

## About the dataset
The credit_card_df data frame contains information on the customers of a large U.S. bank which provides a number of financial services including multiple credit card offerings.

The bank is looking to see if it can determine the factors that lead to customers canceling their credit card account and whether it can predict if a customer will cancel their account in the future.

To maintain profits, banks must maximize the number of customers with credit lines. It is also in their best interests for customers to carry large credit card balances from month-to-month to maximize revenue from interest charges.

The bank has experienced record levels of customers closing their credit accounts in the past couple of years and this is leading to declining revenue.

The bank's goal is to become better at identifying customers at risk of canceling their account to minimize financial losses.
The data set contains a mixture of customer demographics and their financial behavior.

The outcome variable in this data is customer_status. This variable records whether a customer eventually closed their account and indicates a financial loss to the company.



## Data Definitions

| Variable            	     | Definition                                 	                | Data Type    |
|:---------------------------|:-------------------------------------------------------------|:-------------|
| customer_status            | Customer status (closed account or active)                   | Factor       |
| age                        | Customer age                                                 | Numeric      |
| dependents                 | Number of dependents in household                            | Numeric      |
| education                  | Customer education level                                     | Factor       |
| marital_status             | Marital status                                               | Factor       |
| employment_status          | Employment status                                            | Factor       |
| income                     | Annual income (US Dollars)                                   | Numeric      |
| card_type                  | Type of credit card                                          | Factor       |
| months_since_first_account | Months since first credit card account activated             | Numeric      |
| total_accounts             | Total accounts (credit checking and savings)                 | Numeric      |
| months_inactive_last_year  | Months without credit card activity last year                | Numeric      |
| contacted_last_year        | Number of times contacted last year by sales representatives | Numeric      |
| credit_limit               | Current credit limit                                         | Numeric      |
| utilization_ratio          | Average monthly balance to credit limit                      | Numeric      |
| spend_ratio_q4_q1          | Ratio of total Q4 to Q1 spending last year                   | Numeric      |
| total_spend_last_year      | Total amount charged last year                               | Numeric      |
| transactions_last_year     | Number of transactions last year                             | Numeric      |
| transaction_ratio_q4_q1    | Ratio of total Q4 to Q1 transactions last year               | Numeric      |

## Research Questions

 What factors are linked to customers closing their credit card accounts?
 Can we accurately predict whether a customer will close their account?
 What measures or policies can the bank implement to minimize the risk of customer loss?
 Tools and Technologies Used

## Programming Languages: 
R Programming
## Data Manipulation and Analysis: 
dplyr, tidyr
## Machine Learning: 
Logistic regression, decision trees, random forests
## Model Evaluation:
ROC curve, accuracy, AUC-ROC
## Visualization: 
ggplot2

## Analysis and Techniques
The analysis employed several models to predict credit card account closures and evaluate their performance:
### Logistic Regression:
Identified crucial variables affecting account closures and achieved a model accuracy of 80% with a ROC AUC above the baseline.
### Decision Tree: 
Provided insights into decision points influencing account closures, with a high accuracy of 89.35% and a ROC AUC of 91.51% across cross-validation folds.
### Random Forest: 
Demonstrated robust performance with a high accuracy of 95.06% and a ROC AUC of 98.96%, requiring minimal hyperparameter tuning.

## Outcomes and Insights
The analysis identified several factors associated with credit card account closures, such as part-time employment status, card type, frequency of customer care interactions, utilization ratio, and total spending. The models showed strong predictive performance, with the Random Forest model delivering the highest accuracy and ROC AUC. Key recommendations include targeted retention strategies for part-time employees, enhancing card benefits, proactive customer service, and promoting card usage.

## Recommendations
Targeted Retention for Part-Time Employees: Develop personalized strategies to cater to the specific needs of part-time employees.
Enhance "Blue" Card Benefits: Improve the benefits and features of the "blue" card to lower closure rates.
Proactive Customer Service: Implement solutions to address frequent customer service interactions and prevent dissatisfaction.
Promote Card Utilization: Launch campaigns with incentives and rewards to increase card usage.
Optimize Credit Limit Management: Dynamically adjust credit limits based on individual behavior and creditworthiness.
Periodic Card Feature Enhancement: Regularly review and enhance card features to remain competitive and retain customers.

## Please refer the ipynb python file or the html file for the clear analysis and code. 
