# [[Basic Statistics]]

**Tags:** [[Mathematics]] [[Statistics]] [[Probability]] [[Descriptive Statistics]] [[Engineering Mathematics]] [[Data Analysis]]

---

# [[Definition]]

**[[Statistics]]** is the branch of [[Mathematics]] concerned with the **collection, organization, presentation, analysis, interpretation, and drawing conclusions from data**.

It helps summarize large amounts of information and make informed decisions based on data.

[[Statistics]] is broadly divided into:

- [[Descriptive Statistics]]
- [[Inferential Statistics]]

---

# [[Types of Statistics]]

## [[Descriptive Statistics]]

[[Descriptive Statistics]] involves organizing, summarizing, and presenting data in a meaningful way.

It answers questions such as:

- What is the average?
- How spread out is the data?
- What is the most common value?

Examples

- [[Arithmetic Mean]]
- [[Median]]
- [[Mode]]
- [[Variance]]
- [[Standard Deviation]]

---

## [[Inferential Statistics]]

[[Inferential Statistics]] uses sample data to draw conclusions or make predictions about an entire population.

Examples

- [[Hypothesis Testing]]
- [[Confidence Interval]]
- [[Regression Analysis]]
- [[ANOVA]]

---

# [[Basic Terminology]]

## [[Data]]

[[Data]] are facts, observations, or measurements collected for analysis.

Example

Student marks

$$
70,\;75,\;82,\;90,\;65
$$

---

## [[Population]]

A **[[Population]]** is the complete collection of all observations or individuals under study.

Example

All students in a university.

---

## [[Sample]]

A **[[Sample]]** is a subset of the [[Population]] selected for analysis.

Example

100 students selected from a university.

---

## [[Variable]]

A [[Variable]] is a characteristic that can take different values.

Examples

- Height
- Weight
- Age
- Salary

---

# [[Types of Variables]]

## [[Qualitative Variable]]

Also called a **Categorical Variable**.

Describes qualities or categories.

Examples

- Gender
- Blood Group
- Eye Color

---

## [[Quantitative Variable]]

Represents numerical values.

Examples

- Height
- Income
- Marks

---

### [[Discrete Variable]]

A [[Discrete Variable]] can take countable values.

Examples

- Number of students
- Number of books
- Number of cars

---

### [[Continuous Variable]]

A [[Continuous Variable]] can take infinitely many values within an interval.

Examples

- Height
- Weight
- Temperature
- Time

---

# [[Data Classification]]

## [[Primary Data]]

[[Primary Data]] are collected directly by the researcher.

Examples

- Surveys
- Interviews
- Experiments

---

## [[Secondary Data]]

[[Secondary Data]] are collected by someone else.

Examples

- Government Reports
- Census Data
- Research Papers

---

# [[Frequency Distribution]]

A [[Frequency Distribution]] organizes data according to how often each value occurs.

Example

| Marks | Frequency |
|------:|----------:|
|10|2|
|20|5|
|30|8|
|40|6|

---

# [[Measures of Central Tendency]]

These measures describe the center of a dataset.

---

## [[Arithmetic Mean]]

The [[Arithmetic Mean]] is the average of all observations.

Formula

$$
\bar{x}=\frac{\sum x}{n}
$$

where

- $\bar{x}$ = Mean
- $x$ = Observation
- $n$ = Number of observations

Example

$$
5,\;8,\;10,\;12
$$

$$
\bar{x}=\frac{5+8+10+12}{4}=8.75
$$

---

## [[Median]]

The [[Median]] is the middle value after arranging the data in ascending order.

If $n$ is odd

$$
Median=\left(\frac{n+1}{2}\right)^{th}\text{ observation}
$$

If $n$ is even

$$
Median=\frac{\text{Middle Two Values}}{2}
$$

Example

$$
2,\;5,\;8,\;9,\;12
$$

Median

$$
8
$$

---

## [[Mode]]

The [[Mode]] is the value that occurs most frequently.

Example

$$
2,\;4,\;4,\;5,\;6,\;6,\;6,\;8
$$

Mode

$$
6
$$

---

# [[Measures of Dispersion]]

These measures describe the spread of the data.

---

## [[Range]]

The [[Range]] is the difference between the largest and smallest observations.

Formula

$$
Range=Maximum-Minimum
$$

---

## [[Variance]]

[[Variance]] measures the average squared deviation from the mean.

### Population Variance

$$
\sigma^2=\frac{\sum(x-\mu)^2}{N}
$$

### Sample Variance

$$
s^2=\frac{\sum(x-\bar{x})^2}{n-1}
$$

---

## [[Standard Deviation]]

The [[Standard Deviation]] is the positive square root of the [[Variance]].

Population

$$
\sigma=\sqrt{\sigma^2}
$$

Sample

$$
s=\sqrt{s^2}
$$

Properties

- Always non-negative.
- Larger value indicates greater variation.
- Smaller value indicates greater consistency.

---

## [[Coefficient of Variation]]

The [[Coefficient of Variation]] measures relative variability.

Formula

$$
CV=\frac{\sigma}{\mu}\times100\%
$$

---

# [[Measures of Position]]

## [[Quartiles]]

[[Quartiles]] divide ordered data into four equal parts.

- $Q_1$ → First Quartile
- $Q_2$ → Second Quartile ([[Median]])
- $Q_3$ → Third Quartile

---

## [[Percentiles]]

[[Percentiles]] divide data into one hundred equal parts.

Example

The 90th percentile is the value below which 90% of observations lie.

---

# [[Skewness]]

[[Skewness]] measures the symmetry of a distribution.

## [[Symmetric Distribution]]

$$
Mean=Median=Mode
$$

---

## [[Positive Skewness]]

Long tail on the right.

$$
Mean>Median>Mode
$$

---

## [[Negative Skewness]]

Long tail on the left.

$$
Mean<Median<Mode
$$

---

# [[Kurtosis]]

[[Kurtosis]] measures the peakedness of a distribution.

Types

- [[Leptokurtic Distribution]]
- [[Mesokurtic Distribution]]
- [[Platykurtic Distribution]]

---

# [[Correlation]]

[[Correlation]] measures the strength and direction of the relationship between two variables.

Coefficient

$$
-1\le r\le1
$$

Interpretation

- $r=1$ → Perfect Positive Correlation
- $r=-1$ → Perfect Negative Correlation
- $r=0$ → No Linear Correlation

---

# [[Data Presentation]]

Common methods

- [[Frequency Table]]
- [[Bar Graph]]
- [[Histogram]]
- [[Pie Chart]]
- [[Line Graph]]
- [[Box Plot]]
- [[Scatter Plot]]

---

# [[Sampling Methods]]

## [[Random Sampling]]

Every member of the [[Population]] has an equal chance of selection.

---

## [[Systematic Sampling]]

Every $k^{th}$ observation is selected.

---

## [[Stratified Sampling]]

The [[Population]] is divided into homogeneous groups before sampling.

---

## [[Cluster Sampling]]

The [[Population]] is divided into clusters, and entire clusters are selected randomly.

---

# [[Common Statistical Distributions]]

- [[Normal Distribution]]
- [[Binomial Distribution]]
- [[Poisson Distribution]]
- [[Uniform Distribution]]

---

# [[Applications of Statistics]]

## [[Engineering]]

- Quality Control
- Reliability Testing
- Process Optimization

---

## [[Computer Science]]

- [[Machine Learning]]
- [[Data Science]]
- [[Artificial Intelligence]]
- [[Data Mining]]

---

## [[Business]]

- Sales Forecasting
- Market Research
- Customer Analysis

---

## [[Healthcare]]

- Clinical Trials
- Epidemiology
- Medical Research

---

# [[Formula Sheet]]

## [[Arithmetic Mean]]

$$
\bar{x}=\frac{\sum x}{n}
$$

---

## [[Population Variance]]

$$
\sigma^2=\frac{\sum(x-\mu)^2}{N}
$$

---

## [[Sample Variance]]

$$
s^2=\frac{\sum(x-\bar{x})^2}{n-1}
$$

---

## [[Standard Deviation]]

$$
\sigma=\sqrt{\sigma^2}
$$

---

## [[Range]]

$$
Range=Maximum-Minimum
$$

---

## [[Coefficient of Variation]]

$$
CV=\frac{\sigma}{\mu}\times100\%
$$

---

## [[Correlation Coefficient]]

$$
-1\le r\le1
$$

---

# [[Problem Solving Strategy]]

1. Identify whether the data represent a [[Population]] or a [[Sample]].
2. Organize the data into a [[Frequency Distribution]] if necessary.
3. Compute the appropriate [[Measure of Central Tendency]].
4. Compute the appropriate [[Measure of Dispersion]].
5. Examine [[Skewness]] and [[Kurtosis]].
6. Interpret the results.
7. Present the findings using suitable graphs or charts.

---

# [[Common Mistakes]]

- Confusing population formulas with sample formulas.
- Forgetting to divide by $n-1$ for [[Sample Variance]].
- Assuming [[Correlation]] implies causation.
- Ignoring outliers before calculating the [[Arithmetic Mean]].
- Choosing the wrong measure of central tendency.

---

# [[Summary]]

**[[Statistics]]** is the science of collecting, organizing, analyzing, interpreting, and presenting data. It is fundamental to engineering, science, business, economics, [[Artificial Intelligence]], [[Machine Learning]], and research.

Basic statistics focuses on describing data using measures such as the [[Arithmetic Mean]], [[Median]], [[Mode]], [[Variance]], and [[Standard Deviation]], while also understanding [[Probability Distribution]]s, [[Sampling Methods]], and relationships between variables.

---

# [[Related Notes]]

- [[Probability]]
- [[Descriptive Statistics]]
- [[Inferential Statistics]]
- [[Data Analysis]]
- [[Arithmetic Mean]]
- [[Median]]
- [[Mode]]
- [[Variance]]
- [[Standard Deviation]]
- [[Correlation]]
- [[Random Variables]]
- [[Normal Distribution]]
- [[Engineering Mathematics]]
- [[Mathematics Formula Sheet]]