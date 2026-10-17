# Responsible Data Card: Customer Churn Evaluation

## Dataset purpose
* **Supported Decisions:** This dataset is intended for educational modeling practice, exploratory data analysis, and benchmarking binary classification pipelines for subscriber retention.
* **Prohibited Decisions:** It must not be used to execute automated punitive measures, service terminations, or discriminatory pricing against actual consumers. Given its micro-scale (12 records), it is strictly unsuitable for live production deployment.

## Provenance and permission
* **Data Origin:** Sourced via the RabTech Academy coursework repository (`customer-churn-training.csv`).
* **Creator & Licensing:** Original authorship and explicit licensing terms remain unspecified within the dataset schema. 
* **Consent Status:** Privacy compliance and user consent documentation are absent. 
* **Action Item:** Verify generation methods and usage rights with the curriculum administrators prior to any external distribution or publication.

## Population and representation
* **Demographic Scope:** Contains 12 customer observations across three subscription tiers (`Basic`, `Standard`, `Pro`).
* **Class Distribution:** Comprises 7 retained accounts (`churned = 0`) and 5 churned accounts (`churned = 1`).
* **Sampling Limitations:** Due to the extremely small sample size, the dataset lacks statistical representation of a wider subscriber base, preventing generalized demographic or behavioral conclusions.

## Features and target
* **Target Variable:** `churned` (Binary indicator where `1` represents churn and `0` represents retention).
* **Predictor Features:** 
  * `tenure_months`: Subscription duration in months.
  * `support_tickets`: Logged customer service inquiries.
  * `monthly_spend_inr`: Monthly expenditures in Indian Rupees.
  * `last_login_days`: Inactivity duration measured in days since last login.
  * `plan_type`: Subscription tier category.
* **Excluded / Leakage Risks:** `customer_id` must be dropped prior to training to avoid unintended identifier memorization. `churned` must never be used as an input feature.

## Quality checks
* **Missingness & Duplicates:** Programmatic inspection confirms zero missing cells and no identical duplicate rows.
* **Train/Test Partitions:** Traditional train-test splitting is unfeasible given the 12-row constraint; models trained here will experience severe overfitting.
* **Data Integrity:** Numerical ranges fall within logical bounds, though categorical consistency requires validation against an official data dictionary.

## Risks and safeguards
* **Overfitting & Generalization Risk:** High probability of memorizing noise rather than learning robust patterns. *Mitigation:* Treat strictly as a sandbox template; scale up to hundreds or thousands of representative records before advancing models.
* **False Positives / Negatives:** Erroneously flagging loyal users risks incurring unnecessary retention discounts, while missing true churners loses revenue opportunities. *Mitigation:* Mandate human-in-the-loop review before dispensing costly incentives.

## Intended evaluation
* **Baseline Strategies:** Compare machine learning models against a simple majority-class baseline and heuristic inactivity rules (e.g., flagging accounts when `last_login_days >= 15`).
* **Performance Metrics:** Evaluate using Precision, Recall, F1-Score, and confusion matrices rather than relying on misleading raw accuracy metrics.
* **Error Analysis:** Conduct qualitative reviews of false classifications to understand model boundary failures.
