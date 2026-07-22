# Probability

## Definition

**Probability** is the branch of mathematics that deals with the likelihood or chance of an event occurring. It measures uncertainty and assigns a value between **0 and 1**, where:

- **0** means the event is impossible.
- **1** means the event is certain.

Probability is widely used in **statistics, data science, artificial intelligence, machine learning, finance, engineering, medicine, and everyday decision-making**.

---

## Basic Terminology

### [[Experiment]]

An action or process that produces one or more outcomes.

Examples:

- Tossing a coin
- Rolling a die
- Drawing a card

---

### [[Outcome]]

A possible result of an experiment.

Example:

Rolling a die:

```
4
```

is one outcome.

---

### [[Sample Space]]

The **sample space** is the set of all possible outcomes of an experiment.

Example:

Rolling a die:

```
S = {1,2,3,4,5,6}
```

---

### [[Event]]

An **event** is a subset of the sample space.

Example:

Getting an even number:

```
E = {2,4,6}
```

---

## Probability Formula

The probability of an event is:

\[
P(E)=\frac{\text{Number of favorable outcomes}}{\text{Total number of possible outcomes}}
\]

Example:

Probability of getting an even number on a fair die:

\[
P(E)=\frac{3}{6}=\frac{1}{2}
\]

---

## Characteristics of Probability

- Always lies between **0 and 1**.
- Measures uncertainty.
- Can be expressed as a fraction, decimal, or percentage.
- Larger probability means a greater chance of occurring.

---

# Types of Probability

## 1. Classical Probability

Based on equally likely outcomes.

Example:

Probability of getting a head:

```
1/2
```

---

## 2. Experimental (Empirical) Probability

Calculated using actual observations.

Formula:

\[
P(E)=\frac{\text{Number of times event occurs}}{\text{Total number of trials}}
\]

---

## 3. Subjective Probability

Based on personal judgment or experience.

Example:

Estimating the chance that a sports team will win.

---

## Basic Probability Rules

### Impossible Event

```
P(E)=0
```

---

### Certain Event

```
P(E)=1
```

---

### Complement Rule

For an event **A**:

\[
P(A')=1-P(A)
\]

where **A'** is the complement of **A**.

---

### Addition Rule

For two events:

\[
P(A\cup B)=P(A)+P(B)-P(A\cap B)
\]

---

### Multiplication Rule (Independent Events)

If events **A** and **B** are independent:

\[
P(A\cap B)=P(A)\times P(B)
\]

---

### Conditional Probability

The probability of event **A** occurring given that **B** has already occurred.

\[
P(A|B)=\frac{P(A\cap B)}{P(B)}
\]

---

# Types of Events

## Simple Event

Contains only one outcome.

Example:

Rolling a **3**.

---

## Compound Event

Contains more than one outcome.

Example:

Rolling an even number:

```
{2,4,6}
```

---

## Independent Events

The occurrence of one event does not affect the other.

Example:

- Tossing a coin
- Rolling a die

---

## Dependent Events

The occurrence of one event affects the probability of the other.

Example:

Drawing two cards without replacement.

---

## Mutually Exclusive Events

Two events that cannot occur simultaneously.

Example:

Getting both **2** and **5** in a single die roll.

---

## Equally Likely Events

Events having the same probability.

Example:

Each face of a fair die.

---

## Conditional Probability

Probability when another event has already occurred.

Example:

Probability that a selected card is a King given that it is a face card.

---

# Random Variables

A **[[Random Variable]]** assigns numerical values to the outcomes of a random experiment.

Types:

### [[Discrete Random Variable]]

Takes countable values.

Examples:

- Number of heads
- Number of customers

---

### [[Continuous Random Variable]]

Takes values from a continuous interval.

Examples:

- Height
- Weight
- Temperature

---

# Probability Distributions

## [[Binomial Distribution]]

Used when:

- Fixed number of trials.
- Two possible outcomes.
- Independent trials.
- Constant probability of success.

Example:

Number of heads in 10 coin tosses.

---

## [[Poisson Distribution]]

Models the number of events occurring in a fixed interval.

Example:

Calls received by a call center in one hour.

---

## [[Normal Distribution]]

A continuous probability distribution with a bell-shaped curve.

Characteristics:

- Symmetric.
- Mean = Median = Mode.

Applications:

- Heights
- Test scores
- Measurement errors

---

# Counting Principles

## [[Permutation]]

Arrangement where **order matters**.

Formula:

\[
{}_nP_r=\frac{n!}{(n-r)!}
\]

---

## [[Combination]]

Selection where **order does not matter**.

Formula:

\[
{}_nC_r=\frac{n!}{r!(n-r)!}
\]

---

## Expected Value

The expected value is the long-run average outcome of a random variable.

Formula:

\[
E(X)=\sum xP(x)
\]

---

## Applications of Probability

### Statistics

Data analysis and hypothesis testing.

---

### Artificial Intelligence

- Prediction
- Decision-making
- Bayesian models

---

### Machine Learning

- Classification
- Naive Bayes algorithm
- Model evaluation

---

### Finance

- Risk analysis
- Investment planning
- Insurance

---

### Engineering

- Reliability analysis
- Quality control

---

### Medicine

- Disease prediction
- Clinical trials

---

### Weather Forecasting

Estimating the chance of rain or storms.

---

## Advantages

- Quantifies uncertainty.
- Supports decision-making.
- Widely applicable.
- Foundation of statistics and machine learning.
- Helps model real-world randomness.

---

## Limitations

- Predictions are probabilistic, not certain.
- Accuracy depends on assumptions and data quality.
- Complex events may require advanced mathematical models.

---

## Probability vs Statistics

| Probability | Statistics |
|-------------|------------|
| Predicts future outcomes | Analyzes collected data |
| Starts with known probabilities | Starts with observed data |
| Forward reasoning | Backward reasoning |
| Theoretical | Data-driven |

---

## Real-World Examples

- Tossing a coin
- Rolling a die
- Lottery systems
- Weather forecasting
- Stock market risk analysis
- Medical diagnosis
- Spam email filtering
- Recommendation systems

---

## Key Terms

| Term | Description |
|------|-------------|
| [[Probability]] | Measure of the likelihood of an event |
| [[Experiment]] | Process that produces outcomes |
| [[Outcome]] | Result of an experiment |
| [[Sample Space]] | Set of all possible outcomes |
| [[Event]] | Subset of the sample space |
| [[Random Variable]] | Variable representing random outcomes |
| [[Independent Events]] | Events that do not influence each other |
| [[Dependent Events]] | Events where one affects the other |
| [[Permutation]] | Ordered arrangement |
| [[Combination]] | Unordered selection |
| [[Expected Value]] | Long-run average outcome |

---

## Related Notes

- [[Probability]]
- [[Statistics]]
- [[Experiment]]
- [[Outcome]]
- [[Sample Space]]
- [[Event]]
- [[Independent Events]]
- [[Dependent Events]]
- [[Mutually Exclusive Events]]
- [[Conditional Probability]]
- [[Random Variable]]
- [[Discrete Random Variable]]
- [[Continuous Random Variable]]
- [[Permutation]]
- [[Combination]]
- [[Binomial Distribution]]
- [[Poisson Distribution]]
- [[Normal Distribution]]
- [[Expected Value]]
- [[Artificial Intelligence]]
- [[Machine Learning]]
- [[Data Science]]