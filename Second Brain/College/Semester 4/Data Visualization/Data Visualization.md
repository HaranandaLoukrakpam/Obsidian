# Data Visualization using Matplotlib and Seaborn

## Definition

**Data Visualization** is the process of representing data graphically using charts, graphs, and plots to make patterns, trends, relationships, and insights easier to understand.

In [[Python]], the two most popular libraries for data visualization are:

- [[Matplotlib]]
- [[Seaborn]]

Both libraries are widely used in [[Data Science]], [[Machine Learning]], [[Artificial Intelligence]], and data analysis.

---

# Matplotlib

## Definition

**Matplotlib** is an open-source Python library used to create **static, animated, and interactive visualizations**. It provides complete control over graphs and is the foundation of many other visualization libraries, including [[Seaborn]].

---

## Installation

```bash
pip install matplotlib
```

Import:

```python
import matplotlib.pyplot as plt
```

`pyplot` is commonly imported as **`plt`**.

---

## Features of Matplotlib

- Line charts
- Bar charts
- Pie charts
- Histograms
- Scatter plots
- Area charts
- Box plots
- Customizable colors and styles
- Figure customization
- Export graphs as images

---

## Basic Line Plot

```python
import matplotlib.pyplot as plt

x = [1,2,3,4]
y = [10,20,15,30]

plt.plot(x,y)
plt.show()
```

---

## Adding Labels

```python
plt.plot(x,y)

plt.title("Sales")
plt.xlabel("Month")
plt.ylabel("Revenue")

plt.show()
```

---

## Common Plot Types

### Line Plot

Used to show trends over time.

```python
plt.plot(x,y)
```

---

### Scatter Plot

Shows relationships between two variables.

```python
plt.scatter(x,y)
```

---

### Bar Chart

Compares different categories.

```python
plt.bar(x,y)
```

---

### Histogram

Shows the distribution of data.

```python
plt.hist(data)
```

---

### Pie Chart

Shows parts of a whole.

```python
plt.pie(values, labels=labels)
```

---

### Box Plot

Displays data distribution and detects outliers.

```python
plt.boxplot(data)
```

---

## Common Customizations

Change color

```python
plt.plot(x,y,color="red")
```

---

Change line style

```python
plt.plot(x,y,linestyle="--")
```

---

Add marker

```python
plt.plot(x,y,marker="o")
```

---

Grid

```python
plt.grid(True)
```

---

Legend

```python
plt.legend(["Sales"])
```

---

Save Figure

```python
plt.savefig("graph.png")
```

---

# Seaborn

## Definition

**Seaborn** is a high-level Python visualization library built on top of [[Matplotlib]]. It provides attractive default styles and simplifies the creation of statistical graphics.

---

## Installation

```bash
pip install seaborn
```

Import:

```python
import seaborn as sns
```

---

## Features of Seaborn

- Beautiful default themes
- Statistical visualizations
- Built-in datasets
- Easy plotting
- Automatic color palettes
- Works directly with [[Pandas]] DataFrames
- Less code than Matplotlib

---

## Load Sample Dataset

```python
import seaborn as sns

tips = sns.load_dataset("tips")
```

---

## Line Plot

```python
sns.lineplot(data=tips, x="size", y="total_bill")
```

---

## Scatter Plot

```python
sns.scatterplot(data=tips, x="total_bill", y="tip")
```

---

## Bar Plot

```python
sns.barplot(data=tips, x="day", y="total_bill")
```

---

## Histogram

```python
sns.histplot(data=tips, x="total_bill")
```

---

## Box Plot

```python
sns.boxplot(data=tips, x="day", y="total_bill")
```

---

## Violin Plot

Displays data distribution and density.

```python
sns.violinplot(data=tips, x="day", y="total_bill")
```

---

## Count Plot

Counts the number of observations in each category.

```python
sns.countplot(data=tips, x="day")
```

---

## Heatmap

Displays values using colors.

```python
sns.heatmap(data)
```

Common use:

- Correlation matrix
- Missing value visualization

---

## Pair Plot

Shows pairwise relationships among variables.

```python
sns.pairplot(tips)
```

---

## Correlation Heatmap

```python
corr = tips.corr(numeric_only=True)

sns.heatmap(corr, annot=True)
```

---

## Themes

Default

```python
sns.set_theme()
```

Dark Grid

```python
sns.set_style("darkgrid")
```

White Grid

```python
sns.set_style("whitegrid")
```

White

```python
sns.set_style("white")
```

Ticks

```python
sns.set_style("ticks")
```

---

# Matplotlib vs Seaborn

| Matplotlib | Seaborn |
|------------|----------|
| Low-level visualization library | High-level visualization library |
| More customizable | Easier to use |
| More code required | Less code required |
| Basic appearance | Attractive default themes |
| Supports all chart types | Focuses on statistical graphics |
| Foundation for Seaborn | Built on top of Matplotlib |

---

## When to Use Matplotlib

Use Matplotlib when you need:

- Complete control over plots
- Highly customized figures
- Publication-quality graphics
- Complex visualizations
- Animation

---

## When to Use Seaborn

Use Seaborn when you need:

- Quick statistical visualizations
- Beautiful default styles
- Data exploration
- Correlation analysis
- Visualization directly from [[Pandas]] DataFrames

---

## Applications

- [[Data Analysis]]
- [[Data Science]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- Business intelligence
- Financial analysis
- Healthcare analytics
- Scientific research
- Sales reporting
- Weather analysis

---

## Advantages

### Matplotlib

- Highly customizable
- Wide variety of chart types
- Large community support
- Excellent documentation

### Seaborn

- Simple syntax
- Attractive default styles
- Built-in statistical plots
- Easy integration with [[Pandas]]

---

## Limitations

### Matplotlib

- Requires more code.
- Steeper learning curve.

### Seaborn

- Less customization than Matplotlib.
- Depends on Matplotlib for rendering.

---

## Common Chart Types

| Chart | Purpose |
|--------|---------|
| Line Plot | Show trends over time |
| Bar Chart | Compare categories |
| Scatter Plot | Show relationships between variables |
| Histogram | Display frequency distribution |
| Pie Chart | Show proportions |
| Box Plot | Detect outliers and visualize spread |
| Violin Plot | Show data distribution and density |
| Heatmap | Visualize correlations or matrix data |
| Pair Plot | Explore relationships among multiple variables |

---

## Real-World Examples

- Stock market analysis
- Student performance reports
- Sales dashboards
- Website traffic analysis
- Healthcare data visualization
- Customer behavior analysis
- Weather forecasting
- Scientific experiments
- Machine Learning model evaluation

---

## Related Notes

- [[Python]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Pandas]]
- [[NumPy]]
- [[Data Visualization]]
- [[Data Analysis]]
- [[Data Science]]
- [[Machine Learning]]
- [[Artificial Intelligence]]
- [[Line Plot]]
- [[Scatter Plot]]
- [[Bar Chart]]
- [[Histogram]]
- [[Pie Chart]]
- [[Box Plot]]
- [[Violin Plot]]
- [[Heatmap]]
- [[Pair Plot]]
- [[Correlation Matrix]]