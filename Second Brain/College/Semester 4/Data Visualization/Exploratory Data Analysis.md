# Exploratory Data Analysis (EDA)

## Definition

**Exploratory Data Analysis (EDA)** is the process of examining, summarizing, and visualizing a dataset to understand its structure, identify patterns, detect anomalies, discover relationships, and prepare the data for further analysis or [[Machine Learning]].

EDA is one of the most important steps in the [[Data Science]] workflow because it helps analysts understand the data before building models.

---

## Objectives of EDA

The main objectives of Exploratory Data Analysis are to:

- Understand the dataset.
- Discover patterns and trends.
- Detect missing values.
- Identify outliers.
- Understand relationships between variables.
- Check data quality.
- Prepare data for modeling.
- Generate hypotheses for further analysis.

---

## Why is EDA Important?

EDA helps answer questions such as:

- What does the data look like?
- Are there missing values?
- Are there duplicate records?
- Which features are important?
- Are there outliers?
- Are variables correlated?
- Is the data suitable for machine learning?

Without EDA, building accurate and reliable [[Machine Learning]] models becomes difficult.

---

## Steps in Exploratory Data Analysis

### 1. Data Collection

Gather data from sources such as:

- CSV files
- Excel files
- Databases
- APIs
- Sensors
- Web scraping

---

### 2. Data Loading

Load data using libraries such as [[Pandas]].

Example:

```python
import pandas as pd

df = pd.read_csv("data.csv")
```

---

### 3. Inspect the Dataset

View the first rows

```python
df.head()
```

View the last rows

```python
df.tail()
```

Dataset shape

```python
df.shape
```

Column names

```python
df.columns
```

Data types

```python
df.dtypes
```

Dataset information

```python
df.info()
```

---

### 4. Summary Statistics

Generate descriptive statistics.

```python
df.describe()
```

Common statistics include:

- Mean
- Median
- Mode
- Minimum
- Maximum
- Standard deviation
- Variance
- Quartiles

---

### 5. Check Missing Values

Identify missing values.

```python
df.isnull().sum()
```

Handle missing values using:

```python
df.dropna()
```

or

```python
df.fillna()
```

---

### 6. Detect Duplicate Records

Check duplicates

```python
df.duplicated().sum()
```

Remove duplicates

```python
df.drop_duplicates()
```

---

### 7. Detect Outliers

Outliers are unusual observations that differ significantly from other data points.

Common methods:

- [[Box Plot]]
- [[Interquartile Range (IQR)]]
- Z-score
- Standard deviation

---

### 8. Analyze Feature Relationships

Find relationships between variables.

Methods include:

- Correlation matrix
- Scatter plots
- Pair plots
- Heatmaps

---

### 9. Visualize the Data

Use [[Matplotlib]] and [[Seaborn]] to create visualizations.

Common charts include:

- Line Plot
- Bar Chart
- Histogram
- Scatter Plot
- Box Plot
- Violin Plot
- Pie Chart
- Heatmap
- Pair Plot

---

### 10. Feature Engineering

Create or modify features to improve analysis or model performance.

Examples:

- Encoding categorical variables.
- Creating age groups.
- Combining columns.
- Scaling numerical values.

---

## Types of EDA

### Univariate Analysis

Analyzes **one variable** at a time.

Examples:

- Histogram
- Box Plot
- Frequency table

Purpose:

- Understand distribution.
- Detect outliers.
- Measure central tendency.

---

### Bivariate Analysis

Analyzes the relationship between **two variables**.

Examples:

- Scatter Plot
- Correlation
- Line Plot
- Bar Plot

Purpose:

- Identify relationships.
- Detect trends.

---

### Multivariate Analysis

Analyzes **more than two variables** simultaneously.

Examples:

- Pair Plot
- Heatmap
- Correlation Matrix
- Parallel Coordinates Plot

Purpose:

- Understand complex relationships.
- Discover hidden patterns.

---

## Descriptive Statistics Used in EDA

### Measures of Central Tendency

- Mean
- Median
- Mode

---

### Measures of Dispersion

- Range
- Variance
- Standard Deviation
- Interquartile Range (IQR)

---

### Distribution Measures

- Skewness
- Kurtosis

---

## Data Visualization in EDA

### [[Histogram]]

Shows the frequency distribution of data.

---

### [[Box Plot]]

Detects outliers and shows data spread.

---

### [[Scatter Plot]]

Shows relationships between two variables.

---

### [[Bar Chart]]

Compares categorical data.

---

### [[Line Plot]]

Shows trends over time.

---

### [[Heatmap]]

Displays correlation between variables.

---

### [[Pair Plot]]

Shows pairwise relationships among multiple variables.

---

### [[Violin Plot]]

Shows the distribution and density of data.

---

## Common EDA Functions in Pandas

| Function | Purpose |
|----------|---------|
| `head()` | View first rows |
| `tail()` | View last rows |
| `info()` | Dataset information |
| `describe()` | Summary statistics |
| `shape` | Dataset dimensions |
| `columns` | List column names |
| `dtypes` | Display data types |
| `isnull()` | Detect missing values |
| `dropna()` | Remove missing values |
| `fillna()` | Fill missing values |
| `duplicated()` | Find duplicates |
| `drop_duplicates()` | Remove duplicates |
| `value_counts()` | Count unique values |
| `corr()` | Correlation matrix |

---

## EDA Workflow

```
Data Collection
        ↓
Data Loading
        ↓
Data Inspection
        ↓
Data Cleaning
        ↓
Summary Statistics
        ↓
Visualization
        ↓
Relationship Analysis
        ↓
Feature Engineering
        ↓
Machine Learning Model
```

---

## Advantages

- Improves understanding of the dataset.
- Detects missing and inconsistent data.
- Identifies outliers.
- Reveals hidden patterns.
- Helps select useful features.
- Improves model accuracy.
- Reduces errors before modeling.

---

## Limitations

- Time-consuming for very large datasets.
- Requires domain knowledge for proper interpretation.
- Cannot guarantee causal relationships.
- Visualizations may become complex with high-dimensional data.

---

## Applications

- [[Data Science]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- Business analytics
- Healthcare analytics
- Financial analysis
- Market research
- Customer segmentation
- Fraud detection
- Scientific research

---

## Tools Used for EDA

- [[Python]]
- [[Pandas]]
- [[NumPy]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Scikit-learn]]
- [[Jupyter Notebook]]
- [[Google Colab]]

---

## Best Practices

- Understand the dataset before modeling.
- Handle missing values appropriately.
- Remove duplicate records.
- Detect and investigate outliers.
- Visualize data using multiple chart types.
- Check correlations between variables.
- Document findings for future reference.

---

## Real-World Examples

- Analyzing customer purchase behavior.
- Detecting fraudulent transactions.
- Understanding student performance.
- Predicting house prices.
- Analyzing stock market trends.
- Examining healthcare records.
- Sales trend analysis.
- Website traffic analysis.

---

## Related Notes

- [[Data Science]]
- [[Data Analysis]]
- [[Pandas]]
- [[NumPy]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- [[Data Cleaning]]
- [[Feature Engineering]]
- [[Dataset]]
- [[Feature]]
- [[Missing Values]]
- [[Outlier]]
- [[Correlation Matrix]]
- [[Histogram]]
- [[Scatter Plot]]
- [[Box Plot]]
- [[Heatmap]]
- [[Pair Plot]]
- [[Interquartile Range (IQR)]]
- [[Standard Deviation]]
- [[Mean]]
- [[Median]]
- [[Mode]]
- [[Jupyter Notebook]]
- [[Google Colab]]