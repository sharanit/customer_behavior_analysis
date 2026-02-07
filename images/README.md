# Images and Visualizations

This directory contains all visualizations and images generated during the analysis.

## Directory Structure

```
images/
├── visualizations/          # Generated plots and charts
│   ├── univariate/         # Single variable distributions
│   ├── bivariate/          # Two variable relationships
│   ├── correlation/        # Correlation heatmaps and matrices
│   └── customer_profiles/  # Profile-specific visualizations
├── banner.png              # Project banner for README
└── README.md               # This file
```

## Visualization Categories

### Univariate Analysis
Distribution plots for individual variables:
- Age distribution
- Income distribution
- Gender counts
- Product distribution
- Fitness level distribution
- Usage frequency distribution
- Miles per week distribution

### Bivariate Analysis
Relationship visualizations:
- Income by Product (box plots)
- Age by Product (box plots)
- Miles by Fitness Level (scatter plots)
- Usage by Product (violin plots)
- Gender distribution by Product (stacked bars)

### Correlation Analysis
- Full correlation heatmap
- Pair plots for continuous variables
- Correlation matrices by product

### Customer Profiles
- Demographic comparison charts
- Behavioral pattern visualizations
- Economic profile comparisons
- Segment distribution plots

## Saving Visualizations

### From Matplotlib/Seaborn

```python
import matplotlib.pyplot as plt

# Create your plot
plt.figure(figsize=(10, 6))
# ... plotting code ...

# Save with high resolution
plt.savefig('images/visualizations/plot_name.png', 
            dpi=300, 
            bbox_inches='tight',
            facecolor='white')
plt.show()
```

### Naming Convention

Use descriptive names following this pattern:
```
[category]_[variable(s)]_[chart_type].png
```

Examples:
- `univariate_age_histogram.png`
- `bivariate_income_product_boxplot.png`
- `correlation_heatmap.png`
- `profile_kp281_demographics.png`

## Image Specifications

### For Reports/Presentations
- **Format:** PNG
- **DPI:** 300
- **Background:** White
- **Size:** 10x6 inches (default)

### For Web/GitHub
- **Format:** PNG or SVG
- **DPI:** 150-300
- **File size:** < 1MB
- **Dimensions:** Optimized for viewing

## Using Images in Documentation

### In Markdown
```markdown
![Description](images/visualizations/plot_name.png)
```

### In Jupyter Notebooks
```python
from IPython.display import Image
Image(filename='images/visualizations/plot_name.png')
```

## Best Practices

### Creating Visualizations

1. **Always include:**
   - Descriptive title
   - Axis labels with units
   - Legend (if multiple series)
   - Appropriate color scheme

2. **Formatting:**
   - Use consistent fonts
   - Maintain readable font sizes (12pt minimum)
   - Use colorblind-friendly palettes
   - Ensure proper contrast

3. **Annotations:**
   - Add data labels when helpful
   - Highlight key insights
   - Include sample sizes
   - Note data source

### Example: Well-Formatted Plot

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 6))
sns.boxplot(data=df, x='Product', y='Income', palette='Set2')

plt.title('Income Distribution by Product Model', 
          fontsize=16, fontweight='bold', pad=20)
plt.xlabel('Treadmill Model', fontsize=12)
plt.ylabel('Annual Income (USD)', fontsize=12)

# Add sample size annotations
for i, product in enumerate(['KP281', 'KP481', 'KP781']):
    n = len(df[df['Product'] == product])
    plt.text(i, plt.ylim()[0], f'n={n}', 
             ha='center', va='top', fontsize=10)

plt.tight_layout()
plt.savefig('images/visualizations/bivariate_income_product_boxplot.png',
            dpi=300, bbox_inches='tight', facecolor='white')
plt.show()
```

## Image Optimization

For web use, optimize images:

```bash
# Using ImageMagick
convert input.png -resize 1200x -quality 85 output.png

# Using Python (PIL)
from PIL import Image
img = Image.open('input.png')
img.save('output.png', optimize=True, quality=85)
```

## Version Control

### What to Include
- ✓ Banner and logo images
- ✓ Key visualizations for README
- ✓ Sample outputs

### What to Exclude
- ✗ Temporary/test images
- ✗ Large high-resolution files (use external storage)
- ✗ Duplicate versions

## Placeholder Images

If you haven't generated visualizations yet, you can use placeholders:

```python
import matplotlib.pyplot as plt
import numpy as np

fig, ax = plt.subplots(figsize=(10, 6))
ax.text(0.5, 0.5, 'Visualization Coming Soon', 
        ha='center', va='center', fontsize=20)
ax.set_xlim(0, 1)
ax.set_ylim(0, 1)
ax.axis('off')
plt.savefig('images/placeholder.png', dpi=150, bbox_inches='tight')
```

## Contributing Visualizations

When adding new visualizations:

1. Ensure they follow naming conventions
2. Save in appropriate subdirectory
3. Use consistent styling
4. Include in documentation
5. Optimize file size
6. Test display on different devices

---

**Last Updated:** February 2026  
**Visualization Standards:** v1.0
