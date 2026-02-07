# 🏃‍♂️ Business Treadmill Customer Analysis

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive data analysis project focused on customer profiling and product recommendations for Business's treadmill product line using descriptive statistics and probability analysis.

![Business Banner](images/banner.png)

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Analysis Approach](#analysis-approach)
- [Key Findings](#key-findings)
- [Recommendations](#recommendations)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🎯 Project Overview

XYZ Company is a leading brand in fitness equipment, offering a comprehensive range of treadmills, exercise bikes, and gym accessories. This project analyzes customer data to develop targeted customer profiles for each treadmill model, enabling better product recommendations and marketing strategies.

### About Business
Business provides a diverse product range designed to cater to fitness enthusiasts across all levels:
- Entry-level fitness equipment
- Mid-range performance machines
- Advanced professional-grade equipment
- Complete fitness accessories

## 💼 Business Problem

The market research team at Business needs to:

1. **Identify target audience characteristics** for each treadmill model
2. **Analyze differences** in customer demographics across products
3. **Provide better recommendations** to new customers based on their profile
4. **Understand purchasing patterns** through probability analysis

### Key Questions to Answer:
- What are the typical customer profiles for each treadmill model?
- How do demographic factors influence product selection?
- What is the probability of specific customer segments purchasing each model?
- What marketing strategies should be employed for each product?

## 📊 Dataset Description

The dataset contains information on **180+ customers** who purchased treadmills from Business stores over a three-month period.

### Features

| Feature | Description | Type |
|---------|-------------|------|
| **Product** | Treadmill model purchased (KP281, KP481, KP781) | Categorical |
| **Age** | Customer age in years | Numerical |
| **Gender** | Male/Female | Categorical |
| **Education** | Years of education | Numerical |
| **MaritalStatus** | Single or Partnered | Categorical |
| **Usage** | Expected weekly usage frequency | Numerical |
| **Fitness** | Self-rated fitness level (1-5 scale) | Numerical |
| **Income** | Annual income in USD | Numerical |
| **Miles** | Expected weekly miles to walk/run | Numerical |

### Product Portfolio

| Model | Target Segment | Price | Features |
|-------|----------------|-------|----------|
| **KP281** | Entry-level users | $1,500 | Basic features, ideal for beginners |
| **KP481** | Mid-level runners | $1,750 | Enhanced features for regular users |
| **KP781** | Advanced athletes | $2,500 | Premium features for serious fitness enthusiasts |

## 📁 Project Structure


Business-customer-analysis/
│
├── README.md                          # Project overview and documentation
├── LICENSE                            # MIT License
├── requirements.txt                   # Python dependencies
│
├── data/
│   ├── Business_treadmill.csv         # Raw dataset
│   └── data_dictionary.md            # Detailed data descriptions
│
├── notebooks/
│   ├── 01_data_exploration.ipynb     # Initial data exploration
│   ├── 02_statistical_analysis.ipynb # Descriptive statistics
│   ├── 03_probability_analysis.ipynb # Probability calculations
│   └── Business_Complete_Analysis.ipynb # Full analysis notebook
│
├── images/
│   ├── visualizations/               # Generated plots and charts
│   └── banner.png                    # Project banner
│
└── docs/
    ├── BUSINESS_CASE.md              # Detailed business case
    ├── METHODOLOGY.md                # Analysis methodology
    └── FINDINGS.md                   # Detailed findings and insights


## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Jupyter Notebook

### Setup Instructions

1. **Clone the repository**
bash
git clone https://github.com/sharanit/Business-customer-analysis.git
cd Business-customer-analysis


2. **Create a virtual environment** (recommended)
bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


3. **Install required packages**
bash
pip install -r requirements.txt


4. **Launch Jupyter Notebook**
bash
jupyter notebook


5. **Open and run the analysis notebooks** in the `notebooks/` directory

## 🔍 Analysis Approach

### 1. **Data Preparation & Exploration**
- Import and inspect dataset structure
- Check data types and statistical summaries
- Handle missing values and outliers
- Convert categorical variables appropriately

### 2. **Descriptive Statistics**
- Univariate analysis of all features
- Distribution analysis for continuous variables
- Frequency analysis for categorical variables
- Summary statistics by product type

### 3. **Visual Analysis**

#### Univariate Analysis
- Histograms and distribution plots for continuous variables
- Count plots for categorical variables
- Box plots for outlier detection

#### Bivariate Analysis
- Scatter plots for feature relationships
- Box plots grouped by product type
- Correlation heatmaps
- Pair plots for multi-variable relationships

### 4. **Probability Analysis**
- Marginal probabilities for each product
- Conditional probabilities (e.g., P(Product|Gender))
- Two-way contingency tables
- Joint probability distributions

### 5. **Customer Profiling**
- Demographic segmentation
- Behavioral pattern analysis
- Product-specific customer personas
- Purchase likelihood scoring

## 🎯 Key Findings

### Customer Demographics by Product

**KP281 (Entry-Level)**
- Younger customers (avg age: 25-30 years)
- Lower income bracket ($35K-$45K)
- Beginners to fitness (fitness rating: 2-3)
- Lower weekly usage expectations

**KP481 (Mid-Level)**
- Middle-aged customers (avg age: 30-40 years)
- Middle income bracket ($45K-$55K)
- Regular fitness enthusiasts (fitness rating: 3-4)
- Moderate weekly usage

**KP781 (Advanced)**
- Fitness-focused customers (avg age: 28-35 years)
- Higher income bracket ($55K+)
- Advanced fitness level (fitness rating: 4-5)
- High weekly usage expectations

### Statistical Insights
- Strong positive correlation between Income and Product price
- Fitness level is a significant predictor of product choice
- Gender differences exist in product preferences
- Marital status influences purchasing patterns

### Probability Insights
- P(Male customer) = ~58%
- P(KP781 | High Income) = ~65%
- P(Female | KP281) = ~40%
- Customers with fitness rating ≥4 are 3x more likely to purchase KP781

## 💡 Recommendations

### For Marketing Team

1. **Targeted Advertising**
   - KP281: Focus on beginner fitness content, affordability
   - KP481: Highlight value-for-money, versatility
   - KP781: Emphasize premium features, performance metrics

2. **Customer Segmentation**
   - Create specific campaigns for income brackets
   - Develop gender-specific marketing materials
   - Target based on fitness level and experience

3. **Pricing Strategy**
   - KP281: Position as entry point with upgrade path
   - KP481: Emphasize best value proposition
   - KP781: Justify premium pricing with advanced features

### For Sales Team

1. **Product Recommendations**
   - Use customer profiling tool based on demographics
   - Ask qualifying questions about fitness goals
   - Consider income level for appropriate suggestions

2. **Upselling Opportunities**
   - Identify KP281 buyers with high fitness goals
   - Promote KP481 to customers planning frequent use
   - Bundle accessories with KP781 purchases

### For Product Development

1. **Feature Enhancement**
   - Add beginner-friendly features to KP281
   - Develop mid-range accessories for KP481
   - Expand advanced metrics for KP781

2. **New Product Opportunities**
   - Consider a KP381 model to fill pricing gap
   - Develop financing options for premium models
   - Create product bundles by customer segment

## 🛠️ Technologies Used

- **Python 3.8+** - Primary programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization
- **Jupyter Notebook** - Interactive development environment
- **SciPy** - Statistical analysis

## 📈 Future Enhancements

- [ ] Implement machine learning models for customer segmentation
- [ ] Build a predictive model for product recommendations
- [ ] Create an interactive dashboard using Plotly/Dash
- [ ] Perform time-series analysis of purchase patterns
- [ ] Integrate A/B testing framework for marketing campaigns
- [ ] Develop automated reporting system

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the (LICENSE) file for details.

## 👤 Contact

**Sharan**
- GitHub: (https://github.com/sharanit)
- LinkedIn: (https://linkedin.com/in/sharanvora)
- Email: sharanvoracareers@gmail.com

## 🙏 Acknowledgments

- Business for providing the business case
- Data Analytics community for insights and best practices
- Contributors and reviewers

---

⭐ If you found this project helpful, please consider giving it a star!

**Last Updated:** February 2026
