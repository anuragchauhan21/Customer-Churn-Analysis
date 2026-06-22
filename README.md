# Retention Risk Analysis

## Overview

This project analyzes telecom customer churn from both customer-risk and revenue-risk angles. The goal is to identify which customers are more likely to leave, understand the major churn drivers, and estimate which customer groups can create higher monthly revenue exposure.

## Interactive Power BI Dashboard

<p align="center">
  <img src="assets/dashboard_preview.png" alt="Power BI Dashboard" width="900">
</p>

> This dashboard visualizes churn patterns, customer risk levels, and revenue at risk using insights from the ML model.  
> It highlights key KPIs, contract-wise losses, churn probability distribution, and high-value high-risk customers to support data-driven retention decisions.

## Approach & Tech Stack

**Project Flow:**  
Data Preparation → Churn Analysis → Model Building → Risk Scoring → Revenue Impact → Power BI Dashboard

**Tools Used:**  
`Python`, `Pandas`, `NumPy`, `Scikit-learn`, `Power BI`

**Models Used:**  
`Logistic Regression`, `Decision Tree`

## Modeling & Evaluation

Built classification models to predict customer churn using `Logistic Regression` and `Decision Tree`.

Key features used in the model included contract type, tenure, monthly charges, total charges, payment method, internet service, and service usage.

`Logistic Regression` was selected as the final model because it gave better `recall and a balanced F1-score`. In churn analysis, recall is important because missing a likely churn customer can mean missing a retention opportunity.  

### Model Performance  

| Model                | Accuracy | Precision | Recall | F1-Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | 0.750    | 0.518     | 0.826  | 0.636    |
| Decision Tree       | 0.745    | 0.512     | 0.791  | 0.622    |

Logistic Regression performed better with higher recall and overall balanced performance, so it was selected as the final model. The model was used to assign churn probabilities, identify high-risk customers (>0.6), and estimate revenue at risk.

## Key Findings

#### Who is Leaving
- About **26.54% of customers** are leaving.  
- **Senior citizens** and **month-to-month contract customers** leave more often.  
- Customers paying by **electronic check** are more likely to leave.  
- Churn happens mostly in the **first few months** of their subscription.  
- Customers with **0–3 services** leave more often, while customers with **6 or more services** usually stay.

#### Revenue Exposure

The model was used to estimate risk-weighted monthly revenue exposure.

Risk-weighted exposure combines monthly charges with churn probability. It does not mean the company will definitely lose this amount. It shows where revenue is more exposed to churn risk.

- Estimated risk-weighted monthly revenue exposure is around **₹2,13,073**.
- High-value customers contribute around **₹1,51,890** of this exposure.
- **Month-to-month** contracts have the highest churn risk and expected exposure.

#### Factors Affecting Churn
- **More likely to leave:** high monthly bills, high total charges, using internet services, not having online backup.  
- **Less likely to leave:** long-term contracts, tech support, phone service, longer tenure, online security.

## Recommendations
- Focus on **month-to-month customers** to reduce the largest possible loss.  
- Pay attention to **high-value customers** with high risk.  
- Encourage customers to use **more services** like online backup and tech support.  
- Offer **discounts or incentives** to customers with high bills.  
- Engage **customers early** in their first months to prevent churn.

## Impact
- Identified customer groups with higher churn risk.
- Connected churn probability with **monthly revenue** to estimate revenue exposure.
- Created a **high-value high-risk** customer view for retention priority.
- Supported the Power BI dashboard with model-based churn risk and revenue impact.

Project by [**Anurag Chauhan**](https://www.linkedin.com/in/theanuragchauhan/)
