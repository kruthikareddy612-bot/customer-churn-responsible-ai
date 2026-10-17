# Responsible Data Card: Customer Churn Prediction

## Dataset purpose
* **Supported Decisions:** Exploratory data analysis, pattern recognition, and training binary classification models to predict customer churn.
* **Prohibited Decisions:** Automated punitive actions, account termination, or discriminatory pricing against individual customers.

## Provenance and permission
* **Creation & Source:** Curated training dataset (`customer-churn-training.csv`) containing 12 records.
* **Usage & Licensing:** Intended strictly for educational and prototyping purposes.

## Population and representation
* **Represented Groups:** Active and churned subscribers across `Basic`, `Standard`, and `Pro` tiers.
* **Known Limitations & Imbalance:** Extremely small sample size (**12 rows**), consisting of 7 retained and 5 churned samples. High risk of overfitting.

## Features and target
* **Target Label:** `churned` (Binary: `1` = Churned, `0` = Retained).
* **Features:** `customer_id`, `tenure_months`, `support_tickets`, `monthly_spend_inr`, `last_login_days`, `plan_type`.

## Quality checks
* **Missingness & Duplicates:** Zero missing values and zero duplicate `customer_id` entries.
* **Class Balance:** 58.3% retained (class 0) and 41.7% churned (class 1).
* **Train/Test Separation:** Traditional train/test splits are impractical due to the 12-row sample size; cross-validation or data augmentation is required before production use.

## Risks and safeguards
* **Risks:** Severe overfitting and potential false positives/negatives in churn prediction.
* **Mitigations:** Keep as a sandbox template; scale up to hundreds or thousands of rows before deploying models to production.

## Intended evaluation
* **Baselines & Metrics:** Use rule-based thresholds (e.g., `last_login_days > 14`) as a baseline. Evaluate using Accuracy, Precision, Recall, and F1-score.
*