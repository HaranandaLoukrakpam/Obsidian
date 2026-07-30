# [[Differential Calculus]]

## [[Limits and Continuity]]

The foundation of calculus is built upon the concept of the **limit**. A limit describes the behavior of a function as its input approaches a specific value, even if the function is not explicitly defined at that exact point.

### [[Limit Laws]]

Let $c$ be a constant, and assume $\lim_{x \to a} f(x)$ and $\lim_{x \to a} g(x)$ exist.

* **Sum Rule:** $\lim_{x \to a} [f(x) \pm g(x)] = \lim_{x \to a} f(x) \pm \lim_{x \to a} g(x)$
* **Product Rule:** $\lim_{x \to a} [f(x) \cdot g(x)] = \lim_{x \to a} f(x) \cdot \lim_{x \to a} g(x)$
* **Quotient Rule:** $\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{\lim_{x \to a} f(x)}{\lim_{x \to a} g(x)}$, provided $\lim_{x \to a} g(x) \neq 0$

### [[One-Sided Limits]]

A one-sided limit looks at the behavior of a function as $x$ approaches $a$ from only one direction:

* **Left-hand limit:** $\lim_{x \to a^-} f(x)$ (approaching from values less than $a$)
* **Right-hand limit:** $\lim_{x \to a^+} f(x)$ (approaching from values greater than $a$)

A general limit $\lim_{x \to a} f(x)$ exists if and only if both one-sided limits exist and are equal.

### [[Limits at Infinity]]

Limits at infinity describe the end behavior of a function (horizontal asymptotes).


$$\lim_{x \to \infty} f(x) = L$$


This implies that as $x$ grows arbitrarily large, $f(x)$ approaches the finite value $L$.

### [[Intermediate Value Theorem]] (IVT)

If $f$ is a continuous function on a closed interval $[a, b]$, and $N$ is any number between $f(a)$ and $f(b)$, then there exists at least one number $c$ in the open interval $(a, b)$ such that $f(c) = N$.
**Physical Significance:** If you drive from $0$ to $60$ mph, you must have been traveling at exactly $45$ mph at some point during the acceleration.

## [[The Derivative]]

The derivative represents the instantaneous **rate of change** of a function with respect to one of its variables. Geometrically, it is the slope of the tangent line to the curve $y = f(x)$ at a specific point.

### Definition of the Derivative

The formal limit definition of a derivative $f'(x)$ is:


$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$


**Variables:**

* $f'(x)$: Derivative of $f$ with respect to $x$
* $h$: An infinitesimally small change in the input $x$

## [[Rules of Differentiation]]

Calculating limits directly is tedious. The following rules simplify the process:

* **Power Rule:**

$$\frac{d}{dx}(x^n) = nx^{n-1}$$


* **Constant Multiple Rule:**

$$\frac{d}{dx}[cf(x)] = c \frac{d}{dx}f(x)$$


* **Product Rule:**

$$\frac{d}{dx}[u(x)v(x)] = u'(x)v(x) + u(x)v'(x)$$


* **Quotient Rule:**

$$\frac{d}{dx}\left[\frac{u(x)}{v(x)}\right] = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}$$



### [[Chain Rule]]

The chain rule is used to differentiate composite functions. If $y = f(g(x))$, then:


$$\frac{dy}{dx} = f'(g(x)) \cdot g'(x)$$


In Leibniz notation, if $y$ depends on $u$ and $u$ depends on $x$:


$$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$

### [[Implicit Differentiation]]

When a relation cannot be explicitly solved for $y$ (e.g., $x^2 + y^2 = 25$), we differentiate both sides with respect to $x$, applying the [[Chain Rule]] whenever differentiating terms involving $y$, and then algebraically solve for $\frac{dy}{dx}$ (or $y'$).

## [[Derivatives of Transcendental Functions]]

### Trigonometric Functions

| Function $f(x)$ | Derivative $f'(x)$ |
| --- | --- |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |
| $\tan(x)$ | $\sec^2(x)$ |
| $\sec(x)$ | $\sec(x)\tan(x)$ |
| $\csc(x)$ | $-\csc(x)\cot(x)$ |
| $\cot(x)$ | $-\csc^2(x)$ |

### Exponential and Logarithmic Functions

| Function $f(x)$ | Derivative $f'(x)$ |
| --- | --- |
| $e^x$ | $e^x$ |
| $a^x$ | $a^x \ln(a)$ |
| $\ln(x)$ | $\frac{1}{x}$ |
| $\log_a(x)$ | $\frac{1}{x \ln(a)}$ |

## [[Applications of Differentiation]]

### [[Mean Value Theorem]] (MVT)

If $f(x)$ is continuous on the closed interval $[a, b]$ and differentiable on the open interval $(a, b)$, then there exists at least one point $c$ in $(a, b)$ such that:


$$f'(c) = \frac{f(b) - f(a)}{b - a}$$


**Physical Significance:** At some point during a journey, your instantaneous velocity equals your average velocity for the entire trip.

### [[Maxima and Minima]]

* **Critical Points:** Points where $f'(x) = 0$ or $f'(x)$ is undefined.
* **First Derivative Test:** If $f'(x)$ changes from positive to negative at $c$, $f(c)$ is a local maximum. If it changes from negative to positive, $f(c)$ is a local minimum.
* **Second Derivative Test:** If $f'(c) = 0$ and $f''(c) > 0$, it's a local minimum (concave up). If $f''(c) < 0$, it's a local maximum (concave down).

### [[Curve Sketching]]

* **Concavity:** If $f''(x) > 0$, the curve is concave upward (U-shaped). If $f''(x) < 0$, it is concave downward (n-shaped).
* **Inflection Points:** Points where the concavity changes (requires $f''(x) = 0$ or undefined, AND a sign change in $f''$).

### [[Optimization Problems]]

Finding the absolute maximum or absolute minimum of a function within a given domain. Commonly applied in engineering to minimize material cost or maximize volume.

### [[L'Hôpital's Rule]]

Used to evaluate indeterminate limit forms like $\frac{0}{0}$ or $\frac{\infty}{\infty}$.


$$\lim_{x \to a} \frac{f(x)}{g(x)} = \lim_{x \to a} \frac{f'(x)}{g'(x)}$$


(Provided the limit on the right exists).

---

## [[Solved Examples]]

### Example 1: Chain Rule and Product Rule

**Problem:** Find the derivative of $f(x) = x^2 \sin(3x)$.
**Solution:**
Apply the Product Rule: $u = x^2$, $v = \sin(3x)$.


$$f'(x) = (x^2)' \sin(3x) + x^2 (\sin(3x))'$$


Apply the Power Rule to $u$ and the Chain Rule to $v$:


$$(x^2)' = 2x$$

$$(\sin(3x))' = \cos(3x) \cdot \frac{d}{dx}(3x) = 3\cos(3x)$$


Combine them:


$$f'(x) = 2x \sin(3x) + x^2(3\cos(3x)) = 2x \sin(3x) + 3x^2 \cos(3x)$$

### Example 2: Optimization

**Problem:** A farmer has $2400$ ft of fencing and wants to fence off a rectangular field that borders a straight river. He needs no fence along the river. What are the dimensions of the field that has the largest area?
**Solution:**

1. Let $x$ be the width and $y$ be the length parallel to the river.
2. Constraint: $2x + y = 2400 \implies y = 2400 - 2x$.
3. Objective Function (Area): $A = x \cdot y = x(2400 - 2x) = 2400x - 2x^2$.
4. Differentiate to find critical points:

$$\frac{dA}{dx} = 2400 - 4x$$


5. Set to zero: $2400 - 4x = 0 \implies x = 600$.
6. Check second derivative: $\frac{d^2A}{dx^2} = -4$ (Since it is negative, this is a maximum).
7. Find $y$: $y = 2400 - 2(600) = 1200$.
**Answer:** Dimensions are $600 \text{ ft}$ by $1200 \text{ ft}$.

### Example 3: L'Hôpital's Rule

**Problem:** Evaluate $\lim_{x \to 0} \frac{\sin(x)}{x}$.
**Solution:**

1. Direct substitution yields $\frac{0}{0}$ (Indeterminate form).
2. Apply [[L'Hôpital's Rule]]: differentiate numerator and denominator.

$$\lim_{x \to 0} \frac{\frac{d}{dx}(\sin(x))}{\frac{d}{dx}(x)} = \lim_{x \to 0} \frac{\cos(x)}{1}$$


3. Substitute $x = 0$:

$$\frac{\cos(0)}{1} = \frac{1}{1} = 1$$



---

# [[Formula Sheet]]

* **Limit Definition of Derivative:** $f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$
* **Power Rule:** $\frac{d}{dx} x^n = nx^{n-1}$
* **Product Rule:** $(uv)' = u'v + uv'$
* **Quotient Rule:** $(u/v)' = \frac{u'v - uv'}{v^2}$
* **Chain Rule:** $[f(g(x))]' = f'(g(x))g'(x)$
* **L'Hôpital's Rule:** $\lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{g'(x)}$

---

# [[Problem Solving Strategy]]

1. **For Limits:** Always try direct substitution first. If you get a real number, you're done. If you get $0/0$ or $\infty/\infty$, use [[L'Hôpital's Rule]] or algebraic manipulation (factoring, rationalizing).
2. **For Derivatives:** Identify the overarching structure first. Is it a product? A quotient? A composite function? Apply the Product/Quotient rules on the outside, and work your way inside using the [[Chain Rule]].
3. **For Optimization:**
* Draw a diagram and assign variables.
* Write down the objective function (what you are trying to maximize/minimize).
* Write down the constraint equation.
* Use the constraint to eliminate all but one variable in the objective function.
* Take the derivative, set to zero, and solve. Verify it's a max/min using the second derivative test.



---

# [[Common Mistakes]]

* **The Product Rule Error:** Assuming $(uv)' = u'v'$. This is false. You must use $(uv)' = u'v + uv'$.
* **Forgetting the Chain Rule:** Differentiating $\sin(2x)$ as $\cos(2x)$ instead of $2\cos(2x)$. Always look for the "inside" function.
* **Quotient Rule Sign Error:** Putting a plus sign instead of a minus sign in the numerator, or reversing the order ($uv' - u'v$ instead of $u'v - uv'$).
* **L'Hôpital Abuse:** Applying L'Hôpital's Rule when the limit is *not* an indeterminate form (e.g., trying to use it on $1/0$, which is just an asymptote).

---

# [[Applications]]

* **Physics (Kinematics):** If $s(t)$ is position, then the first derivative $s'(t) = v(t)$ is velocity, and the second derivative $s''(t) = a(t)$ is acceleration.
* **Economics:** Derivatives represent "marginal" quantities. Marginal cost is the derivative of the cost function, representing the cost to produce exactly one additional unit.
* **Engineering and Machine Learning:** [[Optimization Problems]] are used to minimize material stress, maximize structural integrity, or (in ML) minimize a loss function to train an AI model (Gradient Descent).

---

# [[Summary]]

[[Differential Calculus]] is the mathematical study of continuous change. By formalizing the concept of a limit, we can evaluate behaviors at infinitesimally small intervals. The derivative acts as a powerful tool to measure instantaneous rates of change, slope, and sensitivity. Through established rules (Power, Product, Quotient, Chain), differentiation becomes a systematic algebraic process. These tools culminate in robust applications: evaluating complex limits via [[L'Hôpital's Rule]], sketching intricate functions, and solving real-world [[Optimization Problems]] in engineering and physics.

---

# [[Related Notes]]

* [[Integral Calculus]]
* [[Multivariable Calculus]]
* [[Limits and Continuity]]
* [[Optimization Problems]]
* [[Physics: Kinematics]]
* [[Differential Equations]]