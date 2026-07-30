# [[First Order Ordinary Differential Equations]]

**Tags:** [[Mathematics]] [[Differential Equations]] [[Ordinary Differential Equations]] [[Calculus]] [[Engineering Mathematics]] [[First Order ODE]]

---

# [[Definition]]

A **[[First Order Ordinary Differential Equation]] (ODE)** is a [[Differential Equation]] that contains only the **first derivative** of the unknown function and no higher-order derivatives.

General Form

$$
F\left(x,y,\frac{dy}{dx}\right)=0
$$

or

$$
\frac{dy}{dx}=f(x,y)
$$

where

- $x$ → [[Independent Variable]]
- $y$ → [[Dependent Variable]]
- $\frac{dy}{dx}$ → [[First Derivative]] of $y$ with respect to $x$

---

# [[Terminology]]

## [[Ordinary Differential Equation]]

An [[Ordinary Differential Equation]] contains derivatives with respect to only **one independent variable**.

Example

$$
\frac{dy}{dx}=3x^2
$$

---

## [[Partial Differential Equation]]

A [[Partial Differential Equation]] contains partial derivatives with respect to two or more independent variables.

Example

$$
\frac{\partial u}{\partial t}
=
c^2
\frac{\partial^2u}{\partial x^2}
$$

---

## [[Order]]

The **[[Order]]** of a differential equation is the highest derivative appearing in the equation.

Examples

### [[First Order]]

$$
\frac{dy}{dx}=x+y
$$

Order = 1

---

### [[Second Order]]

$$
\frac{d^2y}{dx^2}+y=0
$$

Order = 2

---

### [[Third Order]]

$$
\frac{d^3y}{dx^3}=x
$$

Order = 3

---

## [[Degree]]

The **[[Degree]]** of a differential equation is the exponent of the highest-order derivative after removing radicals and fractions involving derivatives.

Example

$$
\left(\frac{dy}{dx}\right)^2+x=0
$$

Order = 1

Degree = 2

---

# [[General Solution]]

A **[[General Solution]]** is a solution containing one arbitrary constant.

Example

$$
\frac{dy}{dx}=2x
$$

Integrating,

$$
y=x^2+C
$$

where

- $C$ is an arbitrary constant called the [[Constant of Integration]].

---

# [[Particular Solution]]

A **[[Particular Solution]]** is obtained after applying an [[Initial Condition]] or a [[Boundary Condition]].

General Solution

$$
y=x^2+C
$$

Given

$$
y(1)=5
$$

Then

$$
5=1+C
$$

Therefore

$$
C=4
$$

Hence

$$
y=x^2+4
$$

---

# [[Initial Value Problem]]

A **[[Initial Value Problem]] (IVP)** consists of a [[Differential Equation]] together with one or more [[Initial Conditions]].

Example

$$
\frac{dy}{dx}=x+y
$$

with

$$
y(0)=2
$$

---

# [[Standard Methods of Solving First Order ODEs]]

The most common methods are

- [[Variable Separable Equations]]
- [[Homogeneous Differential Equations]]
- [[Linear Differential Equations]]
- [[Bernoulli Differential Equations]]
- [[Exact Differential Equations]]
- [[Integrating Factor Method]]

---

# [[Variable Separable Equations]]

## [[Definition]]

A [[Variable Separable Equation]] is one in which the variables can be separated onto opposite sides of the equation.

Standard Form

$$
\frac{dy}{dx}=g(x)h(y)
$$

Rearranging,

$$
\frac{dy}{h(y)}=g(x)\,dx
$$

Integrate both sides.

---

## [[Solution Procedure]]

1. Separate the variables.
2. Integrate both sides.
3. Add the [[Constant of Integration]].
4. Simplify the solution.
5. Apply the [[Initial Condition]] if provided.

---

## [[Example]]

Given

$$
\frac{dy}{dx}=xy
$$

Separate variables

$$
\frac{dy}{y}=x\,dx
$$

Integrate

$$
\ln|y|
=
\frac{x^2}{2}+C
$$

Therefore

$$
y
=
Ce^{x^2/2}
$$

---

# [[Homogeneous Differential Equations]]

## [[Definition]]

A [[Homogeneous Differential Equation]] is a first-order equation that can be written as

$$
\frac{dy}{dx}
=
F\left(\frac{y}{x}\right)
$$

Such equations are solved using substitution.

---

## [[Substitution]]

Let

$$
y=vx
$$

Then

$$
\frac{dy}{dx}
=
v+x\frac{dv}{dx}
$$

Substitute into the original equation and solve by [[Variable Separation]].

---

## [[Example]]

Given

$$
\frac{dy}{dx}
=
\frac{x+y}{x}
$$

Substitute

$$
y=vx
$$

Then

$$
\frac{dy}{dx}
=
v+x\frac{dv}{dx}
$$

Substitute into the equation and solve for $v$.

---

# [[Linear Differential Equations]]

## [[Definition]]

A [[Linear Differential Equation]] has the standard form

$$
\frac{dy}{dx}+P(x)y=Q(x)
$$

where

- $P(x)$ and $Q(x)$ are functions of $x$ only.

---

## [[Integrating Factor]]

The **[[Integrating Factor]] (IF)** is

$$
IF
=
e^{\int P(x)\,dx}
$$

Multiply the entire equation by the [[Integrating Factor]].

Then

$$
\frac{d}{dx}(y\cdot IF)
=
Q(x)\cdot IF
$$

Integrate both sides.

---

## [[General Formula]]

$$
y
=
\frac{\int Q(x)\cdot IF\,dx+C}{IF}
$$

---

## [[Example]]

Given

$$
\frac{dy}{dx}+2y=e^{3x}
$$

Integrating Factor

$$
IF=e^{2x}
$$

Multiply

$$
\frac{d}{dx}(ye^{2x})
=
e^{5x}
$$

Integrate

$$
ye^{2x}
=
\frac{e^{5x}}5+C
$$

Therefore

$$
y
=
\frac15e^{3x}
+
Ce^{-2x}
$$
# [[Bernoulli Differential Equations]]

## [[Definition]]

A **[[Bernoulli Differential Equation]]** is a nonlinear first-order differential equation of the form

$$
\frac{dy}{dx}+P(x)y=Q(x)y^n
$$

where

$$
n\neq0,1
$$

Although nonlinear, it can be transformed into a [[Linear Differential Equation]] using an appropriate substitution.

---

## [[Transformation]]

Let

$$
v=y^{1-n}
$$

Differentiate with respect to $x$

$$
\frac{dv}{dx}
=
(1-n)y^{-n}\frac{dy}{dx}
$$

Substitute into the original equation.

The resulting equation becomes a [[Linear Differential Equation]] in $v$.

---

## [[Example]]

Given

$$
\frac{dy}{dx}+y=xy^2
$$

Let

$$
v=\frac1y
$$

Substitute and solve the resulting linear equation.

---

# [[Exact Differential Equations]]

## [[Definition]]

A **[[Exact Differential Equation]]** has the form

$$
M(x,y)\,dx+N(x,y)\,dy=0
$$

where

- $M(x,y)$ is the coefficient of $dx$
- $N(x,y)$ is the coefficient of $dy$

---

## [[Condition for Exactness]]

The equation is exact if

$$
\frac{\partial M}{\partial y}
=
\frac{\partial N}{\partial x}
$$

If this condition is satisfied, a potential function exists.

---

## [[Solution Procedure]]

### Step 1

Identify

$$
M(x,y)
$$

and

$$
N(x,y)
$$

---

### Step 2

Verify

$$
\frac{\partial M}{\partial y}
=
\frac{\partial N}{\partial x}
$$

---

### Step 3

Find a function

$$
\phi(x,y)
$$

such that

$$
\frac{\partial\phi}{\partial x}
=
M
$$

---

### Step 4

Differentiate partially with respect to $y$

$$
\frac{\partial\phi}{\partial y}
=
N
$$

---

### Step 5

Write the final solution

$$
\phi(x,y)=C
$$

---

## [[Example]]

Given

$$
(2xy+y^2)\,dx+(x^2+2xy)\,dy=0
$$

Here

$$
M=2xy+y^2
$$

$$
N=x^2+2xy
$$

Check

$$
\frac{\partial M}{\partial y}
=
2x+2y
$$

$$
\frac{\partial N}{\partial x}
=
2x+2y
$$

Since they are equal, the equation is [[Exact Differential Equation]].

---

# [[Non-Exact Differential Equations]]

## [[Definition]]

If

$$
\frac{\partial M}{\partial y}
\neq
\frac{\partial N}{\partial x}
$$

the equation is called a **[[Non-Exact Differential Equation]]**.

Such equations may become exact after multiplying by an [[Integrating Factor]].

---

# [[Integrating Factor]]

## [[Definition]]

An **[[Integrating Factor]]** is a function that transforms a [[Non-Exact Differential Equation]] or a [[Linear Differential Equation]] into an equation that can be solved directly.

The integrating factor may depend on

- $x$
- $y$
- both $x$ and $y$

---

## [[Linear Integrating Factor]]

For

$$
\frac{dy}{dx}+P(x)y=Q(x)
$$

the integrating factor is

$$
IF
=
e^{\int P(x)\,dx}
$$

---

## [[Purpose]]

The integrating factor converts

$$
\frac{dy}{dx}+P(x)y=Q(x)
$$

into

$$
\frac{d}{dx}(y\cdot IF)
=
Q(x)\cdot IF
$$

which is easily integrated.

---

# [[Common Substitutions]]

| Equation Type | Substitution |
|--------------|--------------|
| [[Homogeneous Differential Equations]] | $y=vx$ |
| [[Bernoulli Differential Equations]] | $v=y^{1-n}$ |
| [[Variable Separable Equations]] | Direct Separation |
| [[Linear Differential Equations]] | [[Integrating Factor]] |
| [[Exact Differential Equations]] | Potential Function |

---

# [[Applications of First Order Ordinary Differential Equations]]

## [[Physics]]

Applications include

- [[Newton's Law of Cooling]]
- [[Radioactive Decay]]
- [[Motion of Particles]]
- [[Electric Circuits]]
- [[Simple Harmonic Motion]] (after reduction)

---

## [[Engineering]]

Applications include

- [[Heat Transfer]]
- [[Fluid Mechanics]]
- [[Chemical Reactions]]
- [[Control Systems]]
- [[Population Models]]

---

## [[Biology]]

Applications include

- [[Population Growth]]
- [[Logistic Growth]]
- [[Epidemic Models]]
- [[Drug Absorption]]

---

## [[Economics]]

Applications include

- [[Compound Interest]]
- [[Economic Growth Models]]
- [[Investment Models]]
- [[Demand Forecasting]]

---

# [[Formula Sheet]]

## [[Variable Separable Equations]]

$$
\frac{dy}{h(y)}
=
g(x)\,dx
$$

---

## [[Linear Differential Equations]]

Standard Form

$$
\frac{dy}{dx}+P(x)y=Q(x)
$$

Integrating Factor

$$
IF=e^{\int P(x)\,dx}
$$

General Solution

$$
y
=
\frac{\int Q(x)\cdot IF\,dx+C}{IF}
$$

---

## [[Homogeneous Differential Equations]]

Substitution

$$
y=vx
$$

---

## [[Bernoulli Differential Equations]]

Substitution

$$
v=y^{1-n}
$$

---

## [[Exact Differential Equations]]

Standard Form

$$
Mdx+Ndy=0
$$

Condition

$$
\frac{\partial M}{\partial y}
=
\frac{\partial N}{\partial x}
$$

Solution

$$
\phi(x,y)=C
$$

---

# [[Problem Solving Strategy]]

1. Determine the [[Order]] and [[Degree]] of the equation.
2. Check whether the variables can be separated.
3. Test if the equation is a [[Homogeneous Differential Equation]].
4. Check whether it is a [[Linear Differential Equation]].
5. Determine if it is a [[Bernoulli Differential Equation]].
6. Verify whether it is an [[Exact Differential Equation]].
7. If necessary, determine an appropriate [[Integrating Factor]].
8. Solve by integration.
9. Apply the given [[Initial Condition]] or [[Boundary Condition]].
10. Verify the solution by differentiation.

---

# [[Common Mistakes]]

- Forgetting the [[Constant of Integration]].
- Incorrectly separating variables.
- Using the wrong [[Integrating Factor]].
- Forgetting the substitution for a [[Bernoulli Differential Equation]].
- Not checking the condition for an [[Exact Differential Equation]].
- Algebraic mistakes after integration.
- Ignoring the [[Initial Condition]].
- Not verifying the final solution.

---

# [[Summary]]

A **[[First Order Ordinary Differential Equation]]** contains only the first derivative of the unknown function. Depending on its form, it can be solved using techniques such as [[Variable Separable Equations]], [[Homogeneous Differential Equations]], [[Linear Differential Equations]], [[Bernoulli Differential Equations]], or [[Exact Differential Equations]]. The most important step in solving any first-order ODE is correctly identifying its type before choosing the appropriate solution method.

---

# [[Related Notes]]

- [[Higher Order Ordinary Differential Equations]]
- [[Differential Equations]]
- [[Ordinary Differential Equations]]
- [[Calculus]]
- [[Differentiation]]
- [[Integration]]
- [[Partial Differential Equations]]
- [[Laplace Transform]]
- [[Linear Algebra]]
- [[Complex Numbers]]
- [[Engineering Mathematics]]
- [[Mathematics Formula Sheet]]