# Case Study Project:FNB Customer Churn Prediction & Retention Analytics
<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green.svg)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-yellow.svg)
![Machine Learning](https://img.shields.io/badge/ML-Predictive%20Analytics-red.svg)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)

**Saving R578.5M in At-Risk Customer Lifetime Value Through Predictive Analytics**
</div>

---
## Executive Summary

**Context**: This project transforms a European bank customer dataset into a South African retail banking case study, positioning it as an FNB churn prediction and retention optimization initiative. I re-engineered the original 10,000-customer dataset to reflect SA market conditions—localizing geography, currency, products, and digital banking behaviors—creating a realistic foundation for advanced analytics.

**Business Problem**: FNB faced a customer retention crisis with 20.4% annual churn, representing R578.5M in at-risk customer lifetime value. Traditional reactive retention strategies lacked predictive capability to identify high-risk customers or quantify revenue exposure across segments.

**Solution**: I developed an end-to-end churn prediction pipeline combining statistical analysis, feature engineering, and machine learning to build actionable risk profiles. The solution delivers executive dashboards, customer-level risk scores, and intervention prioritization frameworks designed for business stakeholders.

**Impact**: The model achieves 1.72x lift in identifying high-risk customers compared to random selection, quantifies R578.5M in revenue exposure, and projects 1,604% ROI on targeted retention programs. Deliverables include predictive models, Power BI dashboards, and a five-pillar retention strategy with measurable financial outcomes.

![Project Overview](./assets/project_overview.png)
*End-to-end analytics pipeline: data transformation → EDA → predictive modeling → business intelligence dashboards*

---

## Problem Statement

**The Challenge**

One in five FNB customers churn annually with no predictive visibility into which customers will leave or why. This creates unquantified revenue leakage, inefficient retention spending, and missed opportunities to protect high-value relationships.

**Business Objectives**

- Quantify financial exposure from customer churn across segments
- Identify high-impact churn drivers to focus retention investments
- Build predictive risk model to enable proactive interventions
- Develop actionable segmentation for targeted retention programs

**Success Criteria**

- Reduce overall churn from 20.4% to <18% within 6 months
- Achieve 1.5x+ lift in identifying high-risk customers vs random selection
- Generate ROI >300% on retention program investments

---

## Stakeholders & Decision Framework

This project serves C-suite executives (CCO, CFO, CDO), retention marketing teams, product managers, branch operations, and wealth management. The model enables data-driven retention decisions with clear accountability for revenue protection and ROI.

```mermaid
graph TD
    A[Data Science Team] -->|Insights & Predictions| B[Retention Committee]
    B -->|Strategic Direction| C[CCO / Executive Team]
    C -->|Budget Approval| D[Implementation Teams]
    D -->|Campaign Execution| E[Branch Operations]
    D -->|Product Changes| F[Product Management]
    D -->|VIP Outreach| G[Wealth Management]
    E -->|Performance Data| A
    F -->|Performance Data| A
    G -->|Performance Data| A
```

---

## Data & Context

**Source**: Bank Customer Churn Prediction Dataset (Kaggle) by Saurabh Badole

**Transformation**: I re-engineered the European dataset to reflect South African banking conditions:
- Geographic localization (9 SA provinces, 45 cities)
- Currency conversion (EUR → ZAR)
- Cultural features (11 official SA languages)
- Product portfolio (SA banking products: savings, cheque, credit cards, home loans, vehicle finance)
- Digital engagement (mobile banking 80.6%, internet banking 70.0%)

**Dataset Specifications**:
- 10,000 customer records
- 43 variables (demographics, banking, products, financial, engagement)
- 20.4% churn rate (2,037 churned customers)
- No missing values, no duplicates

**Purpose**: Portfolio project demonstrating data localization, feature engineering, and business impact quantification for SA banking market.

---

## Analytical Approach

**Exploratory Data Analysis**
- Univariate and bivariate analysis across 43 features
- Statistical hypothesis testing (t-tests, chi-square) to validate churn drivers
- Effect size calculations (Cohen's d) for practical significance assessment
- Customer segmentation by value, risk, and behavioral cohorts
- Revenue exposure quantification using CLV methodology

**Critical Findings**:
- Age as primary churn predictor: 50.6% churn in 46-55 cohort vs 20.4% baseline (t=29.77, p<0.0001)
- Product complexity paradox: 2 products optimal (7.6% churn), 3-4 products failure mode (83-100% churn)
- Geographic concentration: 2.2x churn variation across provinces (χ²=307.99, p<0.0001)
- Personal loan product risk: 85.9% churn rate requiring immediate intervention
- Gender-based churn disparity: 8.6pp gap (female 25.1% vs male 16.5%, p<0.0001)

All findings validated with α=0.05 significance threshold and medium-to-large effect sizes.

![EDA Key Insights](./assets/eda_key_insights.png)
*Statistical validation of churn drivers: age cohorts, product complexity, geographic patterns, and financial segmentation*

![Age Cohort Analysis](./assets/age_cohort_churn.png)
*Age-based churn distribution showing critical 46-55 cohort with 50.6% churn rate—244% higher than baseline*

![Product Complexity](./assets/product_complexity_ushape.png)
*U-shaped churn curve demonstrating optimal engagement at 2 products and catastrophic failure at 3-4 products*

![Geographic Heatmap](./assets/geographic_churn_heatmap.png)
*Provincial churn rates: Limpopo (34%), Eastern Cape (32%), Mpumalanga (31%) require targeted interventions*

---

## Modeling & Risk Profiling

**Feature Engineering**

I engineered 25+ predictive features based on EDA insights:
- Age-based risk indicators (cohort flags, polynomial transformations)
- Product complexity metrics (optimal vs over-banked customer identification)
- Engagement scoring (digital adoption, service interaction frequency, complaint ratios)
- Geographic risk stratification (high-churn province indicators)
- Financial health ratios (balance-to-salary, wealth concentration indices)
- Customer lifetime value projections (5-year revenue forecasts)

**Composite Risk Scoring Model**

Developed weighted risk algorithm combining:
- Age risk (30% weight)
- Product portfolio risk (25% weight)
- Engagement & activity risk (20% weight)
- Geographic & competitive risk (15% weight)
- Financial profile risk (10% weight)

**Customer Segmentation**:
- Low Risk: 14.5% of base, 4.8% churn rate
- Medium Risk: 45.2% of base, 12.4% churn rate
- High Risk: 33.1% of base, 29.6% churn rate
- Critical Risk: 7.1% of base, 60.3% churn rate

**Model Validation**: 1.72x lift in high-risk identification vs random selection, enabling efficient targeting of retention resources.

![Risk Segmentation](./assets/risk_segmentation_distribution.png)
*Customer distribution across risk tiers with corresponding churn rates and revenue exposure quantification*

**Predictive Modeling**

Trained ensemble of classification algorithms:
- Logistic Regression (interpretable baseline)
- Decision Tree (non-linear baseline)
- Random Forest (200 estimators, max_depth=15)
- XGBoost (gradient boosting, learning_rate=0.1)
- LightGBM (optimized for deployment efficiency)

Model selection criteria: ROC-AUC, precision-recall trade-off, business cost function optimization.

**Champion Model**: XGBoost
- ROC-AUC: 0.86
- Precision: 0.78
- Recall: 0.72
- F1-Score: 0.75

![Model Comparison ROC](./assets/model_comparison_roc_curves.png)
*ROC curves for all candidate models—XGBoost achieves best AUC (0.86) with optimal precision-recall balance for business use case*

![Confusion Matrix](./assets/confusion_matrix_xgboost.png)
*XGBoost confusion matrix on test set: correctly identifies 72% of churners while maintaining 78% precision to minimize false positives*

![Feature Importance](./assets/feature_importance_top20.png)
*Top 20 predictive features ranked by SHAP importance: age, product count, activity status, and balance dominate churn signal*

**Deployment Design**: Monthly batch scoring of customer base with automated risk tier assignment and intervention workflow triggers.

---

## Business Impact

**Revenue Quantification**

- R578.5M customer lifetime value at risk across churning cohorts
- R738M revenue protected through targeted intervention programs
- 1,604% projected ROI on retention campaign portfolio
- R110.5M annual CLV preservation at 12-month retention target

**Strategic Retention Framework**

Five-pillar intervention strategy with measurable ROI:
1. Age-targeted programs (46-55 cohort): R74M CLV protected, 465% ROI
2. Geographic market interventions (high-churn provinces): R730M balances retained, 4,866% ROI
3. Product portfolio optimization (personal loan review, cross-sell re-engineering)
4. VIP relationship management (white-glove service for top-tier customers): R44M CLV protected, 230% ROI
5. ML-powered early warning system (automated intervention triggers by risk tier)

**Business Intelligence Dashboards**

Developed Power BI analytics suite (400+ DAX measures) for multi-stakeholder decision support:

**Executive Churn Overview Dashboard**
- Real-time KPIs: churn rate trends, CLV exposure, customer counts
- 12-month trend analysis with moving averages and benchmark targets
- Provincial risk heatmaps and value segment distribution

![Executive Dashboard](./assets/dashboard_executive_overview.png)
*C-suite dashboard: churn trends, CLV at risk, and provincial performance—enables strategic resource allocation*

**Customer Risk Profile Dashboard**
- High-risk customer tables with sortable risk scores and churn probabilities
- Intervention tracking by risk tier with conversion rate analytics
- Driver analysis showing feature contributions to individual customer risk

![Risk Profile Dashboard](./assets/dashboard_risk_profile.png)
*Operational tool for retention teams: prioritized customer lists, intervention tracking, and real-time campaign performance*

**Product & Engagement Analytics Dashboard**
- Product-level churn rates and penetration-retention matrices
- Cross-sell opportunity scoring and next-best-product recommendations
- Tenure cohort analysis and customer lifecycle survival curves

![Product Dashboard](./assets/dashboard_product_analytics.png)
*Product performance insights: identifies optimal product bundles and flags high-risk product combinations for portfolio review*

**Geographic & Demographic Intelligence Dashboard**
- Branch-level performance with city and province drill-down
- Market opportunity quadrants (customer volume vs churn rate)
- Demographic churn patterns by age, gender, education, and employment

![Geographic Dashboard](./assets/dashboard_geographic_intelligence.png)
*Regional strategy tool: maps market-specific churn drivers and ROI potential for geographic expansion or consolidation*

**Implementation Roadmap**

Phased 12-month deployment:
- Q1: Quick wins (personal loan review, VIP program launch, high-risk province pilots)
- Q2: ML model deployment and automated scoring infrastructure
- Q3: Full-scale retention campaigns with A/B testing
- Q4: Model retraining and performance optimization

Quarterly model retraining with new churn observations ensures sustained predictive accuracy.

---

## Tools & Stack

**Data Analysis**
- Python (Pandas, NumPy, SciPy, Statsmodels)
- Jupyter Notebooks

**Visualization**
- Matplotlib, Seaborn, Plotly
- Power BI (DAX, M Query)

**Machine Learning**
- Scikit-learn
- XGBoost
- LightGBM

**Feature Engineering**
- Custom risk scoring algorithms
- Customer segmentation frameworks
- CLV modeling

**Documentation**
- Markdown
- Mermaid (decision frameworks)

---

## Repository Structure

```
fnb-churn-prediction/
├── data/                    # Raw and processed datasets
├── notebooks/               # EDA, feature engineering, modeling
├── src/                     # Production code (data, features, models)
├── models/                  # Trained model artifacts
├── dashboards/              # Power BI files and DAX formulas
├── reports/                 # Analysis report, visualizations
└── README.md
```

---

## Author

**Timothy [Last Name]**  
Data Scientist | Machine Learning Engineer  
[LinkedIn](#) | [GitHub](#) | [Email](#)

---

**Dataset Attribution**: Original dataset by Saurabh Badole on Kaggle. Transformed for SA banking context as portfolio demonstration.

**Last Updated**: December 2024

