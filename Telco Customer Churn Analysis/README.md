# Telco Customer Churn Analysis & Retention Strategy

##  Project Objective
The objective of this analysis was to identify the key drivers of churn within the Telco dataset and engineer features that isolate high-risk behaviors. By analyzing **7,043 customers**, we discovered that churn is not random but heavily influenced by contract structure, payment methods, and specific demographic risks.

---

##  1. Data Engineering & Risk Identification
To move beyond raw data, several "risk-indicator" features were developed to better predict customer behavior:

* **Commitment Strength**: Created a `long_contract` flag for one- and two-year agreements to measure customer loyalty.
* **Financial Risk**: Developed `price_vs_median` and `services_per_dollar` to determine if high charges relative to service count drive customers away.
* **Senior Citizen Vulnerability**: Engineered a `senior_risk` feature that specifically identifies senior citizens on month-to-month contracts.
* **Frictionless Billing**: Created an `auto_payment` indicator to analyze how automatic billing reduces the "pain of paying" and prevents churn.

---

##  2. Key Findings (The "Why" Behind Churn)
Exploratory Data Analysis (EDA) revealed critical insights into why customers leave:

| Risk Factor | Statistical Result |
| :--- | :--- |
| **Contract Type** | **Month-to-month** customers have a **42.7%** churn rate, while **Two-year** contract holders churn at only **2.8%**. |
| **Payment Method** | Customers using **Electronic Checks** are the highest risk, with a **45.3%** churn rate. |
| **Senior Risk** | Customers flagged under the new `senior_risk` feature churn at **54.6%**, more than double the average. |
| **Billing Type** | **Manual payment** users churn at **34.7%**, compared to only **16.0%** for those on **Auto-pay**. |

---

##  3. Strategic Recommendations for Retention
Based on these data-driven results, the following retention programs are recommended:

### Contract Conversion Incentives
Since month-to-month users represent the highest churn volume, the business should offer a **"Loyalty Discount"** for customers who transition to a 1-year or 2-year contract.

###  Targeted Senior Support
The **54.6% churn rate** for seniors on flexible plans suggests a need for a dedicated **"Senior Value Plan."** This plan should combine security features with discounted long-term rates to provide financial stability for those on fixed incomes.

###  Auto-Pay Migration
Because auto-payment reduces churn by over half, we recommend a campaign to move **"Electronic Check"** users to **"Automatic Bank Transfer"** by offering a one-time bill credit.

###  Service Bundling
Analysis shows that as the number of services (`num_services`) increases, churn generally decreases. Promoting **"Streaming Bundles"** or technical add-ons to single-service users will increase customer "stickiness" and brand ecosystem integration.

---

##  Tech Stack Used
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, XGBoost, SHAP
* **Dataset:** IBM Sample Data Sets (Telco Customer Churn)
