# Pandas

## Definition

**Pandas** is an open-source [[Python]] library used for **data manipulation**, **data analysis**, and **data cleaning**. It provides powerful and easy-to-use data structures, such as the **Series** and **DataFrame**, for working with structured and tabular data.

Pandas is one of the most widely used libraries in [[Data Science]], [[Machine Learning]], and [[Artificial Intelligence]].

---

## Key Features

- Fast and efficient data manipulation.
- Easy handling of tabular data.
- Supports multiple file formats.
- Powerful data cleaning tools.
- Built-in statistical functions.
- Data filtering and sorting.
- Grouping and aggregation.
- Time series analysis.
- Integration with other Python libraries.

---

## Installation

Install Pandas using **pip**:

```bash
pip install pandas
```

Import Pandas in Python:

```python
import pandas as pd
```

The alias **`pd`** is the standard convention.

---

## Why Use Pandas?

Pandas simplifies working with data by allowing users to:

- Read data from files.
- Organize data into tables.
- Clean missing or incorrect values.
- Filter and sort records.
- Perform calculations.
- Analyze trends.
- Prepare datasets for [[Machine Learning]] models.

---

## Core Data Structures

### [[Series]]

A **Series** is a one-dimensional labeled array that can store any data type.

Example:

```python
import pandas as pd

numbers = pd.Series([10, 20, 30, 40])

print(numbers)
```

Output:

```
0    10
1    20
2    30
3    40
dtype: int64
```

---

### [[DataFrame]]

A **DataFrame** is a two-dimensional table consisting of rows and columns.

Example:

```python
import pandas as pd

student = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [20, 21, 19],
    "Marks": [90, 85, 95]
}

df = pd.DataFrame(student)

print(df)
```

Output:

```
      Name  Age  Marks
0    Alice   20     90
1      Bob   21     85
2  Charlie   19     95
```

---

## Reading Data

Pandas can read data from various file formats.

Examples:

```python
df = pd.read_csv("students.csv")
```

```python
df = pd.read_excel("students.xlsx")
```

```python
df = pd.read_json("data.json")
```

Supported formats include:

- CSV
- Excel
- JSON
- SQL Databases
- HTML Tables
- Parquet

---

## Writing Data

Save data to files.

Examples:

```python
df.to_csv("output.csv")
```

```python
df.to_excel("output.xlsx")
```

```python
df.to_json("output.json")
```

---

## Viewing Data

### First Rows

```python
df.head()
```

Returns the first five rows.

---

### Last Rows

```python
df.tail()
```

Returns the last five rows.

---

### Shape

```python
df.shape
```

Returns:

```
(rows, columns)
```

---

### Column Names

```python
df.columns
```

---

### Data Types

```python
df.dtypes
```

---

### Summary Information

```python
df.info()
```

---

### Statistical Summary

```python
df.describe()
```

---

## Selecting Data

### Select a Column

```python
df["Name"]
```

---

### Select Multiple Columns

```python
df[["Name", "Marks"]]
```

---

### Select Rows

```python
df.iloc[0]
```

Selects by integer position.

---

```python
df.loc[0]
```

Selects by index label.

---

## Filtering Data

Example:

```python
df[df["Marks"] > 90]
```

Returns students with marks greater than 90.

---

## Sorting Data

Ascending order:

```python
df.sort_values("Marks")
```

Descending order:

```python
df.sort_values("Marks", ascending=False)
```

---

## Handling Missing Data

Check missing values:

```python
df.isnull()
```

Count missing values:

```python
df.isnull().sum()
```

Remove missing values:

```python
df.dropna()
```

Fill missing values:

```python
df.fillna(0)
```

---

## Data Cleaning

Common operations include:

- Removing duplicates

```python
df.drop_duplicates()
```

- Renaming columns

```python
df.rename(columns={"Marks": "Score"})
```

- Changing data types

```python
df.astype(float)
```

---

## Grouping Data

Example:

```python
df.groupby("Department").mean()
```

Useful for:

- Average calculations
- Sum
- Count
- Maximum
- Minimum

---

## Aggregation Functions

Examples:

```python
df["Marks"].mean()
```

```python
df["Marks"].sum()
```

```python
df["Marks"].max()
```

```python
df["Marks"].min()
```

```python
df["Marks"].count()
```

---

## Common Operations

- Adding a new column

```python
df["Grade"] = "A"
```

---

- Deleting a column

```python
df.drop("Grade", axis=1)
```

---

- Changing values

```python
df["Marks"] = df["Marks"] + 5
```

---

## Advantages

- Easy to learn.
- Fast data manipulation.
- Supports large datasets.
- Rich built-in functions.
- Excellent integration with Python libraries.
- Ideal for preprocessing data before [[Machine Learning]].

---

## Limitations

- Consumes significant memory for very large datasets.
- Slower than some distributed frameworks for big data.
- Primarily designed for data that fits into memory.

---

## Applications

- [[Data Analysis]]
- [[Data Cleaning]]
- [[Data Science]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- Financial analysis
- Business intelligence
- Scientific research
- Data visualization preparation
- Statistical analysis

---

## Integration with Other Libraries

Pandas is commonly used with:

- [[NumPy]] — Numerical computing.
- [[Matplotlib]] — Data visualization.
- [[Seaborn]] — Statistical visualization.
- [[Scikit-learn]] — Machine Learning.
- [[TensorFlow]] — Deep Learning.
- [[PyTorch]] — Deep Learning.

---

## Real-World Examples

- Sales data analysis.
- Student record management.
- Financial reporting.
- Healthcare data analysis.
- Customer segmentation.
- Stock market analysis.
- Survey data processing.
- Data preprocessing for AI models.

---

## Related Notes

- [[Python]]
- [[NumPy]]
- [[Data Analysis]]
- [[Data Cleaning]]
- [[Data Science]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- [[Series]]
- [[DataFrame]]
- [[CSV]]
- [[JSON]]
- [[Excel]]
- [[SQL]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Scikit-learn]]
- [[TensorFlow]]
- [[PyTorch]]