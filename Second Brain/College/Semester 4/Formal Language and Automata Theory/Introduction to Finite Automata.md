# Introduction to Finite Automata (FA)

## Definition

**Finite Automata (FA)** is a mathematical model of computation used to recognize and process patterns in strings. It is one of the fundamental concepts in the **Theory of Computation (TOC)** and is widely used in compiler design, text processing, lexical analysis, digital circuit design, and pattern matching.

A Finite Automaton consists of a finite number of **states** and processes an input string one symbol at a time to determine whether the string belongs to a particular [[Regular Language]].

---

## Key Idea

A Finite Automaton reads an input string from left to right, changing its current state according to predefined transition rules.

- If the automaton ends in an **accepting (final) state**, the string is **accepted**.
- Otherwise, the string is **rejected**.

---

## Characteristics

- Has a finite number of states.
- Reads one input symbol at a time.
- Cannot move backward on the input.
- Has no external memory (except its current state).
- Accepts or rejects an input string.
- Recognizes [[Regular Language|Regular Languages]].

---

## Components of a Finite Automaton

A Finite Automaton is formally represented as a **5-tuple**:

\[
M = (Q, \Sigma, \delta, q_0, F)
\]

Where:

| Symbol | Meaning |
|--------|---------|
| **Q** | Finite set of states |
| **Σ (Sigma)** | Input alphabet (set of valid symbols) |
| **δ (Delta)** | Transition function |
| **q₀** | Initial (start) state |
| **F** | Set of accepting (final) states |

---

## Working of a Finite Automaton

1. Start at the **initial state**.
2. Read the first input symbol.
3. Move to the next state according to the transition function.
4. Repeat until all input symbols are processed.
5. If the final state belongs to **F**, accept the string; otherwise, reject it.

---

## Example

Suppose an automaton accepts strings ending with **1** over the alphabet `{0,1}`.

States:

- q₀ → Start state
- q₁ → Final state

Transitions:

```
q₀ --0--> q₀
q₀ --1--> q₁
q₁ --0--> q₀
q₁ --1--> q₁
```

Examples:

| Input | Result |
|-------|--------|
| 1 | Accepted |
| 01 | Accepted |
| 111 | Accepted |
| 100 | Rejected |
| 1100 | Rejected |

---

## Types of Finite Automata

### [[Deterministic Finite Automaton (DFA)]]

A DFA has exactly **one transition** for each input symbol from every state.

Characteristics:

- No ambiguity.
- Exactly one next state.
- No ε-transitions.
- Easier to implement.

---

### [[Non-Deterministic Finite Automaton (NFA)]]

An NFA may have:

- Multiple transitions for the same input.
- No transition for an input.
- ε-transitions (in ε-NFA).

Characteristics:

- Multiple possible paths.
- Easier to design.
- Equivalent in power to DFA.

---

### [[ε-NFA (Epsilon NFA)]]

A special type of NFA that allows transitions without consuming any input symbol.

These transitions are called **ε-transitions**.

---

## Representation of Finite Automata

Finite Automata can be represented using:

### State Diagram

A graphical representation where:

- Circles represent states.
- Arrows represent transitions.
- Double circles represent final states.
- Incoming arrow indicates the start state.

---

### Transition Table

Example:

| Current State | Input 0 | Input 1 |
|--------------|---------|---------|
| q₀ | q₀ | q₁ |
| q₁ | q₀ | q₁ |

---

## Applications of Finite Automata

### Compiler Design

- Lexical analysis
- Token recognition

---

### Pattern Matching

- Text searching
- Regular expression engines

---

### Digital Electronics

- Sequential circuit design
- Control systems

---

### Networking

- Protocol verification
- Packet filtering

---

### Software Engineering

- Input validation
- Syntax checking

---

### Artificial Intelligence

- State-based decision systems
- Game state modeling

---

## Advantages

- Simple mathematical model.
- Efficient pattern recognition.
- Easy implementation.
- Foundation of compiler construction.
- Useful in hardware design.
- Fast execution.

---

## Limitations

- Limited memory.
- Cannot recognize context-free languages.
- Cannot count unlimited occurrences.
- Cannot solve problems requiring a stack or additional memory.

---

## Finite Automata vs Pushdown Automata

| Finite Automata | Pushdown Automata |
|-----------------|-------------------|
| No auxiliary memory | Uses a stack |
| Recognizes regular languages | Recognizes context-free languages |
| Simpler model | More powerful |
| Cannot handle nested structures | Can handle nested structures like parentheses |

---

## Finite Automata vs Turing Machine

| Finite Automata | Turing Machine |
|-----------------|----------------|
| No external memory | Infinite tape memory |
| Recognizes regular languages | Recognizes recursively enumerable languages |
| Limited computational power | Most powerful computation model |
| Simple state transitions | Read, write, and move tape head |

---

## Real-World Examples

- ATM input validation
- Password validation
- Traffic light controllers
- Vending machines
- Elevator control systems
- Email validation
- Lexical analyzers in compilers
- Search pattern matching
- Network protocol state machines

---

## Key Terms

| Term | Description |
|------|-------------|
| [[State]] | A condition or position of the automaton during computation |
| [[Alphabet]] | Set of valid input symbols |
| [[Transition Function]] | Rule defining state changes |
| [[Initial State]] | Starting state of the automaton |
| [[Final State]] | Accepting state |
| [[String]] | Sequence of input symbols |
| [[Language]] | Set of accepted strings |
| [[Regular Language]] | Language recognized by a finite automaton |

---

## Related Notes

- [[Theory of Computation]]
- [[Regular Language]]
- [[Regular Expression]]
- [[Deterministic Finite Automaton (DFA)]]
- [[Non-Deterministic Finite Automaton (NFA)]]
- [[ε-NFA (Epsilon NFA)]]
- [[State]]
- [[Alphabet]]
- [[Transition Function]]
- [[Initial State]]
- [[Final State]]
- [[String]]
- [[Language]]
- [[Compiler Design]]
- [[Lexical Analysis]]
- [[Pattern Matching]]
- [[Pushdown Automata]]
- [[Turing Machine]]