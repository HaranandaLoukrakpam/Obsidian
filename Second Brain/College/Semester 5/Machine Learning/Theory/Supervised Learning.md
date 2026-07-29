# Supervised Learning

**Tags:** [[Machine Learning]] [[College/Semester 5/Machine Learning/Theory/Supervised Learning]] [[Regression]] [[Linear Regression]] [[Multiple Regression]] [[Classification]] [[Logistic Regression]] [[Decision Trees]] [[k-Nearest Neighbors]] [[Support Vector Machines]] [[Model Evaluation]] [[Accuracy]] [[Precision]] [[Recall]] [[F1 Score]]

---

# Introduction to Supervised Learning

[[College/Semester 5/Machine Learning/Theory/Supervised Learning]] is one of the most widely used types of Machine Learning where the model learns from **labeled data**.

A labeled dataset contains:

- Input variables (Features)
    
- Correct output values (Labels)
    

The objective is to learn a mapping between inputs and outputs so that the model can make accurate predictions on unseen data.

---

## Basic Concept

```text
Input (Features)
       ↓
Training Algorithm
       ↓
Learn Relationship
       ↓
Prediction
```

Example:

|Hours Studied|Exam Result|
|---|---|
|2|Fail|
|4|Pass|
|6|Pass|
|8|Pass|

The model learns the relationship between study hours and exam outcomes.

---

# Types of Supervised Learning

Supervised Learning is divided into two major categories:

```text
Supervised Learning
│
├── Regression
│
└── Classification
```

---

# Regression

[[Regression]] is used when the target variable is **continuous numerical data**.

Examples:

- House price prediction
    
- Salary prediction
    
- Temperature forecasting
    
- Sales prediction
    

Output examples:

```text
$150,000
$250,000
32.5°C
75.2
```

---

# Linear Regression

[[Linear Regression]] is the simplest regression algorithm.

It models a linear relationship between:

- Independent Variable (Feature)
    
- Dependent Variable (Target)
    

---

## Idea

The algorithm attempts to fit the best straight line through the data.

Equation:

```text
y = mx + c
```

Where:

- y = Predicted value
    
- x = Input feature
    
- m = Slope
    
- c = Intercept
    

---

## Example

Predicting house prices:

|House Size (sq ft)|Price ($)|
|---|---|
|1000|100,000|
|1500|150,000|
|2000|200,000|

The model learns:

```text
Larger House → Higher Price
```

---

## Graph Representation

```text
Price
 ^
 |
 |        *
 |      *
 |    *
 |  *
 |________________> House Size
```

The line represents the prediction model.

---

## Advantages

- Simple
    
- Fast
    
- Easy to interpret
    
- Works well for linear relationships
    

---

## Disadvantages

- Assumes linearity
    
- Sensitive to outliers
    
- Cannot model complex relationships
    

---

# Multiple Regression

[[Multiple Regression]] extends Linear Regression by using multiple input features.

Equation:

```text
y = b0 + b1x1 + b2x2 + b3x3 + ... + bnxn
```

Where:

- y = Target value
    
- x1, x2, x3 = Features
    
- b1, b2, b3 = Coefficients
    

---

## Example

House price prediction based on:

- House size
    
- Number of bedrooms
    
- Location score
    
- Age of house
    

Dataset:

|Size|Bedrooms|Age|Price|
|---|---|---|---|
|1200|2|10|150000|
|1800|3|5|250000|
|2500|4|2|400000|

Multiple Regression considers all features simultaneously.

---

## Advantages

- More realistic
    
- Better predictive power
    
- Handles multiple variables
    

---

## Disadvantages

- More computationally expensive
    
- Risk of overfitting
    
- Sensitive to multicollinearity
    

---

# Classification

[[Classification]] is used when the target variable is categorical.

Examples:

- Spam or Not Spam
    
- Disease or No Disease
    
- Pass or Fail
    
- Fraud or Legitimate
    

Output values belong to predefined classes.

---

# Logistic Regression

[[Logistic Regression]] is one of the most popular classification algorithms.

Despite its name, it is used for classification rather than regression.

---

## Purpose

Predicts the probability that a data point belongs to a particular class.

Output:

```text
0 → Negative Class

1 → Positive Class
```

---

## Sigmoid Function

Logistic Regression uses the Sigmoid Function.

Formula:

```text
P = 1 / (1 + e^-z)
```

Output range:

```text
0 to 1
```

---

## Example

Email Spam Detection

|Email|Output|
|---|---|
|Win Money Now|Spam|
|Meeting Tomorrow|Not Spam|

The model predicts probabilities:

```text
Spam Probability = 0.92
```

Since 0.92 > 0.5

Prediction:

```text
Spam
```

---

## Advantages

- Simple
    
- Fast
    
- Interpretable
    
- Produces probabilities
    

---

## Disadvantages

- Assumes linear decision boundary
    
- Less effective on highly complex datasets
    

---

# Decision Trees

[[Decision Trees]] are supervised learning algorithms that make decisions using a tree-like structure.

---

## Structure

```text
Root Node
    |
Decision
   / \
 Yes  No
 /      \
Leaf    Leaf
```

---

## Example

Loan Approval

```text
Income > $50,000?

       /      \
     Yes      No

    Approve   Reject
```

---

## Components

### Root Node

Starting point of the tree.

### Internal Node

Represents a decision.

### Branch

Outcome of a decision.

### Leaf Node

Final prediction.

---

## Advantages

- Easy to understand
    
- Visual representation
    
- Handles numerical and categorical data
    
- Requires little preprocessing
    

---

## Disadvantages

- Can overfit
    
- Sensitive to small data changes
    
- Deep trees become complex
    

---

# k-Nearest Neighbors (kNN)

[[k-Nearest Neighbors]] is a simple instance-based learning algorithm.

It predicts based on the most similar data points.

---

## Working Principle

1. Choose K neighbors.
    
2. Calculate distance.
    
3. Find nearest points.
    
4. Majority vote (classification).
    

---

## Example

Suppose:

```text
K = 3
```

Nearest neighbors:

```text
Spam
Spam
Not Spam
```

Prediction:

```text
Spam
```

Because 2 out of 3 neighbors are Spam.

---

## Distance Metric

Most commonly:

### Euclidean Distance

Formula:

```text
Distance =
√((x₂−x₁)² + (y₂−y₁)²)
```

---

## Advantages

- Simple
    
- No training phase
    
- Effective for small datasets
    

---

## Disadvantages

- Slow for large datasets
    
- Sensitive to feature scaling
    
- Performance depends on K
    

---

# Support Vector Machines (SVM)

[[Support Vector Machines]] are powerful supervised learning algorithms used for both classification and regression.

Their primary goal is to find the optimal boundary that separates classes.

---

## Concept

SVM searches for a hyperplane that maximizes the margin between classes.

---

## Example

```text
Class A  |  Hyperplane  |  Class B
```

The hyperplane creates the largest possible separation.

---

## Support Vectors

Support vectors are the data points closest to the boundary.

These points determine the position of the hyperplane.

---

## Kernel Trick

When data is not linearly separable, SVM uses kernels.

Common kernels:

- Linear Kernel
    
- Polynomial Kernel
    
- Radial Basis Function (RBF)
    
- Sigmoid Kernel
    

---

## Advantages

- High accuracy
    
- Effective in high dimensions
    
- Works well with complex boundaries
    

---

## Disadvantages

- Computationally expensive
    
- Difficult to interpret
    
- Slower on very large datasets
    

---

# Comparison of Algorithms

|Algorithm|Problem Type|Output|
|---|---|---|
|Linear Regression|Regression|Continuous Value|
|Multiple Regression|Regression|Continuous Value|
|Logistic Regression|Classification|Class Label|
|Decision Tree|Classification/Regression|Class or Value|
|kNN|Classification/Regression|Class or Value|
|SVM|Classification/Regression|Class or Value|

---

# Model Evaluation

[[Model Evaluation]] measures how well a trained model performs on unseen data.

Evaluation metrics help determine:

- Accuracy
    
- Reliability
    
- Generalization ability
    

---

# Confusion Matrix

A confusion matrix summarizes classification performance.

||Predicted Positive|Predicted Negative|
|---|---|---|
|Actual Positive|TP|FN|
|Actual Negative|FP|TN|

Where:

- TP = True Positive
    
- TN = True Negative
    
- FP = False Positive
    
- FN = False Negative
    

---

# Accuracy

[[Accuracy]] measures the proportion of correct predictions.

Formula:

```text
Accuracy =
(TP + TN)
/
(TP + TN + FP + FN)
```

---

## Example

100 predictions

Correct predictions = 90

```text
Accuracy = 90%
```

---

## Advantages

- Easy to understand
    
- Useful for balanced datasets
    

---

## Limitation

Can be misleading for imbalanced datasets.

---

# Precision

[[Precision]] measures how many predicted positives are actually positive.

Formula:

```text
Precision =
TP
/
(TP + FP)
```

---

## Example

Predicted Fraud Cases = 100

Actual Fraud Cases = 80

```text
Precision = 80%
```

---

## Important When

False positives are costly.

Examples:

- Spam filtering
    
- Fraud detection
    

---

# Recall

[[Recall]] measures how many actual positives were correctly identified.

Formula:

```text
Recall =
TP
/
(TP + FN)
```

---

## Example

Actual Fraud Cases = 100

Detected Fraud Cases = 90

```text
Recall = 90%
```

---

## Important When

Missing positives is dangerous.

Examples:

- Cancer diagnosis
    
- Disease detection
    
- Security systems
    

---

# F1 Score

[[F1 Score]] combines Precision and Recall into a single metric.

Formula:

```text
F1 Score =
2 ×
(Precision × Recall)
/
(Precision + Recall)
```

---

## Why Use F1 Score?

When datasets are imbalanced:

```text
Accuracy Alone
↓
Can Be Misleading
```

F1 Score provides a balanced evaluation.

---

# Accuracy vs Precision vs Recall vs F1 Score

|Metric|Measures|Best Used When|
|---|---|---|
|Accuracy|Overall correctness|Balanced datasets|
|Precision|Correct positive predictions|False positives are costly|
|Recall|Capturing actual positives|False negatives are costly|
|F1 Score|Balance of Precision and Recall|Imbalanced datasets|

---

# Advantages of Supervised Learning

- High prediction accuracy
    
- Clear performance metrics
    
- Well-understood algorithms
    
- Useful for many real-world applications
    

---

# Limitations of Supervised Learning

- Requires labeled data
    
- Labeling can be expensive
    
- Risk of overfitting
    
- Performance depends heavily on data quality
    

---

# Real-World Applications

## Healthcare

- Disease diagnosis
    
- Cancer detection
    
- Medical image classification
    

---

## Finance

- Credit scoring
    
- Fraud detection
    
- Risk assessment
    

---

## Marketing

- Customer churn prediction
    
- Customer segmentation
    
- Purchase prediction
    

---

## Education

- Student performance prediction
    
- Automated grading
    

---

## Cybersecurity

- Spam detection
    
- Intrusion detection
    
- Malware classification
    

---

# Summary

[[College/Semester 5/Machine Learning/Theory/Supervised Learning]] is a Machine Learning approach that learns from labeled data to make predictions on unseen data. It is divided into two major categories: [[Regression]], which predicts continuous numerical values, and [[Classification]], which predicts categorical outcomes.

Important regression algorithms include [[Linear Regression]] and [[Multiple Regression]], while major classification algorithms include [[Logistic Regression]], [[Decision Trees]], [[k-Nearest Neighbors]], and [[Support Vector Machines]]. Model performance is commonly evaluated using metrics such as [[Accuracy]], [[Precision]], [[Recall]], and [[F1 Score]], each providing unique insights into prediction quality.

---

# Key Terms

- [[College/Semester 5/Machine Learning/Theory/Supervised Learning]]
    
- [[Regression]]
    
- [[Linear Regression]]
    
- [[Multiple Regression]]
    
- [[Classification]]
    
- [[Logistic Regression]]
    
- [[Decision Trees]]
    
- [[k-Nearest Neighbors]]
    
- [[Support Vector Machines]]
    
- [[Confusion Matrix]]
    
- [[Accuracy]]
    
- [[Precision]]
    
- [[Recall]]
    
- [[F1 Score]]
    
- [[True Positive]]
    
- [[True Negative]]
    
- [[False Positive]]
    
- [[False Negative]]