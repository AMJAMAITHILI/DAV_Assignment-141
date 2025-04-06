# DAV_Assignment-141
#  Sleep Health and Lifestyle Dataset – Data Analysis Project

This project performs a detailed analysis of the **Sleep Health and Lifestyle Dataset** using Python. The aim is to explore the data, derive insights, and demonstrate fundamental to advanced operations in **NumPy**, **Pandas**, and **Seaborn/Matplotlib**.

---

## Dataset Overview

The dataset provides health and lifestyle information for individuals. Key attributes include:

- `Person ID`: Unique identifier
- `Age`: Age of the individual
- `Gender`: 0 = Male, 1 = Female
- `Occupation`: Profession of the individual
- `Sleep Duration`: Average hours of sleep per night
- `Quality of Sleep`: Subjective score of sleep quality
- `Physical Activity Level`: Daily physical activity score
- `Stress Level`: Reported stress level
- `Heart Rate`: Average heart rate
- `BMI`: Body Mass Index value
- `BMI Category`: Categorized BMI (Normal, Overweight, etc.)

---

##  Operations Performed

###  Data Loading and Preprocessing
- Loaded dataset with `pandas.read_csv()`
- Inspected data using `.head()`, `.info()`, `.describe()`
- Verified data types and checked for missing/null values

### Basic NumPy and Pandas Operations
- **Array Slicing**: Sliced NumPy arrays from DataFrame values
- **Universal Functions**: Used `np.sqrt`, `np.square`, `np.log`, `np.exp` on numeric data
- **Aggregation Functions**: Applied `mean()`, `sum()`, `min()`, `max()`, `std()` across columns
- **Broadcasting**: Performed arithmetic between arrays and scalars or arrays of the same shape
- **Boolean Masking**: Used masks to filter rows (e.g., high stress or specific age groups)
- **Argsort & Sorting**: Sorted data using `np.argsort()` and `np.sort()`
- **Partial Sorting**: Retrieved top-N or bottom-N sorted results
- **Structured Arrays**: Created NumPy structured arrays with multiple dtypes
- **Hierarchical Indexing**: Grouped by multiple levels using multi-indexing in Pandas

###  Feature Engineering
- Added new column: `Sleep_Efficiency = Sleep Duration - Stress Level`
- Normalized the `Age` column using Z-score:
  ```python
  df['Age_zscore'] = (df['Age'] - df['Age'].mean()) / df['Age'].std()
  ```
- Boolean filtering: Extracted subsets like young adults (age 18–25)

### GroupBy Aggregation
- Grouped by `Occupation`: Mean sleep duration and stress levels
- Grouped by `BMI Category`: Average quality of sleep
- Grouped by both `Age` and `Gender`: Mean stress levels
- Used `.groupby().agg()` for multiple metric aggregation

### Pivot Tables
Created detailed summaries of the data:

- Pivot Table 1:
  ```python
  pd.pivot_table(df, index='BMI Category', values='Quality of Sleep', aggfunc='mean')
  ```
- Pivot Table 2:
  ```python
  pd.pivot_table(df, index='Occupation', columns='Gender', values='Sleep Duration', aggfunc='mean')
  ```
- Pivot Table 3:
  ```python
  pd.pivot_table(df, index='Age', columns='Gender', values='Stress Level', aggfunc='mean')
  ```
- All pivot tables were cross-validated with equivalent `groupby()` logic

### Merging Datasets
- Split the dataset into two (e.g., sleep and health aspects)
- Merged back using `pd.merge()` on `Person ID`

---

##  Data Visualization

Visualizations were created to uncover patterns:

- ■ Histogram of Age
  ```python
  sns.histplot(df['Age'], kde=True)
  ```
- ■ Box Plot of Sleep Duration by Gender
  ```python
  sns.boxplot(x='Gender', y='Sleep Duration', data=df)
  ```
- ■ Count Plot of Occupations
  ```python
  sns.countplot(y='Occupation', data=df)
  ```
- ■ Line Plot of Average Sleep Duration by Age and Gender
  ```python
  sns.lineplot(x='Age', y='Sleep Duration', hue='Gender', data=df.groupby(['Age', 'Gender'])['Sleep Duration'].mean().reset_index())
  ```

---

## How to Run

- Place the CSV file `Sleep_health_and_lifestyle_dataset.csv` in your working directory
- Open and run the Jupyter notebook (`analysis.ipynb`) or Python script (`analysis.py`)
- Ensure you have required libraries installed:

```bash
pip install pandas numpy matplotlib seaborn
```


## 🎓 Summary

This project demonstrates practical data analysis skills, including:

- Core NumPy and Pandas operations
- Feature engineering and normalization
- Group-level analysis and pivoting
- Merging datasets and advanced indexing
- Effective data visualization using Seaborn

The code and approach are modular and can be extended for predictive modeling, clustering, or interactive dashboards in future.



