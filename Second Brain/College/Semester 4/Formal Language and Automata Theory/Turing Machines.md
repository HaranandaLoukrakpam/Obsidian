# Turing Machine (TM)

## Definition

A **Turing Machine (TM)** is a mathematical model of computation proposed by **[[Alan Turing]]** in **1936**. It is one of the most powerful abstract computing models and serves as the theoretical foundation of modern computer science.

Unlike a [[Finite Automata]], a Turing Machine has an **infinite tape** that acts as memory, allowing it to perform complex computations that require reading, writing, and modifying data.

A Turing Machine can recognize **Recursively Enumerable Languages** and can simulate the logic of any computer algorithm.

---

## Key Idea

A Turing Machine works by:

- Reading a symbol from an infinite tape.
- Writing or replacing symbols on the tape.
- Moving the tape head left or right.
- Changing its internal state.
- Continuing until it reaches an accepting or rejecting state.

Unlike a [[Finite Automata]], it is **not limited to remembering only its current state**.

---

## Characteristics

- Infinite tape used as memory.
- Reads and writes symbols.
- Moves left or right on the tape.
- Has a finite set of states.
- Performs sequential computation.
- Can simulate any algorithm that is computable.
- Much more powerful than a [[Finite Automata]].

---

## Components of a Turing Machine

A Turing Machine is formally represented as a **7-tuple**:

\[
M = (Q,\Sigma,\Gamma,\delta,q_0,B,F)
\]

Where:

| Symbol | Meaning |
|--------|---------|
| **Q** | Finite set of states |
| **Σ (Sigma)** | Input alphabet |
| **Γ (Gamma)** | Tape alphabet |
| **δ (Delta)** | Transition function |
| **q₀** | Initial (start) state |
| **B** | Blank symbol |
| **F** | Set of accepting (final) states |

---

## Main Components

### [[Tape]]

An infinite strip divided into cells.

- Stores input and intermediate results.
- Can be read and modified.
- Contains blank symbols beyond the input.

Example:

```
□ □ a b b a □ □ □
```

---

### [[Tape Head]]

The tape head can:

- Read a symbol.
- Write a symbol.
- Move one cell left.
- Move one cell right.

---

### [[State Register]]

Stores the current state of the machine.

Example:

```
q0
q1
q2
```

---

### [[Transition Function]]

Determines the next action based on:

- Current state
- Current tape symbol

General form:

```
δ(q, X) = (p, Y, D)
```

Where:

- **q** = Current state
- **X** = Current tape symbol
- **p** = Next state
- **Y** = Symbol to write
- **D** = Direction (L or R)

---

## Working of a Turing Machine

1. Place the input string on the tape.
2. Position the tape head at the first input symbol.
3. Read the current symbol.
4. Apply the transition function.
5. Write a new symbol if required.
6. Move the tape head left or right.
7. Repeat until an accepting or rejecting state is reached.

---

## Example

Suppose the machine replaces every **0** with **1**.

Input:

```
0010
```

Tape operations:

```
0010
↓

1010
↓

1110
↓

1111
```

Final Output:

```
1111
```

---

## State Diagram

A transition is represented as:

```
Read / Write, Move

0 / 1, R
```

Meaning:

- Read **0**
- Write **1**
- Move Right

---

## Types of Turing Machines

### [[Deterministic Turing Machine (DTM)]]

- Only one possible transition for each state and tape symbol.
- Predictable computation.

---

### [[Non-Deterministic Turing Machine (NTM)]]

- Multiple possible transitions may exist.
- Accepts an input if **any** computation path reaches an accepting state.
- Theoretically equivalent in computational power to a DTM.

---

### [[Multi-Tape Turing Machine]]

Uses multiple tapes and multiple tape heads.

Advantages:

- Faster computation.
- Easier algorithm design.

Equivalent in computational power to a single-tape Turing Machine.

---

### [[Universal Turing Machine (UTM)]]

A Turing Machine capable of simulating any other Turing Machine.

It is the theoretical model of a **general-purpose computer**.

---

## Applications

### Compiler Design

- Parsing
- Program execution models

---

### Algorithm Design

- Studying computational procedures.
- Proving algorithm correctness.

---

### Theory of Computation

- Language recognition.
- Computability analysis.

---

### Artificial Intelligence

- Modeling intelligent computation.
- Problem-solving algorithms.

---

### Complexity Theory

- Time complexity.
- Space complexity.

---

## Advantages

- Extremely powerful computational model.
- Can simulate any modern computer.
- Supports unlimited memory through the tape.
- Foundation of computability theory.
- Useful for proving algorithm correctness.

---

## Limitations

- Abstract theoretical model.
- Slower than practical computers.
- Infinite tape cannot exist physically.
- Not intended for practical programming.

---

## Turing Machine vs Finite Automata

| Turing Machine | Finite Automata |
|---------------|-----------------|
| Infinite tape memory | No external memory |
| Can read and write | Can only read |
| Moves left and right | Moves only forward |
| Recognizes recursively enumerable languages | Recognizes regular languages |
| More computationally powerful | Less powerful |

---

## Turing Machine vs Pushdown Automata

| Turing Machine | Pushdown Automata |
|---------------|-------------------|
| Infinite tape | Stack memory |
| More powerful | Less powerful |
| Recognizes recursively enumerable languages | Recognizes context-free languages |
| Can simulate any algorithm | Cannot simulate every algorithm |

---

## Real-World Examples

- Modern computers
- Compilers
- Operating systems
- Artificial Intelligence algorithms
- Program interpreters
- Language processors
- Automated theorem proving
- Scientific computing

---

## Important Concepts

### [[Computability]]

Determines whether a problem can be solved by a Turing Machine.

---

### [[Decidability]]

Determines whether a Turing Machine always halts with an answer for every input.

---

### [[Halting Problem]]

A famous undecidable problem that asks whether a Turing Machine will eventually stop or run forever on a given input.

---

### [[Universal Turing Machine (UTM)]]

A machine capable of simulating every other Turing Machine.

---

## Key Terms

| Term | Description |
|------|-------------|
| [[Tape]] | Infinite memory used by the machine |
| [[Tape Head]] | Reads, writes, and moves on the tape |
| [[State]] | Current condition of the machine |
| [[Transition Function]] | Rules for computation |
| [[Blank Symbol]] | Empty tape cell symbol |
| [[Alphabet]] | Symbols that may appear on the tape |
| [[Computability]] | Ability of a problem to be solved algorithmically |
| [[Decidability]] | Whether an algorithm always terminates |

---

## Related Notes

- [[Theory of Computation]]
- [[Alan Turing]]
- [[Finite Automata]]
- [[Pushdown Automata]]
- [[Regular Language]]
- [[Context-Free Language]]
- [[Recursively Enumerable Language]]
- [[Tape]]
- [[Tape Head]]
- [[State]]
- [[Transition Function]]
- [[Computability]]
- [[Decidability]]
- [[Halting Problem]]
- [[Universal Turing Machine (UTM)]]
- [[Deterministic Turing Machine (DTM)]]
- [[Non-Deterministic Turing Machine (NTM)]]
- [[Compiler Design]]
- [[Algorithm]]