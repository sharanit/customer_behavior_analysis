# Data Directory

This directory contains the datasets used for the business Customer Analysis project.

## Files

### business_treadmill.csv
The primary dataset containing customer purchase information.

**Source:** business retail stores  
**Period:** Prior three months  
**Size:** 180+ customer records  

For detailed information about the dataset structure and variables, please refer to [data_dictionary.md](data_dictionary.md).

## Data Structure


data/
├── business_treadmill.csv      # Main dataset
├── data_dictionary.md          # Detailed variable descriptions
└── README.md                   # This file


## Usage

### Loading the Data

python
import pandas as pd

# Load the dataset
df = pd.read_csv('data/business_treadmill.csv')

# Display basic information
print(df.info())
print(df.head())


## Data Files Not Included

Due to file size or privacy concerns, the following files are not included in the repository:

- Raw data files (if processed versions are provided)
- Intermediate processed files
- Customer PII (Personally Identifiable Information)

If you need access to these files, please contact the project maintainer.

## Data Privacy

This dataset contains customer information. Please ensure:

- ✓ Data is used only for analysis purposes
- ✓ No individual customer information is shared publicly
- ✓ Aggregated results only in reports
- ✓ Compliance with data protection regulations

## Data Download

If the data file is not included in the repository, you can:

1. Download from: [Add link if available]
2. Request access from the project maintainer
3. Use the sample dataset provided for testing

## Adding New Data

If you're contributing new data files:

1. Ensure data is anonymized
2. Update the data_dictionary.md
3. Add file description to this README
4. Include sample size and date range
5. Verify no PII is included

---

**Last Updated:** February 2026
