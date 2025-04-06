# DAV_Assignment-141
# Sleep Health and Lifestyle Dataset - Data Analysis

This project performs comprehensive data analysis on the Sleep Health and Lifestyle Dataset using Python, NumPy, Pandas, and Seaborn/Matplotlib. The analysis includes data exploration, visualization, transformation, and advanced operations.

## Contents

### Data Loading and Cleaning
- Loading CSV data using Pandas
- Basic inspection: `.info()`, `.describe()`, `.head()`
- Checking and handling missing values

### Basic Analysis using NumPy and Pandas
- Array slicing
- Universal functions (e.g., `np.sqrt`, `np.log`, etc.)
- Aggregations (`mean`, `sum`, `std`, etc.)
- Broadcasting operations
- Boolean masking and filtering
- Sorting with `argsort` and partial sorting
- Structured arrays
- Hierarchical indexing in Pandas

### Feature Engineering
- Creating new columns (e.g., Sleep Efficiency)
- Z-score normalization of age
- Boolean indexing using NumPy logic

### Grouping and Aggregation
- Grouping using `groupby()` on categorical columns (e.g., Occupation, Gender)
- Aggregating numerical features (mean, count, etc.)
- GroupBy comparisons with pivot tables

### Pivot Tables
- Pivot table 1: Average Quality of Sleep by BMI Category
- Pivot table 2: Sleep Duration by Occupation and Gender
- Pivot table 3: Average Stress Level by Age and Gender

### Merging Datasets
- Simulated merging of two DataFrames on 'Person ID' using `pd.merge()`

### Data Visualization
- Histogram of Age
- Box plot of Sleep Duration vs. Gender
- Countplot for Occupation distribution
- Line plot: Average Sleep Duration by Age and Gender

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn


