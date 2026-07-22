# First-Order Ordinary Differential Equations (ODEs)

## Definition

A **First-Order Ordinary Differential Equation (ODE)** is a differential equation that contains the **first derivative** of an unknown function with respect to a single independent variable and does not contain higher-order derivatives.

It describes how a quantity changes with respect to another quantity and is widely used in [[Mathematics]], [[Physics]], [[Engineering]], [[Biology]], and [[Economics]].

---

## Ordinary Differential Equation (ODE)

An **Ordinary Differential Equation (ODE)** is an equation involving a function of one independent variable and its derivatives.

General form:

\[
F(x, y, y', y'', \ldots, y^{(n)}) = 0
\]

where:

- **x** = Independent variable
- **y** = Dependent variable
- **y'** = First derivative
- **y''** = Second derivative

---

## First-Order Differential Equation

A first-order ODE contains only the **first derivative**.

General form:

:contentReference[oaicite:0]{index=0}

More commonly written as:

\[
\frac{dy}{dx}=f(x,y)
\]

---

## Characteristics

- Contains only the first derivative.
- One independent variable.
- One dependent variable.
- Describes the rate of change of a quantity.
- Simpler than higher-order differential equations.

---

## Degree and Order

### Order

The **order** of a differential equation is the highest order derivative present.

Example:

\[
\frac{dy}{dx}=x+y
\]

Order = **1**

---

### Degree

The **degree** is the power of the highest-order derivative after removing radicals and fractions involving derivatives.

Example:

\[
\left(\frac{dy}{dx}\right)^2+y=0
\]

Order = **1**

Degree = **2**

---

# Standard Form

A first-order ODE is usually written as:

\[
\frac{dy}{dx}=f(x,y)
\]

---

# Types of First-Order Differential Equations

## 1. Variable Separable Equation

General form:

\[
\frac{dy}{dx}=g(x)h(y)
\]

Can be rewritten as:

\[
\frac{dy}{h(y)}=g(x)\,dx
\]

### Solution Steps

1. Separate variables.
2. Integrate both sides.
3. Add constant of integration.
4. Simplify the solution.

Example:

\[
\frac{dy}{dx}=xy
\]

Separate:

\[
\frac{dy}{y}=x\,dx
\]

Integrate:

\[
\ln|y|=\frac{x^2}{2}+C
\]

Solution:

\[
y=Ce^{x^2/2}
\]

---

## 2. Linear Differential Equation

General form:

\[
\frac{dy}{dx}+P(x)y=Q(x)
\]

Solution uses an **Integrating Factor (IF)**.

Integrating Factor:

\[
IF=e^{\int P(x)\,dx}
\]

General solution:

\[
y(IF)=\int Q(x)(IF)\,dx+C
\]

---

## 3. Exact Differential Equation

General form:

\[
M(x,y)\,dx+N(x,y)\,dy=0
\]

Condition for exactness:

\[
\frac{\partial M}{\partial y}
=
\frac{\partial N}{\partial x}
\]

---

## 4. Homogeneous Differential Equation

General form:

\[
\frac{dy}{dx}=f\left(\frac{y}{x}\right)
\]

Substitution:

\[
y=vx
\]

Then:

\[
\frac{dy}{dx}=v+x\frac{dv}{dx}
\]

---

## 5. Bernoulli's Differential Equation

General form:

\[
\frac{dy}{dx}+P(x)y=Q(x)y^n
\]

Substitution:

\[
z=y^{1-n}
\]

Transforms into a linear differential equation.

---

## Initial Value Problem (IVP)

A first-order differential equation together with an initial condition.

Example:

\[
\frac{dy}{dx}=2x
\]

Initial condition:

\[
y(0)=3
\]

The initial condition determines the constant of integration.

---

## General Solution

Contains an arbitrary constant.

Example:

\[
y=x^2+C
\]

---

## Particular Solution

Obtained after applying initial or boundary conditions.

Example:

General solution:

\[
y=x^2+C
\]

Given:

\[
y(0)=5
\]

Then:

\[
C=5
\]

Particular solution:

\[
y=x^2+5
\]

---

## Applications

First-order ODEs are used in:

### Physics

- Motion of particles
- Radioactive decay
- Cooling laws

---

### Engineering

- Electrical circuits
- Control systems
- Mechanical vibrations

---

### Biology

- Population growth
- Spread of diseases

---

### Economics

- Growth models
- Investment analysis

---

### Chemistry

- Chemical reaction rates

---

## Advantages

- Models many real-world systems.
- Relatively easy to solve.
- Useful in engineering and science.
- Foundation for higher-order differential equations.

---

## Limitations

- Cannot model systems requiring higher-order derivatives.
- Some equations have no closed-form solution.
- May require numerical methods for complex problems.

---

## Common Solution Methods

| Method | Applicable To |
|---------|---------------|
| Separation of Variables | Separable equations |
| Integrating Factor | Linear equations |
| Exact Equation Method | Exact equations |
| Homogeneous Substitution | Homogeneous equations |
| Bernoulli Substitution | Bernoulli equations |

---

## Real-World Examples

- Cooling of hot objects ([[Newton's Law of Cooling]])
- Population growth
- Radioactive decay
- Charging and discharging of capacitors
- Mixing problems
- Drug concentration in the bloodstream
- Bacterial growth

---

## Important Concepts

### [[Differential Equation]]

An equation involving derivatives of a function.

---

### [[Ordinary Differential Equation (ODE)]]

A differential equation involving derivatives with respect to one independent variable.

---

### [[Initial Value Problem (IVP)]]

A differential equation with specified initial conditions.

---

### [[Integrating Factor]]

A function used to solve first-order linear differential equations.

---

### [[Exact Differential Equation]]

A differential equation satisfying the exactness condition.

---

## Key Terms

| Term                                     | Description                                                 |
| ---------------------------------------- | ----------------------------------------------------------- |
| [[Differential Equation]]                | Equation involving derivatives                              |
| [[Ordinary Differential Equation (ODE)]] | Differential equation with one independent variable         |
| [[First-Order Differential Equation]]    | ODE with only the first derivative                          |
| [[Dependent Variable]]                   | Variable whose value depends on another variable            |
| [[Independent Variable]]                 | Variable with respect to which differentiation is performed |
| [[General Solution]]                     | Solution containing an arbitrary constant                   |
| [[Particular Solution]]                  | Solution satisfying given conditions                        |
| [[Initial Value Problem (IVP)]]          | ODE with initial conditions                                 |
| [[Integrating Factor]]                   | Function used to solve linear ODEs                          |

---

## Related Notes

- [[Differential Equation]]
- [[Ordinary Differential Equation (ODE)]]
- [[First-Order Differential Equation]]
- [[Higher-Order Differential Equation]]
- [[Variable Separable Differential Equation]]
- [[Linear Differential Equation]]
- [[Exact Differential Equation]]
- [[Homogeneous Differential Equation]]
- [[Bernoulli Differential Equation]]
- [[Integrating Factor]]
- [[General Solution]]
- [[Particular Solution]]
- [[Initial Value Problem (IVP)]]
- [[Derivative]]
- [[Integration]]
- [[Newton's Law of Cooling]]
- [[Population Growth]]
- [[Radioactive Decay]]