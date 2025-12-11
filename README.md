# Customer Churn Analysis & Recommendations: Teleconnect Case Study

## 🎯 Executive Summary

This project conducts a comprehensive analysis of customer churn for a telecom provider ("Teleconnect") to identify the main drivers of customer attrition and provide actionable, data-driven recommendations for retention.

* **Overall Churn Rate:** **26.6%**
* **Key Finding:** Churn is heavily concentrated among specific, high-risk customer segments, including month-to-month contract holders, users of the Fiber Optic service, and customers paying via Electronic Check.
* **Goal:** Prioritize identifying *potential* churners (high **Recall**) to allow for effective, early intervention and retention efforts.

## 📊 Data & EDA Highlights

The analysis was performed on a dataset of **7,043 customers** with 21 features covering demographics, services, and billing information.

| Finding | Detail | Churn Rate |
| :--- | :--- | :--- |
| **Contract Type** | Month-to-month contracts account for **73% of all churn**. | 3x Higher |
| **Internet Service** | Fiber optic users have a significantly higher churn risk. | 2x Higher |
| **Payment Method** | Customers using Electronic Check are a high-risk segment. | 30% Higher |
| **Tenure** | New customers are more likely to churn, especially those with high monthly charges. | N/A |
| **Loyalty** | Long-term customers with multiple services show the highest loyalty. | N/A |

## 💻 Methodology & Modeling

### Predictive Modeling

* **Model Used:** **XGBoost** (eXtreme Gradient Boosting) or **Random Forest** classification was utilized to predict the probability of churn.
* **Performance Priority:** The model was tuned to prioritize **Recall** over Accuracy or Precision, as capturing the maximum number of true churners is critical for proactive retention strategies.
* **Model Performance:** The Random Forest model achieved **79% Accuracy**, but the **Recall for churners was 48%**, indicating a need for urgent intervention for flagged customers.

### Key Model Drivers (SHAP Analysis)

SHAP (SHapley Additive exPlanations) analysis was used to interpret the model and identify the top factors driving churn risk for individual customers:

1.  **Contract Type:** Short-term (month-to-month) is the most significant risk factor.
2.  **Monthly Charges:** Higher monthly charges drive higher churn risk.
3.  **Internet Service:** Fiber Optic service is a major churn contributor.

## 💡 Business Recommendations

Based on the analysis, the following actionable strategies are recommended to reduce churn, segmented by targeted customer groups:

### 1. Fiber Optic Retention Overhaul
* **Issue:** 31% higher churn risk for fiber users.
* **Actions:** Launch a lower-cost "Basic Fiber" tier. Bundle premium technical support services for free with all fiber plans.

### 2. Auto-Pay Adoption Campaign
* **Issue:** Electronic check users churn 30% more than others.
* **Actions:** Offer a **5% discount** for enrolling in auto-pay. Simplify setup with proactive SMS/email nudges.

### 3. Contract Conversion Incentives
* **Issue:** 73% of churn comes from month-to-month contracts.
* **Actions:** Offer a **$100 loyalty bonus** or free streaming upgrades for customers switching to 1-year contracts.

### 4. High-Risk Customer Programs
* **High-Risk Segment:** New customers with high monthly charges and the **5% of customers flagged as anomalies** by the model.
* **Actions:** Assign dedicated account managers for personalized retention efforts. Offer new high-spenders a **10% discount** off their first six months.

### 5. Real-Time Churn Alerts
* **Technical Action:** Deploy real-time alerts using the model's predictions.
* **Business Action:** Trigger instant, automated retention offers (e.g., 20% discount or service upgrade) when a customer is flagged as high-risk.

## 📂 Project Files

| File Name | Description |
| :--- | :--- |
| `Garima_Dubey_Teleconnect_case_study (3).ipynb` | The Jupyter Notebook containing the end-to-end data loading, EDA, feature engineering, and predictive model implementation. |
| `Customer Churn Analysis & Recommendations For Technical & Business Stakeholders (4).pptx` | The presentation summarizing the executive findings, model performance, SHAP analysis, and final business recommendations. |

### Technical Requirements

To execute the notebook, you will need the following Python libraries:

```bash
pandas
numpy
scikit-learn
xgboost
shap
matplotlib
