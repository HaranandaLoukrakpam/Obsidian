# Machine Learning (ML)

## Definition

**Machine Learning (ML)** is a subset of [[Artificial Intelligence]] that enables computers to learn from data and improve their performance without being explicitly programmed. Instead of following fixed rules, machine learning algorithms identify patterns in data and use those patterns to make predictions or decisions.

---

## Key Idea

Traditional programming follows predefined rules to produce outputs.

```
Input + Program → Output
```

Machine Learning allows the computer to learn the rules from data.

```
Input + Output Data → Machine Learning Algorithm → Model

New Input → Trained Model → Prediction
```

---

## Characteristics

- Learns from data.
- Improves performance through experience.
- Identifies hidden patterns.
- Makes predictions and decisions.
- Adapts to new data.
- Reduces the need for manual programming.

---

## How Machine Learning Works

1. Collect data.
2. Clean and preprocess the data.
3. Select a machine learning algorithm.
4. Train the model using training data.
5. Evaluate the model.
6. Make predictions on new data.
7. Improve the model with additional data and tuning.

---

## Components of Machine Learning

### [[Dataset]]

A collection of data used to train and test a model.

Examples:

- Customer information
- Images
- Text documents
- Sensor readings

---

### [[Feature]]

An individual measurable property or characteristic of the data.

Examples:

- Age
- Height
- Income
- Temperature

---

### [[Label]]

The correct output or target value that the model learns to predict.

Example:

| Features | Label |
|----------|-------|
| Email content | Spam / Not Spam |
| House size | House price |
| Patient symptoms | Disease |

---

### [[Model]]

A trained machine learning system that makes predictions based on learned patterns.

---

### [[Algorithm]]

A mathematical method used to train a model.

Examples:

- Linear Regression
- Decision Tree
- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Neural Network

---

## Types of Machine Learning

### [[Supervised Learning]]

The model learns using **labeled data**, where the correct output is known.

Applications:

- Email spam detection
- House price prediction
- Disease diagnosis
- Credit risk assessment

Common Algorithms:

- Linear Regression
- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- KNN

---

### [[Unsupervised Learning]]

The model learns from **unlabeled data** by identifying hidden structures or patterns.

Applications:

- Customer segmentation
- Market basket analysis
- Anomaly detection
- Data clustering

Common Algorithms:

- K-Means Clustering
- Hierarchical Clustering
- DBSCAN
- Principal Component Analysis (PCA)

---

### [[Semi-Supervised Learning]]

Uses a small amount of labeled data together with a large amount of unlabeled data.

Applications:

- Image classification
- Medical diagnosis
- Speech recognition

---

### [[Reinforcement Learning]]

An intelligent agent learns by interacting with an environment and receiving rewards or penalties.

Applications:

- Robotics
- Game playing
- Autonomous vehicles
- Resource optimization

---

## Training and Testing

### [[Training Dataset]]

Used to teach the model.

---

### [[Testing Dataset]]

Used to evaluate how well the trained model performs on unseen data.

---

### [[Validation Dataset]]

Used during model development to tune parameters and reduce overfitting.

---

## Important Concepts

### [[Training]]

The process of teaching the model using data.

---

### [[Prediction]]

The output produced by a trained model for new input data.

---

### [[Accuracy]]

Measures how often the model makes correct predictions.

---

### [[Overfitting]]

Occurs when a model learns the training data too well, including noise, leading to poor performance on new data.

---

### [[Underfitting]]

Occurs when a model is too simple to learn the underlying patterns in the data.

---

### [[Feature Engineering]]

The process of selecting, creating, or transforming features to improve model performance.

---

## Common Machine Learning Algorithms

### [[Linear Regression]]

Predicts continuous numerical values.

Example:

- Predicting house prices.

---

### [[Logistic Regression]]

Used for binary classification.

Example:

- Spam or not spam.

---

### [[Decision Tree]]

Makes decisions by splitting data into branches based on feature values.

---

### [[Random Forest]]

An ensemble of multiple decision trees that improves prediction accuracy.

---

### [[Support Vector Machine (SVM)]]

Finds the optimal boundary that separates different classes.

---

### [[K-Nearest Neighbors (KNN)]]

Classifies data based on the labels of its nearest neighbors.

---

### [[Naive Bayes]]

A probabilistic algorithm commonly used for text classification and spam filtering.

---

### [[Artificial Neural Network (ANN)]]

A machine learning model inspired by the human brain, widely used in [[Deep Learning]].

---

## Applications

### Healthcare

- Disease prediction
- Medical image analysis
- Drug discovery

### Finance

- Fraud detection
- Credit scoring
- Stock market analysis

### Retail

- Product recommendations
- Demand forecasting

### Transportation

- Traffic prediction
- Route optimization

### Agriculture

- Crop disease detection
- Yield prediction

### Manufacturing

- Predictive maintenance
- Quality inspection

### Cybersecurity

- Intrusion detection
- Malware classification

---

## Advantages

- Learns automatically from data.
- Improves with more experience.
- Automates complex decision-making.
- Handles large datasets efficiently.
- Finds hidden patterns.
- Supports predictive analytics.

---

## Limitations

- Requires high-quality data.
- Large datasets may be needed.
- Can be computationally expensive.
- May inherit biases from training data.
- Difficult to interpret some complex models.
- Risk of overfitting or underfitting.

---

## Machine Learning vs Traditional Programming

| Traditional Programming | Machine Learning |
|--------------------------|------------------|
| Programmer writes explicit rules | Model learns rules from data |
| Fixed logic | Learns and adapts |
| Limited flexibility | Improves with experience |
| Best for well-defined tasks | Best for pattern recognition and prediction |

---

## Machine Learning vs Deep Learning

| Machine Learning | Deep Learning |
|------------------|---------------|
| Subset of AI | Subset of Machine Learning |
| Often requires manual feature engineering | Learns features automatically |
| Works well with smaller datasets | Typically requires large datasets |
| Faster to train | Slower to train |
| Lower computational requirements | Requires GPUs/TPUs |
| Easier to interpret | More difficult to interpret |

---

## Popular Machine Learning Frameworks

- [[Scikit-learn]]
- [[TensorFlow]]
- [[PyTorch]]
- [[Keras]]
- [[XGBoost]]
- [[LightGBM]]
- [[CatBoost]]

---

## Real-World Examples

- Netflix movie recommendations
- YouTube video recommendations
- Google Search ranking
- Email spam filtering
- Credit card fraud detection
- Face recognition
- Voice assistants
- Product recommendations in e-commerce
- Weather forecasting
- Predictive text on smartphones

---

## Related Notes

- [[Artificial Intelligence]]
- [[Deep Learning]]
- [[Artificial Neural Network (ANN)]]
- [[Dataset]]
- [[Feature]]
- [[Label]]
- [[Model]]
- [[Algorithm]]
- [[Supervised Learning]]
- [[Unsupervised Learning]]
- [[Semi-Supervised Learning]]
- [[Reinforcement Learning]]
- [[Training Dataset]]
- [[Testing Dataset]]
- [[Validation Dataset]]
- [[Overfitting]]
- [[Underfitting]]
- [[Feature Engineering]]
- [[Linear Regression]]
- [[Decision Tree]]
- [[Random Forest]]
- [[Support Vector Machine (SVM)]]
- [[K-Nearest Neighbors (KNN)]]
- [[TensorFlow]]
- [[PyTorch]]
- [[Scikit-learn]]