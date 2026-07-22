# Deep Learning

## Definition

**Deep Learning** is a subset of [[Machine Learning]] that uses **artificial neural networks** with multiple hidden layers to automatically learn patterns and representations from data. Unlike traditional machine learning, deep learning can learn complex features directly from raw data without requiring extensive manual feature engineering.

---

## Key Idea

Deep learning models imitate the way neurons in the human brain process information. By passing data through many interconnected layers, the model gradually learns increasingly abstract representations.

Example:
- Image → Edges → Shapes → Objects → Classification
- Text → Words → Context → Meaning → Prediction

---

## Characteristics

- Learns features automatically from data.
- Requires large datasets for best performance.
- Benefits from powerful hardware such as [[GPU]]s or [[TPU]]s.
- Achieves state-of-the-art performance in many AI tasks.
- Improves as more data becomes available.

---

## Neural Network Structure

A typical deep neural network consists of:

1. **Input Layer**
   - Receives raw data.

2. **Hidden Layers**
   - Perform feature extraction and learning.
   - Multiple hidden layers make the network "deep."

3. **Output Layer**
   - Produces the final prediction.

```
Input → Hidden Layer 1 → Hidden Layer 2 → Hidden Layer 3 → Output
```

---

## Common Deep Learning Models

### [[Artificial Neural Network (ANN)]]
- Basic neural network architecture.
- Used for structured/tabular data.

### [[Convolutional Neural Network (CNN)]]
- Specialized for image processing.
- Detects spatial features like edges and textures.

Applications:
- Image classification
- Face recognition
- Medical imaging

### [[Recurrent Neural Network (RNN)]]
- Designed for sequential data.
- Maintains memory of previous inputs.

Applications:
- Language modeling
- Speech recognition
- Time-series prediction

### [[Long Short-Term Memory (LSTM)]]
- An improved form of RNN.
- Solves the vanishing gradient problem.
- Better for long sequences.

### [[Transformer]]
- Uses attention mechanisms instead of recurrence.
- Processes sequences in parallel.
- Foundation of modern language models.

Applications:
- Machine translation
- Text generation
- Chatbots

---

## Training Process

1. Collect training data.
2. Initialize network weights.
3. Perform **forward propagation**.
4. Compute the **loss function**.
5. Perform **backpropagation**.
6. Update weights using an [[Optimization Algorithm]].
7. Repeat for many epochs.

---

## Important Concepts

### [[Epoch]]
One complete pass through the entire training dataset.

### [[Batch]]
A subset of the training data processed at one time.

### [[Learning Rate]]
Controls how much model weights change during training.

### [[Loss Function]]
Measures prediction error.

Examples:
- Mean Squared Error (MSE)
- Cross Entropy Loss

### [[Backpropagation]]
Algorithm that computes gradients and updates weights to reduce error.

### [[Gradient Descent]]
Optimization algorithm used to minimize the loss function.

---

## Activation Functions

Activation functions introduce non-linearity.

Common activation functions:

- [[ReLU]]
- [[Sigmoid]]
- [[Tanh]]
- [[Softmax]]

---

## Advantages

- High accuracy on complex problems.
- Automatic feature extraction.
- Handles images, audio, video, and text.
- Scales well with more data.
- Powers modern AI applications.

---

## Disadvantages

- Requires large amounts of data.
- Computationally expensive.
- Long training times.
- Difficult to interpret ("black box").
- Can overfit if not properly regularized.

---

## Applications

- [[Computer Vision]]
- [[Natural Language Processing]]
- [[Speech Recognition]]
- [[Autonomous Vehicles]]
- [[Medical Diagnosis]]
- [[Recommendation Systems]]
- [[Fraud Detection]]
- [[Robotics]]
- [[Generative AI]]

---

## Deep Learning vs Machine Learning

| Machine Learning | Deep Learning |
|------------------|---------------|
| Requires manual feature engineering | Learns features automatically |
| Works well with smaller datasets | Usually requires large datasets |
| Faster training | Slower training |
| Lower computational requirements | Requires GPUs/TPUs |
| Easier to interpret | More difficult to interpret |
| Suitable for structured data | Excellent for images, text, audio, and video |

---

## Popular Frameworks

- [[TensorFlow]]
- [[PyTorch]]
- [[Keras]]
- [[JAX]]
- [[MXNet]]

---

## Real-World Examples

- Face Unlock on smartphones
- ChatGPT and other large language models
- Google Translate
- Self-driving cars
- Netflix recommendations
- Spam email detection
- Medical image analysis
- Voice assistants (Siri, Alexa, Google Assistant)

---

## Related Notes

- [[Artificial Intelligence]]
- [[Machine Learning]]
- [[Artificial Neural Network (ANN)]]
- [[Convolutional Neural Network (CNN)]]
- [[Recurrent Neural Network (RNN)]]
- [[Long Short-Term Memory (LSTM)]]
- [[Transformer]]
- [[Backpropagation]]
- [[Gradient Descent]]
- [[Optimization Algorithm]]
- [[Loss Function]]
- [[Epoch]]
- [[Batch]]
- [[Learning Rate]]
- [[ReLU]]
- [[Sigmoid]]
- [[Softmax]]
- [[Computer Vision]]
- [[Natural Language Processing]]
- [[Generative AI]]