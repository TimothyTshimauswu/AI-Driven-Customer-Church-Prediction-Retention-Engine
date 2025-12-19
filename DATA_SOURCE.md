# Dataset Attribution & Transformation

## Original Dataset Source

**Dataset Name**: Bank Customer Churn Prediction Dataset  
**Author**: Saurabh Badole  
**Platform**: Kaggle  
**URL**: https://www.kaggle.com/datasets/saurabhbadole/bank-customer-churn-prediction-dataset  
**Download Date**: [Your download date]  
**Original License**: Please refer to Kaggle dataset page for licensing terms

## Dataset Description

### Original Context
The original dataset represents a European banking institution's customer base with approximately 10,000 customer records. The dataset includes demographic information, account details, product holdings, and churn status.

### Original Features
- Customer demographics (age, gender, geography)
- Banking information (credit score, account balance, tenure)
- Product holdings (number of products)
- Engagement metrics (active member status)
- Target variable (churn/exit status)

## Transformation to South African Context

### Motivation
This project adapts the original European dataset to reflect a South African banking context to:
1. **Increase Relevance**: Make the analysis applicable to South African banking market
2. **Add Regional Complexity**: Introduce province-level and city-level geographic granularity
3. **Cultural Context**: Incorporate South African languages and demographics
4. **Local Banking Focus**: Frame analysis around FNB (First National Bank), one of SA's "Big Four" banks
5. **Portfolio Differentiation**: Demonstrate data localization and domain adaptation skills

### Transformation Details

#### 1. Geographic Localization
**Original**: European countries (France, Spain, Germany)  
**Transformed**: 
- **9 South African Provinces**: Gauteng, Western Cape, KwaZulu-Natal, Eastern Cape, Limpopo, Mpumalanga, North West, Free State, Northern Cape
- **45 Cities**: Including Johannesburg, Cape Town, Durban, Pretoria, Port Elizabeth, Bloemfontein, Polokwane, Nelspruit, etc.
- **Area Types**: Urban, Suburban, Rural

**Mapping Logic**:
- High-density regions → Gauteng, Western Cape
- Coastal regions → Western Cape, KwaZulu-Natal, Eastern Cape
- Rural areas → Limpopo, Mpumalanga, Northern Cape
- Distribution preserved original statistical patterns

#### 2. Currency Conversion
**Original**: EUR (Euros)  
**Transformed**: ZAR (South African Rand)

**Conversion Methodology**:
- Exchange rate applied: ~1 EUR = 20 ZAR (approximate 2024 rate)
- Fields converted:
  - Balance → Balance_ZAR
  - EstimatedSalary → AnnualSalary_ZAR, MonthlySalary_ZAR
- Realistic salary ranges for SA market:
  - Entry level: R200K - R600K annually
  - Mid-level: R600K - R1.5M annually
  - Senior/Executive: R1.5M - R5M+ annually

#### 3. Banking Institution Context
**Original**: Generic European bank  
**Transformed**: FNB (First National Bank)

**Rationale**:
- FNB is one of South Africa's "Big Four" banks (alongside Standard Bank, Absa, Nedbank)
- Market leader in digital banking innovation
- Extensive branch network across all provinces
- Relevant for SA-based portfolio and job applications

#### 4. Cultural & Linguistic Features
**Added Features**:
- **PreferredLanguage**: 11 official South African languages
  - English, Afrikaans, isiZulu, isiXhosa, Sesotho, Setswana, Sepedi, siSwati, Tshivenda, Xitsonga, isiNdebele
- **Language Distribution**: Reflective of SA demographics
  - English: ~25% (urban, business language)
  - Afrikaans: ~20% (Western Cape, Northern Cape concentration)
  - isiZulu: ~16% (KwaZulu-Natal, Gauteng)
  - isiXhosa: ~10% (Eastern Cape, Western Cape)
  - Other languages: Regional concentrations

#### 5. Enhanced Product Portfolio
**Original**: Basic product holdings  
**Expanded**: South African banking product suite
- Savings Account
- Cheque Account
- Credit Card
- Personal Loan
- Home Loan
- Vehicle Finance
- Investment Account
- Premium Banking (Private Banking tier)

**Product Distribution**:
- 1 product: 50.8% (under-engaged, transactional customers)
- 2 products: 45.9% (optimal engagement)
- 3 products: 2.7% (over-banked, friction risk)
- 4 products: 0.6% (critical complexity)

#### 6. Engagement & Digital Banking Features
**Added Features**:
- UsesMobileBanking (80.6% adoption rate - FNB leads in mobile banking)
- UsesInternetBanking (70.0% adoption rate)
- MonthlyBranchVisits (declining trend due to digitalization)
- MonthlyATMTransactions
- CustomerServiceCalls_12M
- Complaints_12M
- PreferredCommChannel (Branch, Phone, Email, Mobile App, Internet Banking)

#### 7. Financial Wellness & Credit Bureau
**Added Features**:
- FinancialWellnessScore (1-10 scale)
- CreditBureau (reporting to SA credit bureaus: TransUnion, Experian, Compuscan, XDS)
- CreditRating (Poor, Fair, Good, Very Good, Excellent - SA credit scoring bands)

#### 8. Account Types
**Original**: Generic account  
**Transformed**: SA-specific account types
- Savings Account
- Cheque Account (primary transactional account in SA)
- Prestige Account (premium tier)
- Student Account
- Pensioner Account

### Statistical Integrity

**Preservation of Original Patterns**:
✅ Overall churn rate maintained (~20%)  
✅ Correlation structures preserved (age, balance, activity status)  
✅ Demographic distributions kept realistic  
✅ Product holding patterns consistent with banking norms  
✅ Geographic variations introduced while maintaining statistical validity

**Enhanced Analytical Opportunities**:
✅ Multi-level geographic analysis (province → city)  
✅ Cultural/linguistic segmentation  
✅ Product complexity analysis  
✅ Digital vs. traditional banking behavior  
✅ Wealth tier segmentation (mass market → VIP)

## Data Quality

### Completeness
- **Zero missing values** across all 43 features
- **No duplicate records** (unique CustomerID for all 10,000 records)
- **Consistent data types** throughout

### Validation Checks Performed
- ✅ Geographic consistency (city matches province)
- ✅ Salary ranges realistic for SA market
- ✅ Age distributions plausible (18-92 years)
- ✅ Product holdings logically consistent
- ✅ Credit scores within valid range (300-850)
- ✅ Tenure realistic (0-10 years)
- ✅ Balance amounts reasonable for account types

### Known Limitations
- **Synthetic transformation**: While based on real European banking data, the SA context is simulated
- **Simplified geography**: Real banking data would have more granular location data
- **Static snapshot**: Dataset represents single point in time, not longitudinal
- **Single bank**: Real competitive analysis would require multi-bank comparison
- **Privacy**: Customer names (surnames) are generic/anonymized

## Ethical Considerations

### Data Privacy
- All customer data is anonymized
- No personally identifiable information (PII)
- Surnames are generic and do not represent real individuals
- Customer IDs are randomly generated

### Fair Use & Educational Purpose
- Dataset used for educational and portfolio demonstration purposes
- Analysis focuses on aggregate patterns, not individual customers
- Recommendations are illustrative and would require validation with real data
- No actual customer data from FNB or any real bank is used

### Bias Awareness
- Gender representation: 54.6% Male, 45.4% Female
- Age distribution: Skewed toward working-age adults (26-55)
- Geographic distribution: Higher representation of major provinces (Gauteng, Western Cape)
- Language distribution: Reflects SA demographics but may not perfectly mirror FNB's actual customer base

## Usage Recommendations

### Appropriate Use Cases
✅ Educational data science projects  
✅ Portfolio demonstrations  
✅ Methodology showcasing  
✅ Interview discussions  
✅ Learning Power BI / DAX  
✅ Practicing EDA and modeling  

### Inappropriate Use Cases
❌ Production banking decisions  
❌ Claiming as real FNB data  
❌ Academic research without noting synthetic transformation  
❌ Commercial purposes without proper attribution  

## Citation

If you use this transformed dataset, please cite both:

1. **Original Dataset**:
   ```
   Badole, Saurabh (2023). Bank Customer Churn Prediction Dataset. 
   Kaggle. https://www.kaggle.com/datasets/saurabhbadole/bank-customer-churn-prediction-dataset
   ```

2. **Transformation**:
   ```
   [Your Name] (2024). South African Banking Context Adaptation of 
   Bank Customer Churn Dataset. GitHub: [Your Repository URL]
   ```

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | [Date] | Initial SA transformation with 9 provinces, 45 cities, 11 languages |
| 1.1 | [Date] | Added digital banking features (mobile, internet adoption) |
| 1.2 | [Date] | Enhanced product portfolio (8 product types) |
| Current | Dec 2024 | Comprehensive feature set with 43 variables |

## Contact

For questions about the transformation methodology or dataset usage:
- **Email**: [Your Email]
- **GitHub**: [Your GitHub Profile]
- **LinkedIn**: [Your LinkedIn Profile]

---

**Last Updated**: December 2024  
**Maintained By**: Timothy [Your Last Name]
