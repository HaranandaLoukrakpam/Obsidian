# [[Higher Order Ordinary Differential Equations]]

**Tags:** [[Mathematics]] [[Differential Equations]] [[Ordinary Differential Equations]] [[Higher Order ODE]] [[Calculus]] [[Engineering Mathematics]]

---

# [[Definition]]

A **[[Higher Order Ordinary Differential Equation]] (ODE)** is an [[Ordinary Differential Equation]] that contains derivatives of the dependent variable of **order two or higher**.

Unlike a [[First Order Ordinary Differential Equation]], higher-order ODEs involve second, third, fourth, or higher derivatives.

General Form

$$
F\left(x,y,\frac{dy}{dx},\frac{d^2y}{dx^2},\cdots,\frac{d^ny}{dx^n}\right)=0
$$

where

- $x$ → [[Independent Variable]]
- $y$ → [[Dependent Variable]]
- $\frac{d^ny}{dx^n}$ → [[Highest Order Derivative]]

---

# [[Terminology]]

## [[Order]]

The **[[Order]]** of a [[Differential Equation]] is the highest derivative appearing in the equation.

### [[Second Order]]

$$
\frac{d^2y}{dx^2}+4y=0
$$

Order = 2

---

### [[Third Order]]

$$
\frac{d^3y}{dx^3}+x\frac{dy}{dx}=0
$$

Order = 3

---

### [[Fourth Order]]

$$
\frac{d^4y}{dx^4}+16y=0
$$

Order = 4

---

## [[Degree]]

The **[[Degree]]** of a differential equation is the exponent of the highest-order derivative after removing radicals and fractions involving derivatives.

Example

$$
\left(\frac{d^2y}{dx^2}\right)^3+y=0
$$

Order = 2

Degree = 3

---

# [[Linear Differential Equations]]

A [[Higher Order Ordinary Differential Equation]] is **linear** if

- The dependent variable and all derivatives occur only to the first power.
- There are no products between derivatives.
- The coefficients depend only on the [[Independent Variable]].

General Form

$$
a_n(x)\frac{d^ny}{dx^n}
+a_{n-1}(x)\frac{d^{n-1}y}{dx^{n-1}}
+\cdots
+a_1(x)\frac{dy}{dx}
+a_0(x)y
=
g(x)
$$

---

# [[Nonlinear Differential Equations]]

A [[Differential Equation]] is **nonlinear** if

- Powers of derivatives occur.
- Products of derivatives occur.
- Functions such as

$$
y^2,\;e^y,\;\sin y
$$

appear.

Example

$$
\frac{d^2y}{dx^2}+y^2=0
$$

---

# [[Classification]]

## [[Homogeneous Differential Equations]]

A higher-order equation is **homogeneous** if

$$
g(x)=0
$$

General Form

$$
a_n(x)y^{(n)}
+\cdots
+a_1(x)y'
+a_0(x)y
=
0
$$

Example

$$
\frac{d^2y}{dx^2}
+
5\frac{dy}{dx}
+
6y
=
0
$$

---

## [[Non-Homogeneous Differential Equations]]

A higher-order equation is **non-homogeneous** if

$$
g(x)\neq0
$$

Example

$$
\frac{d^2y}{dx^2}
+
5\frac{dy}{dx}
+
6y
=
e^x
$$

---

# [[General Solution]]

The **[[General Solution]]** of an $n^{th}$ order differential equation contains **n arbitrary constants**.

Example

$$
\frac{d^2y}{dx^2}=0
$$

Integrating once

$$
\frac{dy}{dx}=C_1
$$

Integrating again

$$
y=C_1x+C_2
$$

Notice that two arbitrary constants appear because the equation is second order.

---

# [[Particular Solution]]

A [[Particular Solution]] is obtained after applying the given [[Initial Condition]] or [[Boundary Condition]].

General Solution

$$
y=C_1x+C_2
$$

Given

$$
y(0)=2
$$

$$
y'(0)=3
$$

Therefore

$$
C_2=2
$$

$$
C_1=3
$$

Hence

$$
y=3x+2
$$

---

# [[Initial Value Problems]]

An **[[Initial Value Problem]] (IVP)** consists of a higher-order differential equation together with initial conditions specified at the same point.

Example

$$
\frac{d^2y}{dx^2}+4y=0
$$

Given

$$
y(0)=1
$$

$$
y'(0)=0
$$

---

# [[Boundary Value Problems]]

A **[[Boundary Value Problem]] (BVP)** specifies the values of the solution at two or more different points.

Example

$$
\frac{d^2y}{dx^2}=0
$$

Given

$$
y(0)=0
$$

$$
y(5)=10
$$

---

# [[Constant Coefficient Linear Differential Equations]]

A **[[Constant Coefficient Linear Differential Equation]]** has constant coefficients.

General Form

$$
a_ny^{(n)}
+a_{n-1}y^{(n-1)}
+\cdots
+a_1y'
+a_0y
=
0
$$

---

# [[Solution Procedure]]

1. Form the [[Auxiliary Equation]].
2. Solve for its roots.
3. Construct the [[Complementary Function]].
4. Find the [[Particular Integral]] if necessary.
5. Apply the given [[Initial Condition]] or [[Boundary Condition]].

---

# [[Auxiliary Equation]]

The [[Auxiliary Equation]] (also called the [[Characteristic Equation]]) is obtained by replacing

$$
\frac{d}{dx}
$$

with

$$
m
$$

Example

$$
\frac{d^2y}{dx^2}
-
5\frac{dy}{dx}
+
6y
=
0
$$

Auxiliary Equation

$$
m^2-5m+6=0
$$

Roots

$$
m=2,\;3
$$

General Solution

$$
y=C_1e^{2x}+C_2e^{3x}
$$

---

# [[Types of Roots]]

## [[Distinct Real Roots]]

If the auxiliary equation has distinct real roots

$$
m_1,m_2,\ldots,m_n
$$

then

$$
y
=
C_1e^{m_1x}
+
C_2e^{m_2x}
+
\cdots
+
C_ne^{m_nx}
$$

---

## [[Repeated Roots]]

If a root

$$
m
$$

is repeated $k$ times,

then

$$
y
=
(C_1+C_2x+\cdots+C_kx^{k-1})e^{mx}
$$

---

## [[Complex Roots]]

If the roots are

$$
m=\alpha\pm\beta i
$$

then

$$
y
=
e^{\alpha x}
(C_1\cos\beta x
+
C_2\sin\beta x)
$$
# [[Complementary Function (CF)]]

## [[Definition]]

The **[[Complementary Function]] (CF)** is the solution of the associated **[[Homogeneous Differential Equation]]**.

It represents the **natural response** of the system without any external forcing function.

General Solution

$$
y=CF+PI
$$

where

- $CF$ → [[Complementary Function]]
- $PI$ → [[Particular Integral]]

---

## [[Finding the Complementary Function]]

Steps

1. Form the [[Auxiliary Equation]].
2. Solve for its roots.
3. Construct the solution according to the type of roots.

Example

$$
y''+4y=0
$$

Auxiliary Equation

$$
m^2+4=0
$$

Roots

$$
m=\pm2i
$$

Complementary Function

$$
y=C_1\cos2x+C_2\sin2x
$$

---

# [[Particular Integral (PI)]]

## [[Definition]]

The **[[Particular Integral]] (PI)** is a specific solution of the **[[Non-Homogeneous Differential Equation]]**.

It represents the response due to the external forcing function.

General Solution

$$
y=CF+PI
$$

---

## [[Purpose]]

The [[Complementary Function]] satisfies the homogeneous equation, while the [[Particular Integral]] accounts for the non-homogeneous term.

---

# [[Method of Undetermined Coefficients]]

## [[Definition]]

The **[[Method of Undetermined Coefficients]]** is used to determine the [[Particular Integral]] when the forcing function is simple.

Applicable forcing functions include

- Polynomial
- Exponential
- Sine
- Cosine
- Linear combinations of these

---

## [[Procedure]]

1. Assume a suitable form of the [[Particular Integral]].
2. Substitute into the differential equation.
3. Determine the unknown constants.
4. Write the complete solution.

---

## [[Example]]

Given

$$
y''-3y'+2y=e^x
$$

Assume

$$
y_p=Ae^x
$$

Substitute into the equation and determine $A$.

---

# [[Method of Variation of Parameters]]

## [[Definition]]

The **[[Method of Variation of Parameters]]** is a general technique for finding the [[Particular Integral]].

Unlike the [[Method of Undetermined Coefficients]], it works for a much wider class of forcing functions.

---

## [[Idea]]

Instead of constants

$$
C_1,\;C_2
$$

assume they become functions

$$
C_1(x),\;C_2(x)
$$

The particular solution becomes

$$
y_p
=
C_1(x)y_1
+
C_2(x)y_2
$$

where

- $y_1$
- $y_2$

are independent solutions of the homogeneous equation.

---

# [[Cauchy-Euler Differential Equation]]

## [[Definition]]

A **[[Cauchy-Euler Differential Equation]]** has variable coefficients that follow a special pattern.

General Form

$$
x^2y''
+
axy'
+
by
=
0
$$

---

## [[Solution Method]]

Assume

$$
y=x^m
$$

Substitute into the equation.

This produces an [[Auxiliary Equation]] in terms of $m$.

Solve for the roots and construct the solution.

---

## [[Example]]

$$
x^2y''
+
3xy'
+
y
=
0
$$

Assume

$$
y=x^m
$$

Substitute and solve for $m$.

---

# [[Reduction of Order]]

## [[Definition]]

The **[[Reduction of Order]]** method is used when

- One solution is already known.
- A second independent solution is required.

---

## [[Substitution]]

Assume

$$
y=v(x)y_1
$$

where

- $v(x)$ is unknown.
- $y_1$ is the known solution.

Substitute into the differential equation and solve for $v(x)$.

---

# [[Applications]]

## [[Physics]]

Higher-order differential equations are used in

- [[Simple Harmonic Motion]]
- [[Mechanical Vibrations]]
- [[Wave Motion]]
- [[Heat Transfer]]
- [[Beam Deflection]]
- [[Electrical Circuits]]

---

## [[Mechanical Engineering]]

Applications include

- [[Spring-Mass Systems]]
- [[Damped Vibrations]]
- [[Structural Analysis]]
- [[Machine Design]]

---

## [[Electrical Engineering]]

Applications include

- [[RLC Circuits]]
- [[Signal Processing]]
- [[Control Systems]]
- [[Electromagnetic Waves]]

---

## [[Civil Engineering]]

Applications include

- [[Beam Theory]]
- [[Structural Mechanics]]
- [[Bridge Analysis]]
- [[Earthquake Engineering]]

---

## [[Aerospace Engineering]]

Applications include

- [[Flight Dynamics]]
- [[Rocket Motion]]
- [[Aircraft Stability]]
- [[Control Systems]]

---

# [[Formula Sheet]]

## [[General Linear Equation]]

$$
a_ny^{(n)}
+
a_{n-1}y^{(n-1)}
+
\cdots
+
a_1y'
+
a_0y
=
g(x)
$$

---

## [[Homogeneous Differential Equation]]

$$
g(x)=0
$$

---

## [[Non-Homogeneous Differential Equation]]

$$
g(x)\neq0
$$

---

## [[General Solution]]

$$
y=CF+PI
$$

---

## [[Auxiliary Equation]]

Replace

$$
\frac{d}{dx}
$$

with

$$
m
$$

---

## [[Distinct Real Roots]]

$$
y=\sum_{i=1}^{n}C_ie^{m_ix}
$$

---

## [[Repeated Roots]]

$$
y
=
(C_1+C_2x+\cdots)e^{mx}
$$

---

## [[Complex Roots]]

$$
y
=
e^{\alpha x}
(C_1\cos\beta x
+
C_2\sin\beta x)
$$

---

## [[Cauchy-Euler Differential Equation]]

$$
x^2y''
+
axy'
+
by
=
0
$$

---

# [[Problem Solving Strategy]]

1. Determine the [[Order]] and [[Degree]].
2. Check whether the equation is [[Linear Differential Equation|Linear]] or [[Nonlinear Differential Equation|Nonlinear]].
3. Identify whether it is [[Homogeneous Differential Equation|Homogeneous]] or [[Non-Homogeneous Differential Equation|Non-Homogeneous]].
4. Form the [[Auxiliary Equation]].
5. Solve for the roots.
6. Construct the [[Complementary Function]].
7. Find the [[Particular Integral]], if required.
8. Apply the [[Initial Condition]] or [[Boundary Condition]].
9. Verify the solution.

---

# [[Common Mistakes]]

- Forming the [[Auxiliary Equation]] incorrectly.
- Ignoring repeated roots.
- Using the wrong solution for complex roots.
- Forgetting the [[Particular Integral]].
- Confusing the [[Complementary Function]] with the [[Particular Integral]].
- Losing arbitrary constants during integration.
- Forgetting to apply [[Initial Value Problems|Initial Conditions]] or [[Boundary Value Problems|Boundary Conditions]].
- Algebraic errors while simplifying.

---

# [[Summary]]

A **[[Higher Order Ordinary Differential Equation]]** is an [[Ordinary Differential Equation]] containing derivatives of order two or higher. These equations model many physical and engineering systems, including [[Mechanical Vibrations]], [[Electrical Circuits]], [[Structural Analysis]], and [[Control Systems]].

Linear higher-order differential equations with constant coefficients are solved using the [[Auxiliary Equation]], [[Complementary Function]], and [[Particular Integral]]. Special forms such as the [[Cauchy-Euler Differential Equation]] require substitution techniques, while more advanced methods such as the [[Method of Variation of Parameters]] and the [[Method of Undetermined Coefficients]] are used to obtain complete solutions.

---

# [[Related Notes]]

- [[First Order Ordinary Differential Equations]]
- [[Differential Equations]]
- [[Ordinary Differential Equations]]
- [[Partial Differential Equations]]
- [[Calculus]]
- [[Differentiation]]
- [[Integration]]
- [[Laplace Transform]]
- [[Linear Algebra]]
- [[Complex Numbers]]
- [[Engineering Mathematics]]
- [[Simple Harmonic Motion]]
- [[Mechanical Vibrations]]
- [[Control Systems]]
- [[Electrical Circuits]]
- [[Mathematics Formula Sheet]]