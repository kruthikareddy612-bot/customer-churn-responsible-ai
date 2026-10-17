# ML Problem-Framing Memo: Customer Churn Prediction

## Overview
* **Decision:** Identify at-risk subscribers for proactive retention outreach.
* **Prediction Target:** `churned` (Binary: `1` for churned, `0` for retained).
* **Action Window:** Next 30 days.
* **Non-ML Baseline:** Rule-based trigger (e.g., if `last_login_days > 14` or `support_tickets >= 3`, flag as churn risk).

---

## Risk Register

| Risk Category | Description | Severity | Mitigation |
| :--- | :--- | :--- | :--- |
| **Overfitting** | Model memorizes patterns from only 12 rows. | High | Treat dataset as a sandbox template; scale up dataset before production. |
| **False Positives** | Giving costly retention discounts to loyal customers. | Medium | Require human review before issuing expensive rewards. |
| **Data Bias** | Sample size is too small to represent real-world subscriber tiers. | High | Collect hundreds of stratified customer records. |