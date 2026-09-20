# [[UNIT-1]]

## [[1. What is ML]]
- [[Machine Learning]] is the study of algorithms that allows computers to improve their performance automatically through experience (data).
- eg - [[Email spam detection]], [[Face recognition]]

## [[2. AI, ML, DL Comparison]]

| **[[AI]]**                                    | **[[ML]]**               | **[[DL]]**                        |
| :-------------------------------------------- | :----------------------- | :-------------------------------- |
| 1. Broad field of making machines intelligent | 1. Subset of [[AI]]      | 1. Subset of [[ML]]               |
| 2. Uses rules & learning                      | 2. Learns from data      | 2. Uses deep neural networks      |
| 3. Can work without data                      | 3. Requires data         | 3. Requires huge amounts of data. |
| 4. Less Computational power                   | 4. Moderate              | 4. High GPU power required.       |
| 5. Eg - [[Chess Program]]                     | 5. [[Email Spam Filter]] | 5. [[Self driving cars]]          |
## [[3. Types of ML]]

### [[A. Supervised learning]]
- The model learns from labeled data
- Input -> Correct Output

#### **Types**
| (i) [[Classification]] | (ii) [[Regression]] |
| :--- | :--- |
| - Predicts Categories<br>- Eg: [[Spam / not spam]]<br>&nbsp;&nbsp;[[Pass / fail]] | - Predicts continuous values<br>- Eg: [[House Price]]<br>&nbsp;&nbsp;[[Temperature]] |

---

### [[B. Unsupervised learning]]
- The model learns from unlabeled data
- No correct output is given

#### **Types**
| (i) [[Clustering]] | (ii) [[Association]] | (iii) [[Dimensionality Reduction]] |
| :--- | :--- | :--- |
| - Groups similar data<br>- eg - [[Customer segmentation]] | - Finds relationships<br>- eg - People buying bread also buy butter | - Reduces number of features<br>- eg - |

---

### [[C. Reinforcement learning]]
- An agent learns by interacting with the environment
## [[Comparison of ML Types]]

| **[[Supervised]]** | **[[Unsupervised]]** | **[[Reinforcement]]** |
| :--- | :--- | :--- |
| 1. Labeled data | 1. Unlabeled data | 1. Reward based |
| 2. Predict Output | 2. Find Patterns | 2. Learn by trial & error |
| 3. [[Classification]] & [[Regression]] | 3. [[Clustering]] | 3. [[Robotics]] & [[Games]] |

---

## [[4. Applications of ML]]

- **[[Healthcare]]**
  - [[Disease prediction]]
  - [[Medical image analysis]]
  - [[Drug discovery]]

- **[[Finance]]**
  - [[Fraud detection]]
  - [[Risk Analysis]]
  - [[Stock prediction]]

- **[[Recommendation System]]**
  - [[Netflix recommendations]]
  - [[Youtube videos]]
  - [[Amazon Product]]
  - [[Spotify songs]]

- **[[Transportation]]**
  - [[Self driving cars]]
  - [[Traffic prediction]]

---

## [[5. ML Workflow]]

1. **[[Data Collection]]** -> collects data from APIs, databases, websites
2. **[[Data Preprocessing]]** -> Clean the data, remove missing values, Remove duplicates
3. **[[Exploratory Data Analysis (EDA)]]** -> analyze the data to understand
4. **[[Feature Engineering]]** -> Improve the database by creating new features
5. **[[Model Training (Building)]]** -> Choose an ML algorithm & train it (decision Tree)
6. **[[Model Evaluation]]** -> Measure model performance
   - **[[Classification]]**
     - Accuracy, Precision, Recall
   - **[[Regression]]**
     - MAE, MSE, RMSE, R²
7. **[[Model Tuning]]** -> Improve performance by Hyperparameter tuning, Cross validation
8. **[[Deployment]]** -> Use the trained model in real applications.
9. **[[Monitoring]]** -> Monitor & retrain the model when needed

---

## [[6. ML Libraries & Frameworks]]

- [[Machine Learning]] Libraries provide ready-made tools & algorithms to build, train, evaluate, & deploy ML model efficiently.
  They reduce coding effort & improve performance.

### [[1. Scikit-learn (sklearn)]]
- *It is one of the easiest libraries for beginners*
- Scikit learn is a free, open source [[Python]] library used for traditional machine learning tasks.
- It is built on top of [[NumPy]], [[SciPy]] & [[Matplotlib]].

**Key features**
- Simple & easy-to-use API
- Large collection of ML algorithms
- Model evaluation.

---

### [[2. TensorFlow]]
- TensorFlow is a open source deep learning framework developed by [[Google]].
- It is mainly used for building & training deep Neural networks.

**Features**
- Deep learning support
- Model deployment
- Distributed training

---

### [[3. PyTorch]]
- PyTorch is an open-source deep learning framework developed by [[Meta]].
- It is widely used in research because of its simplicity & flexibility.

**Feature**
- Easy debugging
- Supports deep neural networks
- Python friendly syntax

---

### [[Library]]
- [[NumPy]]
- [[Pandas]]
- [[SciPy]]
- [[Matplotlib]]
## [[7. Feature Comparison: Scikit-learn vs TensorFlow vs PyTorch]]

| **Feature** | **[[Scikit-learn]]** | **[[TensorFlow]]** | **[[PyTorch]]** |
| :--- | :--- | :--- | :--- |
| 1. Developed By | Community | [[Google]] | [[Meta]] |
| 2. Difficulty | Easy | Moderate | Moderate |
| 3. GPU Support | No / Limited | Yes | Yes |
| 4. Prog Language / Neural Networks | Python, Basic | C++, Python, Advanced | Python, C++, Advanced |
| 5. Flexibility | Moderate | High | Very High |
| 6. Use | Traditional ML | Deep learning & AI | DL & AI |

---

## [[8. Types of Data]]

1. **[[Raw Data]]** — Original, unprocessed data  
   - *eg* — Sensor data, survey responses
2. **[[Structured data]]** — Organized in rows & columns  
   - *eg* — Excel, SQL database
3. **[[Unstructured Data]]** — No fixed format  
   - *eg* — Images, videos, audio, text
4. **[[Semi-Structured Data]]** — Partially organized using tags or metadata  
   - *eg* — JSON, XML, HTML

---

## [[9. Data in ML]]

1. **[[Features]]** — Input variables that help the ML model learn patterns
2. **[[Label / Target]]** — The target or output value that the model is trained to predict

---

## [[10. Common Algorithms used in supervised learning]]

1. **[[Linear Regression]]** -> Predicting house prices
2. **[[Logistic Regression]]** -> Used for classification problems  
   - *classification*: Spam or not spam
3. **[[Decision Tree]]** -> Makes decisions using loan approval, disease diagnosis
4. **[[Random Forest]]** -> Fraud detection
5. **[[Support Vector Machine (SVM)]]** -> Face recognition  
   - *classification*
6. **[[K-Nearest Neighbors (KNN)]]** -> Recommendation System  
   - *clustering*
7. **[[Artificial Neural Network (ANN)]]** -> Image recognition
## [[11. Algorithms used in Unsupervised learning]]

1. **[[K-means clustering]]** -> Customer segmentation
2. **[[Hierarchical clustering]]** -> Document grouping
3. **[[DBSCAN (Density Based Spatial Clustering Application with Noise)]]** -> GPS data analysis
4. **[[PCA (Principle Component Analysis)]]** -> Data visualization
5. **[[Apriori Algorithm]]** -> Market basket analysis

---

## [[12. Algorithms used in Reinforcement learning]]

1. **[[Q-learning]]** -> Robot navigation, Game playing
2. **[[SARSA (State-Action-Reward-State-Action)]]** -> Robot Control
3. **[[Deep Q Network]]** -> Autonomous systems
4. **[[Actor-Critic Methods]]** -> Self-driving cars
5. **[[Policy Gradient]]** -> Robotics

---

## [[13. Regression vs Classification]]

| **[[Regression]]** | **[[Classification]]** |
| :--- | :--- |
| 1. Predicts continuous values | 1. Predicts categorical values |
| 2. Output is a number | 2. Output is a label or category |
| 3. Common Algo — Linear Regression, Decision Tree | 3. Common Algorithms — Logistic Regression |
| 4. Eg — Predicting house price, Salary, Temperature | 4. Eg — Logistic Regression, Predicting Spam / Not spam, Disease / No Disease |

---

## [[14. Goal]]

- **[[Supervised learning]]** — Learn the Relationship between inputs & Outputs to make predictions on new data
- **[[Unsupervised learning]]** — Find Patterns or group similar data
- **[[Reinforcement learning]]** — Maximize cumulative reward over time
## [[ML WORKFLOW]]

Problem Definition -> Data Collection -> Data Preprocessing -> Feature Engineering -> Model Building -> Model Deployment -> Monitoring & Improvement

---

## [[Data Preprocessing]]

1. [[Handling missing values]]
2. [[Removing duplicate record]]
3. [[Handling outliers]]
4. [[Data Normalization]] or [[Standardization]]
5. [[Encoding categorical variables]]
6. [[Splitting data into train & test set]]

---

## [[Types of Feature Engineering]]

1. [[Feature Selection]]
2. [[Feature Extraction]]
3. [[Feature Transformation]]

---

## [[Confusion Matrix]]

| | **Predicted +ve** | **Predicted -ve** |
| :--- | :--- | :--- |
| **Actual +ve** | True +ve (TP) | FN |
| **Actual -ve** | False +ve (FP) | TN |

---

## [[Evaluation Metrics]]

### 1. [[Accuracy]]
- Measures the overall proportion of correct predictions

$$\text{Accuracy} = \frac{\text{TP} + \text{TN}}{\text{TP} + \text{TN} + \text{FP} + \text{FN}}$$
### 2. [[Precision]]
- Measures correctness of positive predictions
$$\text{Precision} = \frac{\text{TP}}{\text{TP} + \text{FP}}$$

### 3. [[Recall]]
- Measures the model's ability to find actual positive cases
$$\text{Recall} = \frac{\text{TP}}{\text{TP} + \text{FN}}$$

### 4. [[F1 Score]]
- It is the harmonic mean of [[Precision]] & [[Recall]]
$$F1 = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$

### 5. [[Mean Absolute Error]]
- Measures the avg absolute difference betn actual & predicted values
$$\text{MAE} = \frac{1}{n} \sum |y_i - \hat{y}_i|$$
$y_i \rightarrow$ Actual value
$\hat{y}_i \rightarrow$ Predicted value
$n \rightarrow$ no of observations

* [[Lower MAE = Better Model]]

eg - Actual = [10, 20, 30]
     Predicted = [12, 18, 33]
     Errors = [2, 2, 3]

$$\text{MAE} = \frac{2 + 2 + 3}{3} = 2.33$$

---

### 6. [[RMSE]] - Root Mean Squared Error
- Measures the square root of the avg squared errors
$$\text{RMSE} = \sqrt{\frac{1}{n} \sum (y_i - \hat{y}_i)^2}$$

* [[Lower RMSE = Better]]

---

## * [[ML Framework & libraries]]

**Frameworks** $\rightarrow$ 
1. [[Scikit learn]]
2. [[Tensorflow]]

| **[[Scenario]]**                   | **[[Recommended library/Fram]]** |
| :--------------------------------- | :------------------------------- |
| 1. [[Classical ML Problem]]        | [[Scikit learn]]                 |
| 2. [[Classification & Regression]] | [[Scikit learn]]                 |
| 3. [[Customer segmentation]]       | [[Scikit learn]]                 |
| 4. [[DL Problems]]                 | [[PyTorch / Tensorflow]]         |
| 5. [[Computer Vision]]             | [[Tensorflow]]                   |
| 6. [[Natural language Processing]] | [[Tensorflow]]                   |
| 7. [[LLM]] (Large Language Model)  | [[PyTorch]]                      |
| 8. [[Research]]                    | [[PyTorch]]                      |
## [[Benefits of ML intelligence System]]

1. It automates repetitive task
2. It learns continuously from new data
3. It improves prediction accuracy
4. It supports faster decision making
5. It detects hidden patterns
6. It provides personalized experiences
7. It enables real time decision support
8. It increases operational accuracy
---
## [[Challenges]]

1. It requires large amount of quality data
2. Bias in training data can lead to unfair decisions
3. Privacy & security concerns
4. High computational requirement for complex model
5. Lack of transparency in some deep learning models.
---
## [[Dataset & Error Guidelines]]

* A dataset is balanced when different classes have approximately equal no of samples. On the otherhand an unbalanced dataset has a large difference in the no of samples among classes.
* **[[Bias & variance]]** describe 2 difference sources of errors that are there in ML.
---
## [[Underfitting vs Overfitting]]

### [[Underfitting]]
* Model is too simple
* Performs poorly on training data
* Poor performance on new data
* High bias
### [[Overfitting]]
* Model is too complex
* Performs very well on training data
* Poor performance on new data
* High variance
### [[Aspect Comparison Table]]

| **[[Aspect]]**     | **[[Bias]]**                           | **[[Variance]]**                         |
| :----------------- | :------------------------------------- | :--------------------------------------- |
| **Meaning**        | Error due to overly simple assumptions | Error due to being too sensitive to data |
| **Model**          | Usually too simple                     | Usually too complex                      |
| **Training error** | High                                   | Very low                                 |
| **Test error**     | High                                   | High                                     |
| **Main Problem**   | [[Underfitting]]                       | [[Overfitting]]                          || **[[Features]]** | **[[Traditional System]]** | **[[ML-based Intelligence System]]** |
| :--- | :--- | :--- |
| [[Decision Making]] | Rule Based | Data driven |
| [[Learning]] | No | Yes |
| [[Adaptability]] | Low | High |
| [[Prediction]] | Limited | Excellent |
| [[Automation]] | Fixed | Intelligent |
| [[Handles Complex data]] | Limited | Excellent |
| [[Improvement]] | Low | Yes |

---
## [[Linear Regression]]

- Linear regression is a supervised learning algorithm used to model the relationship betn a dependent variable & one or more independent variable in a straight line.
- The dependent variable is known as '[[Target]]' $\rightarrow$ Output.
- Independent variable '[[features]]' $\rightarrow$ Input.

### [[Mathematical Eqn]] $\rightarrow$
- for one variable : $y = mx + b$ $\leftarrow$ [[bias]]
- for multiple variables : $y = w_1x_1 + w_2x_2 + \dots + w_mx_m + b$ $\leftarrow$ [[bias]]

where...
$y$ = predicted output
$x_i$ = input features
$w_i$ = weights (coefficient)
---
### [[Geometrical Interpretation]]
- **In 2D :** [Graph showing a 2-dimensional Cartesian coordinate system with a plotted straight line and data points]
- **In 3D :** [Graph showing a 3-dimensional coordinate system with a plotted plane]

---
### [[When to use]] $\rightarrow$
1. When output is continuous
2. When relationship betn variable are approximately linear.
- eg - [[house prize prediction]], [[Salary prediction]], [[sales forecasting]].

## [[Code]]

```python
import numpy as np
import matplotlib as plt
from sklearn.linear_model import LinearRegression

x = [1, 2, 3, 4, 5, 6, 7, 8]
y = [30, 35, 40, 50, 55, 60, 70, 75] # dataset

m = len(x)
print("Number of data points : ", m)

sum_x = 0
for x in X:
    sum_x = sum_x + x

mean_x = sum_x / m
print("Mean of X : ", mean_x)
```

---

## [[Hyperparameter]]

- A [[Hyperparameter]] is a setting in comp or configuration that we chose before training model.
    
- It controls how the learning algorithm works rather than being learned from training data.
---
## [[Advantages of Linear Regression]]

1. Simple to understand & implement
    
2. Fast & computational efficient
    
3. Easy to interpret
    
4. Works well with linear relationships
    
5. Useful for identifying important variables
    
6. Requires less training data
---

## [[Disadvantages of Linear Regression]]

1. Assumes a linear relationship
    
2. Sensitive to outliers
    
3. Requires several assumptions
    
4. Limited to continuous outputs
    
5. Affected by multicollinearity
## [[Naive Baye's]]

- It is a [[supervised ML algorithm]] based on [[Baye's theorem]] which is used for [[classification]] and [[probabilistic prediction]].
    
- It predicts the class of data using [[probability]] and prior knowledge.
    
- It is a [[probabilistic classification algorithm]] that assumes all input features are independent of each other.
### [[Key Concepts]] $\rightarrow$

- [[Bayes Theorem]]
    
- [[Prior Probability]]
    
- [[Posterior Probability]]

### [[Mathematical Equation]]

**[[Bayes Theorem]]**  
P(A/B)=P(B/A)P(A)P(B)P(A/B) = \frac{P(B/A) P(A)}{P(B)}

**[[Naive Bayes Formula]]**  
P(C∣x)=P(x∣C)P(C)P(x)P(C|x) = \frac{P(x|C) P(C)}{P(x)}

where,  
$P(C|x) \rightarrow$ [[Posterior probability]]  
$P(x|C) \rightarrow$ [[Likelihood]]  
$P(C) \rightarrow$ [[Prior probability]]  
$P(x) \rightarrow$ [[evidence]]  
$C \rightarrow$ class  
$x \rightarrow$ feature vector

---

## [[Types of Naive Baye's]]

1. [[Gaussian NB]]
    
2. [[Multinomial NB]]
    
3. [[Bernoulli's NB]]
### [[Behaviour]] $\rightarrow$

1. Fast probabilistic classification
    
2. It is effective for text data
    
3. NB calculates probabilities for each class
    
4. It assigns the class with highest probability
    
5. Assumes features contribute independently.
---
## [[Agentic AI Workflow]]

[[Goal Definition]] $\rightarrow$ [[Planning Engines]] $\rightarrow$ Task Breakdown, chain creation execution $\rightarrow$ [[Tool Solution]] $\rightarrow$ [[Call APIs Run Automation]] $\rightarrow$ [[Self Monitoring]] $\rightarrow$ [[Result Evaluation]] $\rightarrow$ [[Adjustment]]
---
## [[Mathematics for ML]]

1. **[[Linear Algebra]]** $\rightarrow$ Vectors Space, Linear Maps, Determinant, Metric Space, Matrix
    
2. **[[Calculus & Optimization]]** $\rightarrow$ Extremum, Gradients, Jacobians, Taylor's Theorem, Convexity, Conditions of local Minima
    
3. **[[Probability]]** $\rightarrow$ Conditional Probability, Chain Rule, Baye's Rule, Random Variables $\rightarrow$ Discrete, Continuous, Joint Probability Distribution, Joint Expectation, Variance, Covariance, Estimation of Parameters, Gaussian Distribution.
---
## [[Benefits of ML Intelligent System]]

1. It automates repetitive task
    
2. It learns continuously from new data
## [[Support Vector Machine]]

- [[SVM]] is a supervised ML algorithm used for classification, regression & outlier detection. It finds the optimal boundaries. Optimal boundaries known as [[Hyperplane]] that separate data points into classes.
    
- [[SVM]] tries to find the best decision boundary with the max margin betn the classes.
    
- **[[Hyperplane]]** $\rightarrow$ Decision Boundary
    
- **[[Support Vectors]]** $\rightarrow$ Nearest data points to boundary
    
- **[[Margin]]** $\rightarrow$ Distance betn boundary & vectors
    
- SVM focuses on maximizing the margin for better generalization.
### [[Mathematical Eqn]] $\rightarrow$

1. **[[HYPERPLANE]]** $\rightarrow$ $W^Tx + b = 0$
    
    - $W$ $\rightarrow$ weight vector
        
    - $b$ $\rightarrow$ Bias
        
    - $x$ $\rightarrow$ input features (data)
        
2. **[[Classification Rate]]** $\rightarrow$ $f(x) = \text{sign}(W^Tx + b)$ $\rightarrow$ Predicts class label.
    
3. **[[Margin Formula]]** $\rightarrow$ $\frac{2}{||W||}$
### [[Geometrical Interpretation]]

- SVM creates a separating hyperplane.
    
- The hyperplane also known as [[Kernal trick]].
    
- [[Kernal trick]] allows non linear separation.
    
- Few of the common kernal are:
    
    1. [[linear]] $\rightarrow$ straight boundary
        
    2. [[Polynomial]]
        
    3. [[RBF (Gaussian)]]
        
    4. [[Sigmoid]]

---
## [[TYPES]]

1. **[[Linear SVM]]** $\rightarrow$ Straight Boundary
    
2. **[[Non linear SVM]]** $\rightarrow$ Curved Boundary using kernal.
### [[When to use]]

1. Use SVM when dataset is small to medium range.
    
2. When the high dimensional data exist.
    
3. Clear margin of separation exist.
    
4. It used for text classification problems.
### [[Assumptions]]

1. Data is separable
    
2. Independent observations
    
3. Feature scaling improve performance.
    
4. It works better with clear margin betn classes.
    
5. It uses to complex classification boundaries
### [[Assign]]

1. Adv & disadv of SVM
    
2. Compare logistic Regression & SVM
    
3. Implement SVM from scratch using libraries & framework.
    

_(Note: The page includes graph sketches for [[Linear SVM]] showing a straight boundary with a margin and support vectors on $x_1, x_2$ axes, and [[Non linear SVM]] showing a circular boundary on $x_1, x_2$ axes.)_
---
## [[Logistic Regression]]

- [[LR]] is a supervised ML algorithm used for classification problem. It predicts the probability that an input belongs to a particular class.
    
- It uses sigmoid functions to output values betn 0 & 1
### [[Mathematical eqn]]

**[[Linear Combination]]** : $z = w_1x_1 + w_2x_2 + \dots + w_nx_n + b$  
where, $w_i = \text{weights}$  
$b = \text{bias}$

**[[Sigmoid func]]** : $\sigma(z) = \frac{1}{1 + e^{-z}}$

where, $z$ is the [[linear Combination]]  
$\sigma(z)$ is the probability  
$\sigma$ range (0 - 1)

**[[Final prediction]]** :
$$ \hat{y} = \begin{cases} 1 & \text{if } \sigma(z) \geq 0.5 \\ 0 & \text{if } \sigma(z) < 0.5 \end{cases} $$
### [[Geometrical Interpretation]] -

- In 2D, a straight line separating classes.
    
- In 3D, a plane uses sigmoid curve to map outputs into probability.
## [[Decision Tree]]

- It is a [[supervised ML algorithm]] used for both classification & regression tasks.
    
- It works like a tree structure where decision are made based on conditions.
    
    - **[[Internal nodes]]** — feature tests
        
    - **[[Branches]]** — Outcomes of tests
        
    - **[[leaf nodes]]** — final prediction / outputs
        
- It mimics human decision making.
    

### [[Geometrical Interpretation]] $\rightarrow$

1. Decision tree divides feature space into rectangular regions
    
2. Each split creates a decision boundary
    
3. Final regions corresponds to predicted classes or values
    

```text
    X2 ^
       |  +-------+-------+
       |  |       |       |
       |  |       |       |
       |  +-------+-------+
       |  |       |       |
       |  |       |       |
       |  +-------+-------+
       +---------------------> X1
```

### [[Mathematical Eqn]] $\rightarrow$

**[[Entropy formula]]** :  
Entropy(S)=−∑i=1cPilog⁡2(Pi)Entropy(S) = -\sum_{i=1}^{c} P_i \log_2(P_i)

**[[Information gain]]** :  
IG(S,A)=Entropy(S)−∑∣Sv∣∣S∣Entropy(Sv)IG(S, A) = Entropy(S) - \sum \frac{\vert{}S_v\vert{}}{\vert{}S\vert{}} Entropy(S_v)

- Here, $P_i = \text{Probability of class i}$
    
- $S = \text{Sample}$
    
- **[[Entropy]]** measures impurity
    
- **[[Information gain]]** measures reduction in impurity
    

---

## [[Example: Decision Tree Flow]]

```text
               [ Salary > 50k ? ]
                 /            \
             Yes/              \No
               /                \
       [ Age > 30 ]           Not Buy
         /      \
     Yes/        \No
       /          \
     Buy        Not Buy
```

---

## [[KNN Prediction Example]]

**Q. A new student has the features - Study hrs = 5 & attendance = 80, using KNN with K=3, predict whether the student will pass/fail based on the following training data.**

|Student|Study hrs|Attendance|Class|
|:--|:--|:--|:--|
|A|2|60|F|
|B|3|65|F|
|C|4|70|P|
|D|6|95|P|
|E|4|90|P|

### **Step 1: Calculate the dist from 'P' to each training point**

$P(x,y) = (5, 80)$

- $A(2, 60) \rightarrow \text{dist } PA = \sqrt{409} \approx 20.22$
    
- $B(3, 65) \rightarrow \text{dist } PB \approx 15.13$
    
- $C \rightarrow \approx 10.05$
    
- $D \rightarrow \approx 5.10$
    
- $E \rightarrow \approx 10.20$
    

### **Step 2: Rank the neighbours by dist**

|Rank|Student|Dist|Class|
|:--|:--|:--|:--|
|1|D|5.10|P|
|2|C|10.05|P|
|3|E|10.20|P|
|4|B|15.13|F|
|5|A|20.22|F|

### **Step 3: The 3 nearest neighbor points are**

|D|C|E|
|:--|:--|:--|
|P|P|P|

### **Step 4: Majority voting**

- pass rate = 3
    
- fail rate = 0
    
- **major class = Pass**
    

---

## [[GRADIENT DESCENT]]

- It is an iterative optimization algo used in ML to find parameter values that minimize a loss of cost function.
    
- It moves the parameters in the opposite directn to the gradient bcoz the gradient points towards the directn of latest increase.
    

[Θnew=Θold−α×∇J(Θ)][\Theta_{new} = \Theta_{old} - \alpha \times \nabla J(\Theta)]

- Here, $\Theta = \text{model parameter}$
    
- $\alpha = \text{learning rates}$
    
- $J(\Theta) = \text{cost function}$
    
- $\nabla J(\Theta) = \text{gradient of the cost func}$
    

### [[TYPES]]

|**[[Types]]**|**[[Data Used in one Update]]**|**[[Main Characteristic]]**|
|:--|:--|:--|
|**[[Batch Gradient Descent]]**|Entire training dataset|Stable updates, but can be slow for large dataset|
|**[[Stochastic GD]]**|No training sample|Fast & noisy updates can escape some local region.|
|**[[Mini Batch GD]]**|Small batch of sample|Balances speed & stability widely used in Deep learning|

### [[Cost Function Graphs]]

```text
Cost ^
     |
     |         Local           Local
     |         Maxima          Maxima
     |          /\              /\
     |         /  \            /  \
     |  Local /    \          /    \
     | Minima/      \        /      \
     |   \__/        \      /        \
     |                \    /          \
     |                 \__/            \
     |             Global minima        \
     +-------------------------------------> Weight
```

```text
Cost ^
     |
     | * Initial weight
     |  \
     |   \  <-- Incremental steps (Gradient)
     |    \
     |     *
     |      \
     |       *
     |        \_ * __
     |               * <-- min minimum cost / local minima & global minima
     +-------------------------------------> Weight
```

---

## [[Gradient Descent Iteration Example]]

**Q. Consider the cost function $J(\theta) = (\theta - 4)^2$ starting with $\theta = 0$ & using a learning rate $\alpha = 0.1$ perform 3 G.D iterations**

**Step 1 $\rightarrow$ Find the gradient**

J(θ)=(θ−4)2J(\theta) = (\theta - 4)^2

dJdθ=2(θ−4)\frac{dJ}{d\theta} = 2(\theta - 4)

**2 $\rightarrow$ Use the update rule**

θnew=θold−α(dJdθ)\theta_{new} = \theta_{old} - \alpha(\frac{dJ}{d\theta})

### **Iteration 1 :** $\theta_0 = 0$

- Gradient = $2(0 - 4) = -8$
    
- $\theta_1 = 0 - 0.1(-8) = 0.8$
    
- Cost : $J(0.8) = (0.8 - 4)^2 = 10.24$
    

### **Iteration 2 :** $\theta_1 = 0.8$

- Gradient = $2(0.8 - 4) = -6.4$
    
- $\theta_2 = 0.8 - 0.1(-6.4) = 1.44$
    
- Cost : $?$ _(Calculation omitted in source)_
    

### **Iteration 3 :** $\theta_2 = 1.44$

- Gradient = $2(1.44 - 4) = -5.12$
    
- $\theta_3 = 1.44 - 0.1(-5.12) = 1.952$
    
- Cost : $J(1.952) = (1.952 - 4)^2 = 4.1943$
    

### [[Summary of Iterations]]

|Iteration|$\theta$ value|Gradient|Cost $J(\theta)$|
|:--|:--|:--|:--|
|0 (initial)|0.000|-8.000|16.000|
|1|0.800|-6.400|10.2400|
|2|1.440|-5.120|6.5536|
|3|1.952|-4.096|4.1943|