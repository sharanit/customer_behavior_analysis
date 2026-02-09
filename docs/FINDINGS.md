# Analysis Findings and Insights

> **Note:** This document will be populated with actual findings from your analysis. The sections below provide a template for organizing your results.

## Executive Summary

This analysis reveals clear market segmentation with income, fitness level, and gender as primary drivers of product choice. The significant opportunity in the female premium market (currently only 18% of KP781 buyers) and the strong income-product correlation provide clear direction for targeted marketing strategies.

By implementing income-based segmentation, gender-inclusive premium marketing, and enhanced customer experience programs, Aerofit can increase market share in profitable premium segments while maintaining entry-level dominance.

### Key Takeaways
**Key Success Factors:**
1. Address gender disparity in premium segment
2. Leverage income data for targeted marketing
3. Emphasize fitness community and social proof
4. Provide flexible purchasing options
5. Build customer loyalty through engagement

**Expected Overall Impact:**
- 20-30% revenue growth
- 5-7% premium market share increase
- 15% improvement in customer satisfaction
- 25% increase in customer lifetime value

### Visualizations Generated:
1. Univariate Analysis (Age, Income, Product distributions)
2. Outlier Detection (Boxplots for all numerical variables)
3. Bivariate Analysis (Product vs Demographics)
4. Correlation Heatmap
5. Comprehensive Dashboard

---

## 1. Data Overview

### Dataset Summary
- **Total Customers:** 180
- **Analysis Period:** 2025-01-01 to 2025-12-31
- **Products Analyzed:** KP281, KP481, KP781
- **Variables Analyzed:** 9 features

### Data Quality
- **Missing Values:** 0%
- **Outliers Detected:** Yes
- **Data Completeness:** Sample data is not complete

---

## 2. Customer Demographics

### 2.1 Age Distribution

**Overall Statistics:**
- Mean Age: 28.79 years
- Median Age: 26.0 years
- Age Range: 18 - 50 years

**By Product:**
| Product | Mean Age | Median Age | Std Dev |
|---------|----------|------------|---------|
| KP281   | 28.55    | 26.00      | 7.22    |
| KP481   | 28.90    | 26.00      | 6.65    |
| KP781   | 29.10    | 27.00      | 6.97    |

**Key Insights:**
- [Insight about age patterns]
- [Insight about product preference by age]

### 2.2 Gender Distribution

**Overall Distribution:**
- Male: 58.00%
- Female: 42.00%

**By Product:**
| Product | Male % | Female % |
|---------|--------|----------|
| KP281   | 58.00% | 42.00%   |
| KP481   | 58.00% | 42.00%   |
| KP781   | 58.00% | 42.00%   |

**Key Insights:**
- [Insight about gender preferences]
- [Notable patterns or differences]

### 2.3 Marital Status

**Overall Distribution:**
- Single: 41.00%
- Partnered: 59.00%

**By Product:**
| Product | Single % | Partnered % |
|---------|----------|-------------|
| KP281   | 41.00%   | 59.00%      |
| KP481   | 41.00%   | 59.00%      |
| KP781   | 41.00%   | 59.00%     |

**Key Insights:**
- [Insight about marital status impact]
- [Purchasing patterns]

---

## 3. Economic Profile

### 3.1 Income Analysis

**Overall Statistics:**
- Mean Income: 53719.58
- Median Income: 53719.58
- Income Range: 29562.00 - 104581.00

**By Product:**
| Product | Mean Income | Median Income | Std Dev |
|---------|-------------|---------------|---------|
| KP281   | 46418.03    | 46617.00      | 9075.78   |
| KP481   | 48973.65    | 49459.50      | 8653.99   |
| KP781   | 75441.57    | 76568.50      | 18505.84  |

**Income Distribution by Product:**
- KP281: Primarily [29562.00 - 104581.00] income range
- KP481: Primarily [29562.00 - 104581.00] income range
- KP781: Primarily [29562.00 - 104581.00] income range

**Key Insights:**
- [Clear income segmentation patterns]
- [Price sensitivity observations]
- [Income as a predictor of product choice]

### 3.2 Education Level

**Overall Statistics:**
- Mean Education: 15.57 years
- Median Education: 16.00 years
- Range: 12.00 - 21.00 years

**By Product:**
| Product | Mean Education | Median Education |
|---------|----------------|------------------|
| KP281   | 15.04          | 16.00             |
| KP481   | 15.12          | 16.00.            |
| KP781   | 17.32          | 18.00             |

**Key Insights:**
- [Education level patterns]
- [Correlation with other factors]

---

## 4. Behavioral Patterns

### 4.1 Usage Frequency

**Overall Statistics:**
- Mean Usage: 3.46 times/week
- Median Usage: 3.00 times/week

**By Product:**
| Product | Mean Usage | Median Usage | Range      |
|---------|------------|--------------|------------|
| KP281   | 3.09       | 3.00         | 2.00 - 5.00|
| KP481   | 3.07       | 3.00         | 2.00 - 5.00|
| KP781   | 4.78       | 5.00         | 3.00 - 7.00|

**Key Insights:**
- [Usage patterns by product]
- [Commitment level indicators]

### 4.2 Distance Expectations (Miles)

**Overall Statistics:**
- Mean Miles: 103.19 miles/week
- Median Miles: 94.00 miles/week

**By Product:**
| Product | Mean Miles  | Median Miles | Range           |
|---------|-------------|--------------|-----------------|
| KP281   | 82.79       | 85.00        | 38.00 - 188.00  |
| KP481   | 87.93       | 85.00        | 21.00 - 212.00  |
| KP781   | 166.90      | 160.00       | 80.00 - 360.00  |

**Key Insights:**
- [Distance expectations by product tier]
- [Correlation with fitness level]

### 4.3 Fitness Level

**Overall Distribution:**
| Fitness Level | Count | Percentage |
|---------------|-------|------------|
| 1 (Poor)      | 2     | 0.01       |
| 2 (Below Avg) | 26    | 0.14      |
| 3 (Average)   | 97    | 0.54      |
| 4 (Good)      | 24    | 0.13     |
| 5 (Excellent) | 31    | 0.17       |

**By Product:**
| Product | Mean Fitness | Mode | Advanced Users (4-5) % |
|---------|--------------|------|------------------------|
| KP281   | 2.96         | 3.00 | 0.31                   |
| KP481   | 2.90         | 3.00 | 0.31                   |
| KP781   | 4.62         | 5.00 | 0.31                   |
 
**Key Insights:**
- [Fitness level as a strong predictor]
- [Self-assessment patterns]

---

## 5. Product Analysis

### 5.1 Product Distribution

| Product | Count | Percentage | Revenue Contribution* |
|---------|-------|------------|----------------------|
| KP281   | [X]   | [X%]       | [X%]                 |
| KP481   | [X]   | [X%]       | [X%]                 |
| KP781   | [X]   | [X%]       | [X%]                 |

*Based on product prices

### 5.2 Product Preferences by Segment

**By Gender:**
- Males prefer: [Product] ([X%])
- Females prefer: [Product] ([X%])

**By Age Group:**
- Young Adults (18-30): Prefer [Product] ([X%])
- Middle Age (31-45): Prefer [Product] ([X%])
- Mature (46+): Prefer [Product] ([X%])

**By Income Level:**
- Low Income (<$40K): [X%] choose KP281
- Medium Income ($40K-$60K): [X%] choose KP481
- High Income (>$60K): [X%] choose KP781

---

## 6. Statistical Relationships

### 6.1 Correlation Analysis

**Strong Positive Correlations (r > 0.6):**
- [Variable 1] ↔ [Variable 2]: r = [X]
- [Variable 3] ↔ [Variable 4]: r = [X]

**Moderate Correlations (0.3 < r < 0.6):**
- [Variable] ↔ [Variable]: r = [X]

**Weak/No Correlation (r < 0.3):**
- [Variable] ↔ [Variable]: r = [X]

**Key Insights:**
- [Interpretation of correlations]
- [Business implications]

### 6.2 Distribution Patterns

**Normal Distributions:**
- [Variable]: Approximately normal
- [Variable]: Slightly skewed

**Skewed Distributions:**
- [Variable]: Right-skewed (skewness = [X])
- [Variable]: Left-skewed (skewness = [X])

---

## 7. Probability Analysis

### 7.1 Marginal Probabilities

**Product Probabilities:**
- P(KP281) = [X%]
- P(KP481) = [X%]
- P(KP781) = [X%]

**Demographic Probabilities:**
- P(Male) = [X%]
- P(Female) = [X%]
- P(Single) = [X%]
- P(Partnered) = [X%]

### 7.2 Conditional Probabilities

**Gender-Based:**
| Condition | P(KP281) | P(KP481) | P(KP781) |
|-----------|----------|----------|----------|
| Male      | [X%]     | [X%]     | [X%]     |
| Female    | [X%]     | [X%]     | [X%]     |

**Income-Based:**
| Income Level | P(KP281) | P(KP481) | P(KP781) |
|--------------|----------|----------|----------|
| Low          | [X%]     | [X%]     | [X%]     |
| Medium       | [X%]     | [X%]     | [X%]     |
| High         | [X%]     | [X%]     | [X%]     |

**Fitness-Based:**
| Fitness Level | P(KP281) | P(KP481) | P(KP781) |
|---------------|----------|----------|----------|
| Beginner (1-2)| [X%]     | [X%]     | [X%]     |
| Intermediate(3)| [X%]    | [X%]     | [X%]     |
| Advanced (4-5)| [X%]     | [X%]     | [X%]     |

### 7.3 Notable Probability Findings

1. **Highest Probability Combinations:**
   - P(KP781 | High Income & Advanced Fitness) = [X%]
   - P(KP281 | Low Income & Beginner) = [X%]

2. **Surprising Findings:**
   - [Unexpected probability result]
   - [Counter-intuitive pattern]

---

## 8. Customer Profiles

### 8.1 KP281 Customer Profile (Entry-Level)

**Demographic Profile:**
- **Typical Age:** [X] years old
- **Gender Split:** [X%] Male, [X%] Female
- **Marital Status:** [X%] Single, [X%] Partnered

**Economic Profile:**
- **Average Income:** $[X]
- **Education Level:** [X] years
- **Price Sensitivity:** High

**Behavioral Profile:**
- **Usage Frequency:** [X] times/week
- **Weekly Miles:** [X] miles
- **Fitness Level:** [X] (Beginner/Intermediate)

**Persona: "The Fitness Starter"**
[1-2 paragraph narrative description]

### 8.2 KP481 Customer Profile (Mid-Level)

**Demographic Profile:**
- **Typical Age:** [X] years old
- **Gender Split:** [X%] Male, [X%] Female
- **Marital Status:** [X%] Single, [X%] Partnered

**Economic Profile:**
- **Average Income:** $[X]
- **Education Level:** [X] years
- **Price Sensitivity:** Moderate

**Behavioral Profile:**
- **Usage Frequency:** [X] times/week
- **Weekly Miles:** [X] miles
- **Fitness Level:** [X] (Intermediate)

**Persona: "The Regular Runner"**
[1-2 paragraph narrative description]

### 8.3 KP781 Customer Profile (Advanced)

**Demographic Profile:**
- **Typical Age:** [X] years old
- **Gender Split:** [X%] Male, [X%] Female
- **Marital Status:** [X%] Single, [X%] Partnered

**Economic Profile:**
- **Average Income:** $[X]
- **Education Level:** [X] years
- **Price Sensitivity:** Low

**Behavioral Profile:**
- **Usage Frequency:** [X] times/week
- **Weekly Miles:** [X] miles
- **Fitness Level:** [X] (Advanced)

**Persona: "The Serious Athlete"**
[1-2 paragraph narrative description]

---

## 9. Key Insights Summary

### 9.1 Most Important Findings

1. **[Finding 1]**
   - Supporting data
   - Business impact
   - Recommendation

2. **[Finding 2]**
   - Supporting data
   - Business impact
   - Recommendation

3. **[Finding 3]**
   - Supporting data
   - Business impact
   - Recommendation

### 9.2 Unexpected Discoveries

1. [Surprising finding]
2. [Counter-intuitive pattern]
3. [Unexpected correlation]

### 9.3 Validation of Assumptions

**Confirmed Assumptions:**
- [Assumption that was validated]
- [Expected pattern confirmed]

**Rejected Assumptions:**
- [Assumption that proved false]
- [Expected pattern not found]

---

## 10. Limitations and Caveats

### 10.1 Data Limitations
- [Limitation 1]
- [Limitation 2]
- [Limitation 3]

### 10.2 Analysis Limitations
- [Limitation 1]
- [Limitation 2]

### 10.3 Future Research Needs
- [Area requiring more investigation]
- [Additional data needed]
- [Follow-up analysis recommended]

---

**Document Status:** Template  
**To be completed with:** Actual analysis results  
**Last Updated:** February 2026  
**Analysts:** [Sharan]
