# Repository Guide: Churn Analysis & Responsible Modeling

## Overview of Deliverables
This workspace contains the complete documentation and code for the customer churn evaluation task:
1. `problem_framing_memo.md`: Strategic breakdown of the machine learning scope, target definition, and baseline rules.
2. `responsible-data-card.md`: Documentation covering data provenance, feature distribution, limitations, and governance.
3. `customer_churn_baseline.ipynb`: Interactive script executing data checks, summary statistics, and preliminary baselines.
4. `risk_register.md`: Assessment of failure modes, operational risks, and safeguards (human oversight and mitigation steps).

## Dataset Usage
- `customer-churn-training.csv`: The primary tabular dataset consisting of 12 sample records. Ensure this CSV is kept in the same working directory as the Jupyter notebook prior to execution.

## Execution Notes & Guidelines
- Run the Jupyter notebook sequentially from the initial cell downward to replicate data inspections.
- Note that given the minimal sample size (12 observations), outcomes are strictly illustrative/exploratory and cannot be treated as production-ready metrics.
- Confirm any operational parameters or constraints with local project guidelines before broader implementation.
