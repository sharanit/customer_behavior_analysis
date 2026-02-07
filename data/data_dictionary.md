# Data Dictionary

## Overview
This document provides detailed information about each variable in the business Treadmill dataset.

## Dataset Information
- **Source:** business retail stores
- **Time Period:** Prior three months
- **Sample Size:** 180+ customers
- **Collection Method:** Point-of-sale transaction data combined with customer surveys

---

## Variables

### 1. Product
- **Type:** Categorical (Nominal)
- **Description:** The treadmill model purchased by the customer
- **Possible Values:**
  - `KP281` - Entry-level treadmill ($1,500)
  - `KP481` - Mid-level treadmill ($1,750)
  - `KP781` - Advanced treadmill ($2,500)
- **Business Significance:** Target variable for profiling and recommendation
- **Missing Values:** Not allowed
- **Data Quality Notes:** All transactions must have a product code

---

### 2. Age
- **Type:** Continuous (Numeric)
- **Description:** Customer's age at the time of purchase
- **Unit:** Years
- **Expected Range:** 18-75 years
- **Typical Values:** 20-50 years
- **Business Significance:** Key demographic factor for segmentation
- **Missing Values:** Should be minimal; impute with median if necessary
- **Outlier Treatment:** Values outside 18-75 should be investigated

---

### 3. Gender
- **Type:** Categorical (Binary/Nominal)
- **Description:** Customer's gender
- **Possible Values:**
  - `Male`
  - `Female`
- **Business Significance:** Important for targeted marketing and product design
- **Missing Values:** Not allowed
- **Data Quality Notes:** Standardize capitalization

---

### 4. Education
- **Type:** Continuous (Numeric)
- **Description:** Number of years of formal education completed
- **Unit:** Years
- **Expected Range:** 10-21 years
- **Typical Values:** 12-18 years
- **Interpretation:**
  - 12 years = High school diploma
  - 16 years = Bachelor's degree
  - 18+ years = Graduate degree
- **Business Significance:** Proxy for socioeconomic status and health awareness
- **Missing Values:** Impute with median or mode
- **Outlier Treatment:** Values below 10 or above 25 should be verified

---

### 5. MaritalStatus
- **Type:** Categorical (Binary/Nominal)
- **Description:** Customer's marital or partnership status
- **Possible Values:**
  - `Single` - Not in a committed relationship
  - `Partnered` - Married or in a committed relationship
- **Business Significance:** Affects purchasing decisions and household income
- **Missing Values:** Not allowed
- **Data Quality Notes:** Standardize capitalization and terminology

---

### 6. Usage
- **Type:** Continuous (Numeric)
- **Description:** Expected number of times the customer plans to use the treadmill per week
- **Unit:** Times per week
- **Expected Range:** 2-7 times
- **Typical Values:** 3-5 times
- **Business Significance:** Indicator of commitment level and appropriate product match
- **Missing Values:** Critical variable; should be collected at purchase
- **Outlier Treatment:** Values above 7 should be verified
- **Note:** Self-reported; actual usage may vary

---

### 7. Income
- **Type:** Continuous (Numeric)
- **Description:** Customer's annual household income
- **Unit:** US Dollars (USD)
- **Expected Range:** $25,000 - $120,000
- **Typical Values:** $40,000 - $70,000
- **Business Significance:** Primary indicator of purchasing power
- **Missing Values:** Sensitive data; may have higher missing rate
- **Outlier Treatment:** 
  - Values below $20,000 - verify
  - Values above $150,000 - verify
- **Privacy Notes:** Should be handled confidentially
- **Income Brackets for Analysis:**
  - Low: < $40,000
  - Medium: $40,000 - $60,000
  - High: > $60,000

---

### 8. Fitness
- **Type:** Ordinal (Categorical)
- **Description:** Self-rated fitness level
- **Possible Values:** 1, 2, 3, 4, 5
- **Scale Interpretation:**
  - `1` - Poor shape (Beginner, sedentary lifestyle)
  - `2` - Below average (Occasional exercise)
  - `3` - Average (Regular moderate exercise)
  - `4` - Good shape (Frequent exercise, active lifestyle)
  - `5` - Excellent shape (Athlete, very active)
- **Business Significance:** Matches customer capability with appropriate equipment
- **Missing Values:** Should be minimal; impute with mode or median
- **Data Quality Notes:** Subjective measure; may have bias
- **Analysis Categories:**
  - Beginner: 1-2
  - Intermediate: 3
  - Advanced: 4-5

---

### 9. Miles
- **Type:** Continuous (Numeric)
- **Description:** Average number of miles the customer expects to walk/run per week
- **Unit:** Miles
- **Expected Range:** 20-200 miles
- **Typical Values:** 50-150 miles
- **Business Significance:** Indicates intensity of use and appropriate product features
- **Missing Values:** Important predictor; should be collected
- **Outlier Treatment:** Values above 250 should be verified
- **Note:** Self-reported expectations; actual usage may differ
- **Conversion:** 1 mile ≈ 1.6 kilometers

---

## Derived Variables (for Analysis)

### Age Groups
- **Young Adults:** 18-30 years
- **Middle Age:** 31-45 years
- **Mature:** 46+ years

### Income Categories
- **Low Income:** < $40,000
- **Middle Income:** $40,000 - $60,000
- **High Income:** > $60,000

### Fitness Categories
- **Beginner:** 1-2
- **Intermediate:** 3
- **Advanced:** 4-5

### Usage Frequency
- **Light Users:** < 3 times/week
- **Regular Users:** 3-4 times/week
- **Heavy Users:** 5+ times/week

---

## Data Relationships

### Expected Correlations
- **Positive Correlations:**
  - Income ↔ Product Price
  - Fitness ↔ Miles
  - Fitness ↔ Usage
  - Age ↔ Income (moderate)
  - Education ↔ Income

- **Weak/No Correlation:**
  - Gender ↔ Fitness
  - Marital Status ↔ Usage

### Business Logic Validations
1. Higher fitness levels should correlate with higher usage and miles
2. Higher income should correlate with premium products
3. Younger customers may prefer entry-level products (budget constraints)
4. Older customers with higher income may prefer advanced features

---

## Data Quality Checklist

- [ ] No missing values in critical fields (Product, Gender, MaritalStatus)
- [ ] Age values within reasonable range (18-75)
- [ ] Income values are positive and within expected range
- [ ] Fitness ratings are integers between 1-5
- [ ] Usage frequency is realistic (0-7 times/week)
- [ ] Miles per week is realistic based on usage
- [ ] No duplicate customer records
- [ ] Categorical variables have consistent formatting
- [ ] All numeric values are in correct units

---

## Privacy and Ethics

### Sensitive Data
- **Income:** Confidential, aggregated reporting only
- **Age:** Can be reported in ranges
- **Gender:** Respect privacy in reporting

### Usage Guidelines
- Data should be anonymized for external sharing
- Individual customer details should not be disclosed
- Aggregate statistics only in public reports
- Comply with data protection regulations (GDPR, CCPA)

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | Feb 2026 | Initial creation | Data Team |

---

**Document Owner:** Data Analytics Team  
**Last Reviewed:** February 2026  
**Next Review:** May 2026
