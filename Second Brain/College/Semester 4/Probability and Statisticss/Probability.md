# Probability

**Tags:** [[Mathematics]] [[Probability]] [[Statistics]] [[Engineering Mathematics]] [[Random Variables]] [[Combinatorics]]

---

# Definition

**Probability** is the branch of mathematics that deals with the study of **random events** and the likelihood of their occurrence.

It measures how likely an event is to happen and assigns a value between **0** and **1**.

- **0** → Impossible event
- **1** → Certain event

---

# Basic Terminology

## [[Random Experiment]]

An experiment whose outcome cannot be predicted with certainty before it is performed.

Examples

- Tossing a coin
- Rolling a die
- Drawing a card from a deck

---

## [[Outcome]]

A single possible result of a random experiment.

Example

Rolling a die

Possible outcomes

$$
\{1,2,3,4,5,6\}
$$

---

## [[Sample Space]]

The set of all possible outcomes of a random experiment.

Denoted by

$$
S
$$

Example

Coin Toss

$$
S=\{H,T\}
$$

Die Roll

$$
S=\{1,2,3,4,5,6\}
$$

---

## [[Event]]

An event is any subset of the sample space.

Example

Getting an even number when rolling a die

$$
E=\{2,4,6\}
$$

---

# Types of Events

## [[Simple Event]]

Contains only one outcome.

Example

$$
\{3\}
$$

---

## [[Compound Event]]

Contains more than one outcome.

Example

$$
\{2,4,6\}
$$

---

## [[Certain Event]]

Occurs in every trial.

$$
P(S)=1
$$

---

## [[Impossible Event]]

Can never occur.

$$
P(\varnothing)=0
$$

---

## [[Complementary Event]]

The complement of event $A$ consists of all outcomes not in $A$.

Formula

$$
A'=S-A
$$

Probability

$$
P(A')=1-P(A)
$$

---

## [[Mutually Exclusive Events]]

Two events that cannot occur simultaneously.

$$
A\cap B=\varnothing
$$

Example

Rolling a die

- Event A = Even number
- Event B = Odd number

---

## [[Independent Events]]

Two events are independent if the occurrence of one does not affect the other.

Formula

$$
P(A\cap B)=P(A)P(B)
$$

Example

- Tossing a coin
- Rolling a die

---

## [[Dependent Events]]

Two events are dependent if one event affects the probability of the other.

Example

Drawing two cards without replacement.

---

# Probability Formula

For equally likely outcomes,

$$
P(A)=\frac{\text{Number of favourable outcomes}}{\text{Total number of outcomes}}
$$

---

# Properties of Probability

## Range

$$
0\le P(A)\le1
$$

---

## Impossible Event

$$
P(\varnothing)=0
$$

---

## Certain Event

$$
P(S)=1
$$

---

## Complement Rule

$$
P(A')=1-P(A)
$$

---

# Addition Rule

For any two events,

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$

If A and B are mutually exclusive,

$$
P(A\cup B)=P(A)+P(B)
$$

---

# Multiplication Rule

For independent events,

$$
P(A\cap B)=P(A)P(B)
$$

For dependent events,

$$
P(A\cap B)=P(A)P(B|A)
$$

---

# Conditional Probability

Conditional probability is the probability of event $A$ occurring given that event $B$ has already occurred.

Formula

$$
P(A|B)=\frac{P(A\cap B)}{P(B)}
$$

where

$$
P(B)\neq0
$$

---

# Bayes' Theorem

Bayes' theorem relates conditional probabilities.

Formula

$$
P(A|B)=\frac{P(B|A)P(A)}{P(B)}
$$

Applications

- Medical diagnosis
- Machine Learning
- Spam detection
- Artificial Intelligence

---

# Law of Total Probability

If

$$
B_1,B_2,\ldots,B_n
$$

are mutually exclusive and exhaustive events,

then

$$
P(A)=\sum_{i=1}^{n}P(A|B_i)P(B_i)
$$

---

# Counting Principles

## Factorial

$$
n!=n(n-1)(n-2)\cdots2\cdot1
$$

Special Case

$$
0!=1
$$

---

## Permutations

The number of arrangements of $r$ objects from $n$ objects.

Formula

$$
{}^nP_r=\frac{n!}{(n-r)!}
$$

Example

Arrange 3 students from 5 students

$$
{}^5P_3=\frac{5!}{2!}=60
$$

---

## Combinations

The number of selections of $r$ objects from $n$ objects.

Formula

$$
{}^nC_r=\frac{n!}{r!(n-r)!}
$$

Example

Choose 3 students from 5

$$
{}^5C_3=10
$$

---

# Random Variable

A variable whose value depends on the outcome of a random experiment.

Types

- Discrete Random Variable
- Continuous Random Variable

---

## [[Discrete Random Variable]]

Takes countable values.

Example

Number of heads in three coin tosses.

---

## [[Continuous Random Variable]]

Can take infinitely many values within an interval.

Example

- Height
- Weight
- Temperature

---

# Probability Distribution

A probability distribution describes how probabilities are assigned to different values of a random variable.

---

## [[Discrete Distribution]]

Example

| X | P(X) |
|---|------|
|0|0.25|
|1|0.50|
|2|0.25|

---

## [[Continuous Distribution]]

Represented by a probability density function (PDF).

---

# Expected Value

The expected value is the weighted average of all possible outcomes.

Formula

$$
E(X)=\sum xP(x)
$$

---

# [[Variance]]

Measures the spread of the random variable.

Formula

$$
Var(X)=E(X^2)-[E(X)]^2
$$

---

# [[Standard Deviation]]

The positive square root of the variance.

$$
\sigma=\sqrt{Var(X)}
$$

---

# Common Probability Distributions

## [[Bernoulli Distribution]]

Models a single trial.

Possible outcomes

- Success
- Failure

---

## [[Binomial Distribution]]

Models repeated independent Bernoulli trials.

Formula

$$
P(X=x)=
\binom{n}{x}
p^x
(1-p)^{n-x}
$$

---

## [[Poisson Distribution]]

Used to model the number of events occurring in a fixed interval.

Formula

$$
P(X=x)=
\frac{e^{-\lambda}\lambda^x}{x!}
$$

---

## [[Normal Distribution]]

A continuous probability distribution with a bell-shaped curve.

Properties

- Symmetric
- Mean = Median = Mode
- Total area = 1

---

# Applications of Probability

## Engineering

- Reliability Analysis
- Signal Processing
- Communication Systems

---

## Computer Science

- Machine Learning
- Artificial Intelligence
- Cryptography
- Randomized Algorithms

---

## Finance

- Risk Analysis
- Stock Market Prediction
- Insurance

---

## Medical Science

- Disease Diagnosis
- Clinical Trials

---

# Formula Sheet

## [[Basic Probability]]

$$
P(A)=\frac{\text{Favourable Outcomes}}{\text{Total Outcomes}}
$$

---

## [[Complement Rule]]

$$
P(A')=1-P(A)
$$

---

## [[Addition Rule]]

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$

---

## [[Multiplication Rule]]

Independent

$$
P(A\cap B)=P(A)P(B)
$$

Dependent

$$
P(A\cap B)=P(A)P(B|A)
$$

---

## [[Conditional Probability]]

$$
P(A|B)=\frac{P(A\cap B)}{P(B)}
$$

---

## [[Bayes' Theorem]]

$$
P(A|B)=\frac{P(B|A)P(A)}{P(B)}
$$

---

## Permutations

$$
{}^nP_r=\frac{n!}{(n-r)!}
$$

---

## Combinations

$$
{}^nC_r=\frac{n!}{r!(n-r)!}
$$

---

## Expected Value

$$
E(X)=\sum xP(x)
$$

---

## [[Variance]]

$$
Var(X)=E(X^2)-[E(X)]^2
$$

---

# Problem Solving Strategy

1. Identify the sample space.
2. Define the event(s).
3. Determine whether events are independent, dependent, or mutually exclusive.
4. Choose the appropriate probability rule.
5. Use permutations or combinations if counting is required.
6. Simplify the result.
7. Verify that the probability lies between 0 and 1.

---

# Common Mistakes

- Confusing permutations with combinations.
- Forgetting the intersection term in the addition rule.
- Assuming events are independent when they are not.
- Ignoring conditional probability.
- Forgetting that probabilities must satisfy

$$
0\le P(A)\le1
$$

---

# Summary

**Probability** is the mathematical study of uncertainty. It provides tools for measuring the likelihood of events and forms the foundation of **statistics**, **machine learning**, **artificial intelligence**, **data science**, **engineering**, **finance**, and **scientific research**. Understanding concepts such as sample spaces, events, conditional probability, Bayes' theorem, counting techniques, and probability distributions is essential for solving real-world problems involving randomness and decision-making.

---

# Related Notes

- [[Statistics]]
- [[Random Variables]]
- [[Combinatorics]]
- [[Permutations]]
- [[Combinations]]
- [[Binomial Distribution]]
- [[Poisson Distribution]]
- [[Normal Distribution]]
- [[Bayes' Theorem]]
- [[Conditional Probability]]
- [[Differential Equations]]
- [[Engineering Mathematics]]
- [[Mathematics Formula Sheet]]