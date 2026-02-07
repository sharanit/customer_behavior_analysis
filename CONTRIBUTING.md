# Contributing to business Customer Analysis

First off, thank you for considering contributing to this project! 🎉

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Style Guidelines](#style-guidelines)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)

## Code of Conduct

This project adheres to a code of conduct. By participating, you are expected to uphold this code. Please be respectful and constructive in all interactions.

### Our Standards

- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what you expected**
- **Include screenshots if relevant**
- **Include your environment details** (OS, Python version, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the proposed enhancement**
- **Explain why this enhancement would be useful**
- **List any alternatives you've considered**

### Contributing Code

#### Types of Contributions

1. **Analysis Improvements**
   - New statistical methods
   - Additional visualizations
   - Enhanced customer profiling techniques

2. **Documentation**
   - Fixing typos or clarifying existing docs
   - Adding examples or tutorials
   - Improving code comments

3. **Code Quality**
   - Bug fixes
   - Performance improvements
   - Code refactoring

4. **New Features**
   - Interactive dashboards
   - Machine learning models
   - Automated reporting

## Getting Started

### Prerequisites

- Python 3.8 or higher
- Git
- Basic understanding of data analysis and Python

### Setting Up Your Development Environment

1. **Fork the repository** on GitHub

2. **Clone your fork locally**
   bash
   git clone https://github.com/sharanit/business-customer-analysis.git
   cd business-customer-analysis
   

3. **Create a virtual environment**
   bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   

4. **Install dependencies**
   bash
   pip install -r requirements.txt
   

5. **Create a branch for your changes**
   bash
   git checkout -b feature/your-feature-name
   

## Development Process

### Workflow

1. **Create an issue** (if one doesn't exist) describing what you plan to work on
2. **Assign yourself** to the issue
3. **Create a branch** from `main`
4. **Make your changes** with clear, logical commits
5. **Test your changes** thoroughly
6. **Update documentation** as needed
7. **Submit a pull request**

### Testing Your Changes

Before submitting a pull request:

1. **Run all notebooks** to ensure they execute without errors
2. **Check data validation** - ensure data integrity is maintained
3. **Verify visualizations** - ensure plots render correctly
4. **Test edge cases** - check how code handles unusual inputs

## Style Guidelines

### Python Code Style

We follow PEP 8 guidelines with some modifications:

#### General Guidelines

python
# Good - Clear variable names
customer_age = df['Age'].mean()
total_customers = len(df)

# Bad - Unclear abbreviations
ca = df['Age'].mean()
tc = len(df)


#### Imports

python
# Standard library imports first
import os
import sys

# Third-party imports
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Local imports
from utils import helper_functions


#### Function Documentation

python
def calculate_probability(df, condition_col, condition_val, target_col, target_val):
    """
    Calculate conditional probability P(target|condition).
    
    Parameters:
    -----------
    df : pd.DataFrame
        Input dataframe
    condition_col : str
        Column name for condition
    condition_val : str/int
        Value for condition
    target_col : str
        Column name for target
    target_val : str/int
        Value for target
    
    Returns:
    --------
    float
        Conditional probability value
    
    Example:
    --------
    >>> prob = calculate_probability(df, 'Gender', 'Male', 'Product', 'KP781')
    >>> print(f"P(KP781|Male) = {prob:.2%}")
    """
    condition_data = df[df[condition_col] == condition_val]
    target_count = len(condition_data[condition_data[target_col] == target_val])
    return target_count / len(condition_data) if len(condition_data) > 0 else 0


#### Visualization Standards

python
# Good - Clear, well-labeled plot
plt.figure(figsize=(10, 6))
sns.boxplot(data=df, x='Product', y='Income')
plt.title('Income Distribution by Product', fontsize=14, fontweight='bold')
plt.xlabel('Product Model', fontsize=12)
plt.ylabel('Annual Income ($)', fontsize=12)
plt.tight_layout()
plt.savefig('images/income_by_product.png', dpi=300, bbox_inches='tight')
plt.show()


### Jupyter Notebook Guidelines

1. **Clear section headers** using markdown cells
2. **Explanatory text** before code cells
3. **Clean output** - remove unnecessary print statements
4. **Restart and run all** before committing
5. **Remove sensitive data** from outputs

#### Notebook Structure

markdown
# 1. Setup and Imports
## 1.1 Import Libraries
## 1.2 Load Data

# 2. Data Cleaning
## 2.1 Handle Missing Values
## 2.2 Detect Outliers

# 3. Exploratory Data Analysis
## 3.1 Univariate Analysis
## 3.2 Bivariate Analysis

# 4. Statistical Analysis
## 4.1 Descriptive Statistics
## 4.2 Probability Analysis

# 5. Customer Profiling
## 5.1 Create Profiles
## 5.2 Visualize Segments

# 6. Insights and Recommendations


### Documentation Style

- Use clear, concise language
- Include examples where helpful
- Keep README up to date
- Document assumptions and limitations
- Add inline comments for complex logic

## Commit Messages

### Format

<type>(<scope>): <subject>

<body>

<footer>


### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code formatting (no logic change)
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

### Examples

bash
# Good commit messages
feat(analysis): Add correlation analysis for customer segments
fix(visualization): Correct axis labels in income distribution plot
docs(readme): Update installation instructions for Windows users
refactor(profiling): Simplify customer profile creation function

# Bad commit messages
Update stuff
Fixed bug
Changed code


## Pull Request Process

### Before Submitting

1. **Update your branch** with the latest main
   bash
   git checkout main
   git pull upstream main
   git checkout your-branch
   git rebase main


2. **Run final checks**
   - All notebooks execute successfully
   - No merge conflicts
   - Documentation is updated
   - Code follows style guidelines

### PR Description Template

markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Code refactoring

## Changes Made
- Change 1
- Change 2
- Change 3

## Testing
Describe how you tested your changes

## Screenshots (if applicable)
Add screenshots for visual changes

## Checklist
- [ ] Code follows project style guidelines
- [ ] Documentation updated
- [ ] All notebooks run without errors
- [ ] Commit messages are clear
- [ ] No merge conflicts


### Review Process

1. At least one maintainer will review your PR
2. Address any requested changes
3. Once approved, a maintainer will merge your PR
4. Your contribution will be acknowledged in release notes

## Recognition

Contributors will be:
- Listed in the project README
- Acknowledged in release notes
- Eligible for contributor badge

## Questions?

Feel free to:
- Open an issue for questions
- Reach out to maintainers
- Join discussions in existing issues

---

Thank you for contributing! 🙏

**Last Updated:** February 2026
