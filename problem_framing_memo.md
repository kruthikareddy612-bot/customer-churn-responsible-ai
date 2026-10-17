# Churn Intelligence & Risk Analysis – Problem Framing Memo

## 1. Business objective
Leverage churn-risk predictions to assist account management teams in prioritizing proactive customer outreach and engagement strategies. Predictions must act solely as decision support for human operators, avoiding any automated punitive actions or restrictions.

## 2. Target definition
The binary target variable is designated as `churned`. Within this dataset, `1` indicates a churned subscriber and `0` indicates retention. Validation with the data provider is recommended for broader deployments.

## 3. Scope and granularity
The dataset consists of 12 distinct rows and 7 attributes, where each record corresponds to an individual customer profile.

## 4. Evaluation and horizon
Proposed framework: utilizing snapshots of customer data to project churn probability over a 30-day forecast horizon. This is an operational assumption requiring empirical validation against historical event timelines.

## 5. Input features
Authorized predictors include `tenure_months`, `support_tickets`, `monthly_spend_inr`, `last_login_days`, and `plan_type`. `customer_id` is excluded to prevent unintended memorization, and `churned` is strictly reserved as the target label.

## 6. Baseline model
A heuristic benchmark rule flagging accounts with `last_login_days >= 15` or `support_tickets >= 3` will serve as the non-ML baseline, compared against a majority-class predictor.

## 7. Cost matrix and performance metrics
False positives risk allocating unnecessary retention incentives to loyal customers, whereas false negatives result in missed opportunities to save at-risk accounts. Evaluation should prioritize Precision, Recall, F1-Score, and confusion matrix analysis over raw accuracy.

## 8. Constraints and observations
With only 12 observations, findings remain strictly exploratory. Generalization to production environments requires expanding the sample size and verifying data provenance.