# 📉 Telco Customer Churn Analysis — Excel

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle%20Telco%20Churn-20BEFF?style=flat&logo=kaggle&logoColor=white)
![Rows](https://img.shields.io/badge/Records-7%2C043%20customers-lightgrey?style=flat)

## 📌 Project Overview

This project analyzes customer churn behavior for a fictional telecommunications company using the [Telco Customer Churn dataset from Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn). The goal is to identify **who is churning, why they're leaving, and how much revenue is at risk** — framed as a business problem, not just a data exercise.

The entire analysis was built in Microsoft Excel, covering data cleaning, feature engineering, KPI modeling, pivot analysis, and scenario planning.

---

## 🗂️ Workbook Structure

| Sheet | Description |
|---|---|
| `Raw` | Original dataset as sourced from Kaggle (7,043 rows × 21 columns) |
| `Clean Model` | Cleaned data with 8 engineered columns added for analysis |
| `KPIs` | Summary metrics including churn rate, ARPU, revenue at risk, and a what-if scenario model |
| `Pivots` | Breakdown tables by contract type, payment method, internet service, tenure band, and add-on score |
| `Insights` | Key findings and business takeaways |

---

## 🛠️ Feature Engineering

Eight new columns were added to the clean model to enable deeper analysis:

| Column | Logic |
|---|---|
| `Total Charges Clean` | Handles blank/null values in `TotalCharges` using `TRIM` + `IF` |
| `Churn Flag` | Binary 1/0 encoding of the `Churn` column |
| `Tenure Band` | Bucketed tenure into: 0–11, 12–23, 24–47, 48–59, 60+ months |
| `Payment Type` | Simplified to Auto-Pay vs. Manual using `SEARCH` |
| `Internet Type` | Cleaned `InternetService` to handle "No Internet" as a category |
| `ADD On Protection Score` | Count of active protection add-ons per customer (0–4) |
| `Revenue at Risk` | Monthly charges of churned customers only; 0 for retained |
| `High Risk Tag` | Flags customers meeting all 4 criteria: Month-to-month contract + Manual payment + Tenure < 12 months + Fiber optic or charges ≥ $80 |

---

## 📊 Key KPIs

| Metric | Value |
|---|---|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Overall Churn Rate | ~26.5% |
| Retention Rate | ~73.5% |
| Monthly Revenue | ~$456K |
| Monthly Revenue at Risk (from churned customers) | ~$139K |
| Early-Life Churn Rate (0–11 months) | ~48.3% |
| High Risk Churn Rate | Significantly elevated vs. base rate |

---

## 🔍 Pivot Analysis Highlights

**Churn by Contract Type**
| Contract | Customers | Churned | Churn Rate |
|---|---|---|---|
| Month-to-month | 3,875 | 1,655 | ~42.7% |
| One year | 1,473 | 166 | ~11.3% |
| Two year | 1,695 | 48 | ~2.8% |

**Churn by Payment Method**
| Payment Type | Customers | Churned | Churn Rate |
|---|---|---|---|
| Manual | 3,977 | 1,379 | ~34.7% |
| Auto-Pay | 3,066 | 490 | ~16.0% |

**Churn by Internet Service**
| Service | Customers | Churned | Churn Rate |
|---|---|---|---|
| Fiber optic | 3,096 | 1,297 | ~41.9% |
| DSL | 2,421 | 459 | ~19.0% |
| No Internet | 1,526 | 113 | ~7.4% |

**Add-On Protection Score vs. Churn**

Customers with more protection add-ons (security, backup, device protection, tech support) churn at significantly lower rates — from ~29.8% at score 0 down to ~5.3% at score 4. This suggests add-ons act as a strong retention lever.

**Early-Life Churn (Tenure Band)**

Nearly half of all customers who leave do so within their first 11 months (~48.3% churn rate), highlighting onboarding and early engagement as critical intervention points.

---

## 💡 Business Insights

1. **Month-to-month contracts are the primary churn driver** — over 88% of all churned customers were on flexible contracts. Converting even a fraction to annual contracts would significantly reduce churn.

2. **Manual payment customers churn at 2x the rate of auto-pay customers** — nudging customers toward automatic billing could reduce involuntary and habitual churn.

3. **Fiber optic customers churn at 42%** — despite being the premium internet tier, these customers are the most dissatisfied. This is a product-quality or pricing signal worth investigating.

4. **Add-ons are a retention mechanism** — customers with 3–4 protection add-ons churn at under 13%. Cross-selling add-ons during onboarding has measurable retention value.

5. **The first year is the most critical** — with a ~48% churn rate in months 0–11, targeted intervention (e.g., loyalty discounts, proactive support) during the onboarding phase has the highest ROI.

---

## 🔮 Scenario Model: What-If Analysis

A built-in scenario model in the `KPIs` sheet estimates the revenue impact of reducing high-risk customer churn. By setting a target churn reduction %, the model calculates:

- Estimated **monthly revenue saved**
- Estimated **annual revenue saved**
- High-risk segment's **share of total revenue at risk**

---

## 📁 Files

| File | Description |
|---|---|
| `Customer Churn Analysis.xlsx` | Full Excel workbook with raw data, clean model, KPIs, pivots, and insights |

---

## 🔗 Data Source

- **Dataset:** [Telco Customer Churn — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Original Source:** IBM Sample Data Sets

---

## 👤 Author

**Angad**
- GitHub: [@angad-s16](https://github.com/angad-s16)
