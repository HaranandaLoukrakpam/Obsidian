# Unsupervised Learning

**Tags:** [[Machine Learning]] [[College/Semester 5/Machine Learning/Theory/Unsupervised Learning]] [[Clustering]] [[K-Means Clustering]] [[Hierarchical Clustering]] [[Dimensionality Reduction]] [[Principal Component Analysis (PCA)]] [[Market Segmentation]] [[Document Clustering]] [[Association Rule Mining]] [[Apriori Algorithm]] [[FP-Growth Algorithm]] [[Outlier Detection]] [[Isolation Forest]] [[One-Class SVM]]

---

# Introduction to Unsupervised Learning

[[College/Semester 5/Machine Learning/Theory/Unsupervised Learning]] is a type of [[Machine Learning]] where the algorithm learns from **unlabeled data**. Unlike [[College/Semester 5/Machine Learning/Theory/Supervised Learning]], there are no predefined target labels or correct outputs.

The goal of unsupervised learning is to discover hidden patterns, structures, or relationships within the data.

It answers questions such as:

- Which customers have similar buying habits?
    
- Which news articles discuss similar topics?
    
- Which transactions are unusual?
    
- Which products are frequently purchased together?
    

---

# Characteristics of Unsupervised Learning

- Uses **unlabeled data**
    
- Discovers hidden patterns automatically
    
- Groups similar observations together
    
- Identifies anomalies
    
- Finds relationships between variables
    
- Often used for exploratory data analysis
    

---

# Basic Workflow

```text
Raw Data
     ↓
Unsupervised Learning Algorithm
     ↓
Hidden Patterns / Groups / Relationships
```

---

# Types of Unsupervised Learning

The major categories of unsupervised learning are:

```text
Unsupervised Learning
│
├── Clustering
│
├── Dimensionality Reduction
│
├── Association Rule Mining
│
└── Outlier Detection
```

---

# Clustering

[[Clustering]] is the process of grouping similar data points together.

Objects within the same cluster are more similar to each other than to objects in different clusters.

Example:

A company groups customers according to:

- Age
    
- Income
    
- Shopping habits
    

Without knowing customer categories beforehand.

---

# Applications of Clustering

- Customer segmentation
    
- Image segmentation
    
- Social network analysis
    
- Medical diagnosis
    
- Recommendation systems
    
- Document organization
    

---

# K-Means Clustering

[[K-Means Clustering]] is one of the simplest and most widely used clustering algorithms.

The objective is to divide data into **K clusters**, where each data point belongs to the cluster with the nearest centroid.

---

## Working Principle

1. Choose the number of clusters (**K**).
    
2. Randomly initialize **K centroids**.
    
3. Assign every data point to the nearest centroid.
    
4. Recalculate the centroid of each cluster.
    
5. Repeat until the centroids no longer change significantly.
    

---

## Workflow

```text
Choose K
      ↓
Initialize Centroids
      ↓
Assign Points to Nearest Centroid
      ↓
Update Centroids
      ↓
Repeat Until Stable
```

---

## Example

Suppose a shopping mall wants to classify customers into three groups:

- Budget shoppers
    
- Regular shoppers
    
- Premium shoppers
    

Set:

```text
K = 3
```

The algorithm automatically groups customers based on purchasing behavior.

---

## Choosing the Value of K

One common method is the **Elbow Method**.

The idea is to:

- Train the model using different values of K.
    
- Plot the clustering error.
    
- Select the point where the decrease in error begins to slow (forming an "elbow").
    

---

## Advantages

- Easy to understand
    
- Fast for large datasets
    
- Efficient implementation
    
- Works well with spherical clusters
    

---

## Disadvantages

- Must choose K beforehand
    
- Sensitive to outliers
    
- Sensitive to centroid initialization
    
- Performs poorly with irregularly shaped clusters
    

---

# Hierarchical Clustering

[[Hierarchical Clustering]] creates a hierarchy of clusters rather than dividing data into a fixed number of groups.

The output is represented using a **Dendrogram**.

---

## Types

### Agglomerative Clustering

Bottom-up approach.

Every observation starts as its own cluster.

Clusters are merged repeatedly until only one cluster remains.

```text
A  B  C  D

↓

AB

↓

ABC

↓

ABCD
```

---

### Divisive Clustering

Top-down approach.

Start with one large cluster.

Repeatedly divide it into smaller clusters.

---

# Dendrogram

A **Dendrogram** is a tree diagram showing how clusters merge or split.

The height of each merge represents the distance between clusters.

Cutting the dendrogram at different heights produces different numbers of clusters.

---

## Advantages

- No need to specify K initially
    
- Produces a hierarchical structure
    
- Useful for visual analysis
    
- Works well with smaller datasets
    

---

## Disadvantages

- Computationally expensive
    
- Slow for large datasets
    
- Difficult to modify once clusters are formed
    

---

# K-Means vs Hierarchical Clustering

|Feature|K-Means|Hierarchical|
|---|---|---|
|Number of Clusters|Must specify K|Determined from dendrogram|
|Speed|Fast|Slower|
|Large Datasets|Good|Poor|
|Output|Clusters|Hierarchical Tree|
|Sensitive to Outliers|Yes|Moderate|

---

# Dimensionality Reduction

[[Dimensionality Reduction]] reduces the number of input features while preserving as much useful information as possible.

Many datasets contain hundreds or thousands of features, many of which may be redundant or highly correlated.

Reducing dimensions helps improve:

- Training speed
    
- Memory efficiency
    
- Visualization
    
- Model performance
    
- Noise reduction
    

---

# Principal Component Analysis (PCA)

[[Principal Component Analysis (PCA)]] is the most popular dimensionality reduction technique.

PCA transforms the original features into a new set of **principal components**.

These principal components:

- Are uncorrelated
    
- Capture maximum variance
    
- Reduce redundancy
    

---

## Working Principle

1. Standardize the data.
    
2. Compute the covariance matrix.
    
3. Calculate eigenvalues and eigenvectors.
    
4. Select principal components with the highest variance.
    
5. Transform the original dataset.
    

---

## Example

Original dataset:

```text
20 Features
```

After PCA:

```text
5 Principal Components
```

Most important information is retained while reducing complexity.

---

## Applications

- Image compression
    
- Face recognition
    
- Data visualization
    
- Noise reduction
    
- Feature extraction
    

---

## Advantages

- Faster model training
    
- Removes redundant features
    
- Reduces overfitting
    
- Easier visualization
    

---

## Disadvantages

- Reduced interpretability
    
- Information loss
    
- Components may not have meaningful real-world interpretations
    

---

# Applications of Unsupervised Learning

---

# Market Segmentation

[[Market Segmentation]] divides customers into groups with similar characteristics.

Businesses use clustering based on:

- Age
    
- Income
    
- Purchase history
    
- Shopping frequency
    
- Geographic location
    

Benefits:

- Personalized marketing
    
- Better advertisements
    
- Improved customer satisfaction
    

---

# Document Clustering

[[Document Clustering]] automatically groups documents discussing similar topics.

Examples:

- News categorization
    
- Research paper organization
    
- Search engine indexing
    
- Digital libraries
    

Instead of manually labeling every document, clustering algorithms organize documents based on content similarity.

---

# Association Rule Mining

[[Association Rule Mining]] discovers relationships between items that frequently occur together in large datasets.

It is widely used in:

- Retail
    
- E-commerce
    
- Healthcare
    
- Banking
    

Example:

Customers purchasing:

```text
Bread
```

often also purchase:

```text
Butter
```

---

# Important Concepts

### Support

Measures how frequently an itemset appears in the dataset.

---

### Confidence

Measures the probability that item B is purchased when item A is purchased.

---

### Lift

Measures how much more likely two items occur together compared to random chance.

---

# Apriori Algorithm

[[Apriori Algorithm]] is one of the earliest and most widely used algorithms for association rule mining.

---

## Working Principle

1. Find frequent individual items.
    
2. Generate larger itemsets.
    
3. Remove infrequent itemsets.
    
4. Generate association rules.
    

---

## Example

Transactions:

|Transaction|Items|
|---|---|
|1|Milk, Bread|
|2|Milk, Bread, Butter|
|3|Bread, Butter|
|4|Milk, Butter|

The algorithm may discover:

```text
Milk → Bread
```

---

## Advantages

- Easy to understand
    
- Produces meaningful association rules
    
- Widely studied
    

---

## Disadvantages

- Generates many candidate itemsets
    
- Slow on very large datasets
    
- High memory consumption
    

---

# FP-Growth Algorithm

[[FP-Growth Algorithm]] improves upon Apriori by avoiding repeated candidate generation.

Instead, it builds an **FP-Tree (Frequent Pattern Tree)**.

---

## Working Principle

1. Scan the dataset.
    
2. Build the FP-Tree.
    
3. Mine frequent patterns directly from the tree.
    
4. Generate association rules.
    

---

## Advantages

- Faster than Apriori
    
- Lower memory usage
    
- Efficient for large datasets
    
- Handles dense datasets well
    

---

## Disadvantages

- FP-Tree construction can be complex
    
- More difficult to implement
    

---

# Apriori vs FP-Growth

|Feature|Apriori|FP-Growth|
|---|---|---|
|Candidate Generation|Yes|No|
|Speed|Slower|Faster|
|Memory Usage|Higher|Lower|
|Large Datasets|Less Suitable|Highly Suitable|
|Implementation|Simpler|More Complex|

---

# Outlier Detection

[[Outlier Detection]] identifies observations that differ significantly from the majority of the data.

Outliers may indicate:

- Fraud
    
- Network attacks
    
- Sensor failures
    
- Medical abnormalities
    
- Manufacturing defects
    

---

## Applications

- Credit card fraud detection
    
- Intrusion detection
    
- Financial auditing
    
- Industrial monitoring
    
- Medical diagnosis
    

---

# Isolation Forest

[[Isolation Forest]] is an anomaly detection algorithm specifically designed to identify outliers.

Instead of profiling normal data, it isolates observations using random decision trees.

The key idea is:

- Normal observations require many splits to isolate.
    
- Outliers require very few splits.
    

---

## Working Principle

1. Build multiple random trees.
    
2. Randomly select features and split values.
    
3. Measure the average path length.
    
4. Shorter path length indicates an anomaly.
    

---

## Advantages

- Fast
    
- Scalable
    
- Works well with high-dimensional data
    
- Handles large datasets efficiently
    

---

## Disadvantages

- Performance depends on parameter tuning
    
- Less effective when anomalies are not isolated
    

---

# One-Class SVM

[[One-Class SVM]] is an unsupervised version of the [[Support Vector Machines]] algorithm used for anomaly detection.

Instead of separating two classes, it learns the boundary around normal data.

Any observation lying outside this boundary is considered an outlier.

---

## Working Principle

1. Train using only normal observations.
    
2. Learn the boundary enclosing normal data.
    
3. Classify new observations.
    
4. Points outside the boundary are anomalies.
    

---

## Applications

- Fraud detection
    
- Fault detection
    
- Intrusion detection
    
- Manufacturing quality control
    

---

## Advantages

- Effective for anomaly detection
    
- Handles nonlinear boundaries using kernels
    
- Works well with high-dimensional datasets
    

---

## Disadvantages

- Sensitive to parameter selection
    
- Computationally expensive for very large datasets
    

---

# Isolation Forest vs One-Class SVM

|Feature|Isolation Forest|One-Class SVM|
|---|---|---|
|Method|Random Tree Isolation|Boundary Learning|
|Speed|Faster|Slower|
|Large Datasets|Excellent|Moderate|
|High Dimensions|Good|Good|
|Computational Cost|Low|High|

---

# Advantages of Unsupervised Learning

- Does not require labeled data
    
- Discovers hidden patterns
    
- Useful for exploratory data analysis
    
- Identifies unknown relationships
    
- Can detect anomalies automatically
    

---

# Limitations of Unsupervised Learning

- Difficult to evaluate results
    
- Clusters may not have clear meanings
    
- Sensitive to parameter selection
    
- Higher computational complexity for some algorithms
    

---

# Real-World Applications

## Healthcare

- Patient grouping
    
- Disease subtype discovery
    
- Medical image segmentation
    

---

## Finance

- Fraud detection
    
- Customer segmentation
    
- Risk analysis
    

---

## Retail

- Product recommendation
    
- Market basket analysis
    
- Customer behavior analysis
    

---

## Cybersecurity

- Intrusion detection
    
- Malware detection
    
- Network anomaly detection
    

---

## Search Engines

- Document clustering
    
- Topic modeling
    
- Search result organization
    

---

# Summary

[[College/Semester 5/Machine Learning/Theory/Unsupervised Learning]] is a branch of [[Machine Learning]] that discovers hidden patterns from **unlabeled data**. Major techniques include [[Clustering]], [[Dimensionality Reduction]], [[Association Rule Mining]], and [[Outlier Detection]].

Popular clustering algorithms include [[K-Means Clustering]] and [[Hierarchical Clustering]], while [[Principal Component Analysis (PCA)]] is the most widely used dimensionality reduction technique. [[Association Rule Mining]] uses algorithms such as the [[Apriori Algorithm]] and [[FP-Growth Algorithm]] to discover relationships among items, whereas anomaly detection techniques like [[Isolation Forest]] and [[One-Class SVM]] identify unusual observations that differ significantly from normal data.

These techniques have widespread applications in customer segmentation, document organization, recommendation systems, fraud detection, cybersecurity, healthcare, and business analytics.

---

# Key Terms

- [[Machine Learning]]
    
- [[College/Semester 5/Machine Learning/Theory/Unsupervised Learning]]
    
- [[Clustering]]
    
- [[K-Means Clustering]]
    
- [[Hierarchical Clustering]]
    
- [[Dendrogram]]
    
- [[Dimensionality Reduction]]
    
- [[Principal Component Analysis (PCA)]]
    
- [[Market Segmentation]]
    
- [[Document Clustering]]
    
- [[Association Rule Mining]]
    
- [[Support]]
    
- [[Confidence]]
    
- [[Lift]]
    
- [[Apriori Algorithm]]
    
- [[FP-Growth Algorithm]]
    
- [[Outlier Detection]]
    
- [[Isolation Forest]]
    
- [[One-Class SVM]]