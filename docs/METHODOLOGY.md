# Analysis Methodology

## Overview

This document outlines the analytical approach, techniques, and methodologies used in the business Customer Analysis project. The analysis follows a systematic approach to extract meaningful insights from customer data.

## Table of Contents
1. [Data Preparation](#data-preparation)
2. [Exploratory Data Analysis](#exploratory-data-analysis)
3. [Statistical Analysis](#statistical-analysis)
4. [Probability Analysis](#probability-analysis)
5. [Customer Profiling](#customer-profiling)
6. [Tools and Libraries](#tools-and-libraries)

---

## 1. Data Preparation

### 1.1 Data Import
python
import pandas as pd
import numpy as np

# Load dataset
df = pd.read_csv('data/business_treadmill.csv')


### 1.2 Data Quality Assessment

#### Structure Analysis
- Examine dataset dimensions
- Identify data types
- Check column names and consistency

#### Data Validation
python
# Check for missing values
df.isnull().sum()

# Check for duplicates
df.duplicated().sum()

# Verify data types
df.dtypes
df.info()


### 1.3 Data Cleaning

#### Missing Value Treatment
- Identify missing values
- Determine missing data mechanism (MCAR, MAR, MNAR)
- Apply appropriate imputation or removal strategy

#### Outlier Detection
Methods used:
1. **Statistical Method:** IQR (Interquartile Range)
2. **Visual Method:** Box plots
3. **Z-score Method:** For normally distributed variables

python
# IQR Method
Q1 = df['column'].quantile(0.25)
Q3 = df['column'].quantile(0.75)
IQR = Q3 - Q1
outliers = (df['column'] < (Q1 - 1.5 * IQR)) | (df['column'] > (Q3 + 1.5 * IQR))


#### Data Type Conversion
python
# Convert categorical variables
df['Product'] = df['Product'].astype('category')
df['Gender'] = df['Gender'].astype('category')
df['MaritalStatus'] = df['MaritalStatus'].astype('category')


---

## 2. Exploratory Data Analysis (EDA)

### 2.1 Univariate Analysis

#### Continuous Variables
Techniques:
- **Descriptive Statistics:** Mean, median, mode, std, min, max
- **Distribution Analysis:** Histograms, KDE plots
- **Shape Assessment:** Skewness, kurtosis

python
# Summary statistics
df.describe()

# Distribution visualization
import matplotlib.pyplot as plt
import seaborn as sns

sns.histplot(data=df, x='Age', kde=True)
plt.title('Age Distribution')
plt.show()


#### Categorical Variables
Techniques:
- **Frequency Tables:** Value counts
- **Proportions:** Percentage distribution
- **Visual Analysis:** Count plots, bar charts

python
# Frequency table
df['Product'].value_counts()

# Proportion
df['Product'].value_counts(normalize=True)

# Visualization
sns.countplot(data=df, x='Product')


### 2.2 Bivariate Analysis

#### Continuous vs Continuous
- **Scatter Plots:** Relationship visualization
- **Correlation Coefficient:** Pearson, Spearman
- **Trend Lines:** Linear regression lines

python
# Scatter plot
sns.scatterplot(data=df, x='Income', y='Miles')

# Correlation
df[['Income', 'Miles', 'Age']].corr()


#### Categorical vs Continuous
- **Box Plots:** Distribution comparison across categories
- **Violin Plots:** Distribution density
- **Group Statistics:** Mean, median by group

python
# Box plot
sns.boxplot(data=df, x='Product', y='Income')

# Group statistics
df.groupby('Product')['Income'].describe()


#### Categorical vs Categorical
- **Cross-tabulation:** Frequency tables
- **Stacked Bar Charts:** Proportion visualization
- **Heatmaps:** Count matrices

python
# Cross-tabulation
pd.crosstab(df['Product'], df['Gender'])

# Stacked bar chart
pd.crosstab(df['Product'], df['Gender'], normalize='index').plot(kind='bar', stacked=True)


### 2.3 Multivariate Analysis

#### Correlation Analysis
python
# Correlation heatmap
plt.figure(figsize=(10, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', center=0)
plt.title('Correlation Matrix')


#### Pair Plots
python
# Pairplot colored by product
sns.pairplot(df, hue='Product', vars=['Age', 'Income', 'Miles', 'Usage'])


---

## 3. Statistical Analysis

### 3.1 Descriptive Statistics

#### Central Tendency
- **Mean:** Average value
- **Median:** Middle value
- **Mode:** Most frequent value

#### Dispersion
- **Range:** Max - Min
- **Variance:** Average squared deviation
- **Standard Deviation:** Square root of variance
- **IQR:** Q3 - Q1

#### Shape
- **Skewness:** Measure of asymmetry
- **Kurtosis:** Measure of tailedness

python
# Comprehensive statistics by product
df.groupby('Product').agg({
    'Age': ['mean', 'median', 'std'],
    'Income': ['mean', 'median', 'std'],
    'Usage': ['mean', 'median', 'std']
})


### 3.2 Distribution Analysis

#### Normality Testing
- Visual: Q-Q plots, histograms
- Statistical: Shapiro-Wilk test, Kolmogorov-Smirnov test

python
from scipy import stats

# Shapiro-Wilk test
statistic, p_value = stats.shapiro(df['Age'])


---

## 4. Probability Analysis

### 4.1 Marginal Probability

Definition: Probability of a single event occurring

python
# P(Product = KP281)
total_customers = len(df)
kp281_customers = len(df[df['Product'] == 'KP281'])
prob_kp281 = kp281_customers / total_customers


**Applications:**
- Overall product distribution
- Gender distribution
- Marital status distribution

### 4.2 Conditional Probability

Definition: P(A|B) = Probability of A given B has occurred

python
# P(Product = KP781 | Gender = Male)
male_customers = df[df['Gender'] == 'Male']
male_kp781 = male_customers[male_customers['Product'] == 'KP781']
prob_kp781_given_male = len(male_kp781) / len(male_customers)


**Applications:**
- Product preference by gender
- Product choice by income bracket
- Purchase likelihood by fitness level

### 4.3 Joint Probability

Definition: P(A ∩ B) = Probability of both A and B occurring

python
# P(Product = KP781 AND Gender = Male)
male_kp781_count = len(df[(df['Product'] == 'KP781') & (df['Gender'] == 'Male')])
prob_joint = male_kp781_count / total_customers


### 4.4 Two-Way Contingency Tables

python
# Create contingency table
contingency_table = pd.crosstab(
    df['Product'], 
    df['Gender'], 
    margins=True,
    margins_name='Total'
)

# Convert to probability table
prob_table = pd.crosstab(
    df['Product'], 
    df['Gender'], 
    normalize='all'
)


**Analysis Components:**
1. **Marginal Totals:** Row and column sums
2. **Conditional Probabilities:** Row-wise or column-wise normalization
3. **Independence Testing:** Chi-square test

---

## 5. Customer Profiling

### 5.1 Segmentation Approach

#### Demographic Segmentation
- Age groups: Young (18-25), Middle (26-40), Mature (41+)
- Gender: Male, Female
- Marital Status: Single, Partnered

#### Behavioral Segmentation
- Usage frequency: Low (<3), Medium (3-4), High (5+)
- Fitness level: Beginner (1-2), Intermediate (3), Advanced (4-5)

#### Economic Segmentation
- Income brackets: Low (<$40K), Medium ($40K-$60K), High ($60K+)
- Education level: Basic (<12), Standard (12-16), Advanced (16+)

### 5.2 Profile Development

For each product, create a profile including:

1. **Demographic Characteristics**
   - Average age
   - Gender distribution
   - Marital status split

2. **Economic Profile**
   - Average income
   - Income range
   - Education level

3. **Behavioral Traits**
   - Expected usage frequency
   - Average miles planned
   - Fitness level distribution

4. **Statistical Summary**
   - Sample size
   - Percentage of total customers
   - Key differentiators

python
# Example profile creation
def create_customer_profile(df, product):
    product_data = df[df['Product'] == product]
    
    profile = {
        'product': product,
        'count': len(product_data),
        'percentage': len(product_data) / len(df) * 100,
        'avg_age': product_data['Age'].mean(),
        'avg_income': product_data['Income'].mean(),
        'avg_usage': product_data['Usage'].mean(),
        'avg_miles': product_data['Miles'].mean(),
        'avg_fitness': product_data['Fitness'].mean(),
        'gender_dist': product_data['Gender'].value_counts(normalize=True).to_dict(),
        'marital_dist': product_data['MaritalStatus'].value_counts(normalize=True).to_dict()
    }
    
    return profile


---

## 6. Tools and Libraries

### 6.1 Core Libraries

#### Data Manipulation
python
import pandas as pd  # DataFrames and data manipulation
import numpy as np   # Numerical computations


#### Visualization
python
import matplotlib.pyplot as plt  # Basic plotting
import seaborn as sns           # Statistical visualization


#### Statistical Analysis
python
from scipy import stats  # Statistical functions


### 6.2 Visualization Best Practices

#### Color Schemes
- Use colorblind-friendly palettes
- Maintain consistency across visualizations
- Use appropriate color mapping for data types

python
# Set style
sns.set_style("whitegrid")
sns.set_palette("husl")


#### Plot Customization
python
# Standard plot template
fig, ax = plt.subplots(figsize=(10, 6))
# ... plotting code ...
plt.title('Descriptive Title', fontsize=14, fontweight='bold')
plt.xlabel('X Label', fontsize=12)
plt.ylabel('Y Label', fontsize=12)
plt.tight_layout()
plt.show()


### 6.3 Code Organization

#### Notebook Structure
1. **Setup:** Imports and configuration
2. **Data Loading:** Read and initial inspection
3. **Data Cleaning:** Preprocessing steps
4. **EDA:** Exploration and visualization
5. **Analysis:** Statistical and probability analysis
6. **Profiling:** Customer segment creation
7. **Insights:** Summary and recommendations

#### Code Best Practices
- Use meaningful variable names
- Add comments for complex operations
- Create reusable functions
- Document assumptions
- Version control all code

---

## 7. Validation and Quality Assurance

### 7.1 Data Validation
- Cross-check calculations
- Verify probability sums (should equal 1)
- Validate logical relationships

### 7.2 Result Validation
- Peer review findings
- Business logic validation
- Sensitivity analysis

### 7.3 Documentation
- Document all assumptions
- Record data transformation steps
- Maintain analysis log

---

## Conclusion

This methodology provides a structured approach to analyzing customer data, ensuring:
- **Reproducibility:** Clear, documented steps
- **Reliability:** Validated techniques and results
- **Actionability:** Business-focused insights
- **Scalability:** Adaptable framework for future analysis

---

**Document Version:** 1.0  
**Last Updated:** February 2026  
**Author:** Data Analytics Team
