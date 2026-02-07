# Quick Start Guide

Get up and running with the business Customer Analysis project in minutes!

## 📋 Prerequisites

Before you begin, ensure you have:
- ✅ Python 3.8 or higher installed
- ✅ pip package manager
- ✅ Git installed
- ✅ 500MB free disk space

## 🚀 Quick Setup (5 minutes)

### Option 1: Clone from GitHub

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/business-customer-analysis.git
cd business-customer-analysis

# 2. Create virtual environment
python -m venv venv

# 3. Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Launch Jupyter Notebook
jupyter notebook
```

### Option 2: Download as ZIP

1. Download the ZIP file from GitHub
2. Extract to your desired location
3. Open terminal/command prompt in the extracted folder
4. Follow steps 2-5 from Option 1 above

## 📊 Download the Dataset

The dataset should be placed in the `data/` folder:

1. Download `business_treadmill.csv` from [source]
2. Place it in: `data/business_treadmill.csv`
3. Verify the file is in the correct location

## 🎯 Running the Analysis

### Quick Run

```bash
# 1. Make sure you're in the project directory
cd business-customer-analysis

# 2. Activate virtual environment (if not already active)
source venv/bin/activate  # or venv\Scripts\activate on Windows

# 3. Start Jupyter
jupyter notebook

# 4. Open the main notebook
# Navigate to: notebooks/business_Complete_Analysis.ipynb

# 5. Run all cells
# Click: Cell > Run All
```

### Step-by-Step Run

If you prefer to run sections individually:

1. Open `notebooks/business_Complete_Analysis.ipynb`
2. Run cells sequentially (Shift + Enter)
3. Review outputs after each section
4. Modify as needed for your analysis

## 📁 Project Structure Overview

```
business-customer-analysis/
│
├── data/                          # Data files go here
│   └── business_treadmill.csv     # Main dataset
│
├── notebooks/                     # Jupyter notebooks
│   └── business_Complete_Analysis.ipynb
│
├── images/                        # Visualizations
│   └── visualizations/           # Generated plots
│
├── docs/                         # Documentation
│   ├── BUSINESS_CASE.md         # Business context
│   ├── METHODOLOGY.md           # Analysis methods
│   └── FINDINGS.md              # Results template
│
└── README.md                     # Project overview
```

## 🔍 What You'll Find

After running the analysis, you'll get:

1. **Customer Profiles** for each treadmill model
2. **Statistical Insights** on customer demographics
3. **Probability Analysis** for marketing targeting
4. **Visualizations** showing patterns and trends
5. **Business Recommendations** for sales and marketing

## ⚡ Common Issues & Solutions

### Issue: ModuleNotFoundError

```bash
# Solution: Install missing package
pip install package-name
# or reinstall all requirements
pip install -r requirements.txt
```

### Issue: Kernel dies or crashes

```python
# Solution: Restart kernel in Jupyter
# Click: Kernel > Restart & Clear Output
# Then run cells again
```

### Issue: Can't find data file

```python
# Solution: Check file path
import os
print(os.getcwd())  # Should be in project root
print(os.path.exists('data/business_treadmill.csv'))  # Should be True
```

### Issue: Plots not displaying

```python
# Solution: Add this at the top of notebook
%matplotlib inline
import matplotlib.pyplot as plt
```

## 📚 Next Steps

1. **Explore the Data**
   - Run the complete analysis
   - Review generated visualizations
   - Read the findings

2. **Customize the Analysis**
   - Modify visualizations
   - Add new analyses
   - Create additional segments

3. **Share Your Results**
   - Export notebook to PDF/HTML
   - Save key visualizations
   - Update FINDINGS.md with your results

4. **Contribute** (Optional)
   - Fork the repository
   - Make improvements
   - Submit a pull request

## 🆘 Getting Help

If you encounter issues:

1. **Check Documentation**
   - README.md
   - docs/METHODOLOGY.md
   - Notebook comments

2. **Search Issues**
   - GitHub Issues tab
   - Common problems section

3. **Ask for Help**
   - Open a new issue on GitHub
   - Include error message
   - Describe what you tried

## 🎓 Learning Resources

### Python & Data Analysis
- [Python for Data Analysis](https://wesmckinney.com/book/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

### Statistics & Probability
- [Khan Academy Statistics](https://www.khanacademy.org/math/statistics-probability)
- [Probability Concepts](https://seeing-theory.brown.edu/)

### Jupyter Notebooks
- [Jupyter Documentation](https://jupyter-notebook.readthedocs.io/)
- [Markdown Guide](https://www.markdownguide.org/)

## ✅ Verification Checklist

Before proceeding, verify:

- [ ] Python 3.8+ is installed
- [ ] Virtual environment is created and activated
- [ ] All packages installed without errors
- [ ] Dataset is in the correct location
- [ ] Jupyter Notebook launches successfully
- [ ] Can open the analysis notebook
- [ ] First few cells run without errors

## 🎉 You're Ready!

You should now be able to:
- ✓ Load and explore the data
- ✓ Run statistical analyses
- ✓ Generate visualizations
- ✓ Create customer profiles
- ✓ Extract business insights

Happy analyzing! 📊

---

**Need more detailed instructions?** See the full [README.md](README.md)

**Questions?** Open an issue on GitHub or contact the maintainer.

**Last Updated:** February 2026
