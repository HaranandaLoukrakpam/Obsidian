# [[Integral Calculus and Infinite Series]]

## [[Integration Foundations]]

While differential calculus concerns itself with instantaneous rates of change, **integral calculus** focuses on the accumulation of quantities, such as areas under curves, total distance traveled, and accumulated growth.

### [[Antiderivatives]] and [[Indefinite Integrals]]

An **antiderivative** of a function $f(x)$ is a function $F(x)$ such that $F'(x) = f(x)$. The set of all antiderivatives is called the [[Indefinite Integral]], denoted by:

$$\int f(x) dx = F(x) + C$$

**Variables:**

- $\int$: Integral symbol
    
- $f(x)$: Integrand (the function being integrated)
    
- $dx$: Differential (indicates the variable of integration)
    
- $F(x)$: Antiderivative
    
- $C$: Constant of integration (accounts for the fact that the derivative of a constant is zero)
    

### [[Riemann Sums]] and [[Definite Integrals]]

A **Riemann sum** approximates the area under a curve by dividing the region into vertical rectangles. As the number of rectangles approaches infinity (and their width approaches zero), the sum converges to the exact area, defined as the [[Definite Integral]]:

$$\int_{a}^{b} f(x) dx = \lim_{n \to \infty} \sum_{i=1}^{n} f(x_i^*)\Delta x$$

**Variables:**

- $a, b$: Lower and upper limits of integration
    
- $n$: Number of subintervals
    
- $\Delta x$: Width of each subinterval ($\frac{b-a}{n}$)
    
- $x_i^*$: Sample point in the $i$-th subinterval
    

### [[Fundamental Theorem of Calculus]] (FTC)

The FTC bridges differential and integral calculus, proving they are inverse processes.

**Part 1:** If $f(x)$ is continuous on $[a,b]$, then the function $g(x) = \int_a^x f(t)dt$ is continuous on $[a,b]$ and differentiable on $(a,b)$, and $g'(x) = f(x)$.

**Part 2:** If $f(x)$ is continuous on $[a,b]$ and $F(x)$ is any antiderivative of $f(x)$, then:

$$\int_{a}^{b} f(x) dx = F(b) - F(a)$$

## [[Techniques of Integration]]

Because reading a derivative backward is often complex, several algebraic techniques exist to simplify integrands.

### [[u-substitution]]

This is the reverse of the Chain Rule. It is used when an integrand contains a composite function and the derivative of the "inner" function is present.

Let $u = g(x)$, then $du = g'(x)dx$.

$$\int f(g(x))g'(x) dx = \int f(u) du$$

### [[Integration by Parts]]

Derived from the Product Rule of differentiation. It transforms the integral of a product of functions into a simpler integral.

$$\int u dv = uv - \int v du$$

_Heuristic for choosing $u$:_ **LIATE** (Logarithmic, Inverse trig, Algebraic, Trigonometric, Exponential). Choose the function that appears first in this list to be $u$.

### [[Trigonometric Substitution]]

Used to evaluate integrals containing radical expressions by exploiting trigonometric identities (like $\sin^2\theta + \cos^2\theta = 1$).

|**Radical Expression**|**Substitution**|**Identity Used**|
|---|---|---|
|$\sqrt{a^2 - x^2}$|$x = a \sin(\theta)$|$1 - \sin^2(\theta) = \cos^2(\theta)$|
|$\sqrt{a^2 + x^2}$|$x = a \tan(\theta)$|$1 + \tan^2(\theta) = \sec^2(\theta)$|
|$\sqrt{x^2 - a^2}$|$x = a \sec(\theta)$|$\sec^2(\theta) - 1 = \tan^2(\theta)$|

### [[Partial Fraction Decomposition]]

Used to integrate rational functions $P(x)/Q(x)$ where the degree of $P(x)$ is less than the degree of $Q(x)$. The denominator $Q(x)$ is factored, and the fraction is split into a sum of simpler fractions that can be easily integrated (usually yielding logarithms).

## [[Applications of Integration]]

### [[Area Between Curves]]

The area $A$ between two continuous curves $y = f(x)$ (top) and $y = g(x)$ (bottom) from $x=a$ to $x=b$ is:

$$A = \int_{a}^{b} [f(x) - g(x)] dx$$

### [[Volumes of Solids of Revolution]]

When a planar region is revolved around an axis, it generates a 3D solid.

**ASCII Diagram of a Disk:**

Plaintext

```
      y
      |   /---\ 
    f(x)-|     |  <-- Cross-section is a circular disk of radius f(x)
      |   \---/
      +--------- x
          dx (thickness)
```

**1. [[Disk Method]] / [[Washer Method]]**

Used when slicing _perpendicular_ to the axis of revolution.

- **Disk:** $V = \pi \int_{a}^{b} [R(x)]^2 dx$
    
- **Washer (Hollow Center):** $V = \pi \int_{a}^{b} \left( [R_{outer}(x)]^2 - [r_{inner}(x)]^2 \right) dx$
    

**2. [[Cylindrical Shell Method]]**

Used when slicing _parallel_ to the axis of revolution. The solid is broken into nested cylindrical shells.

$$V = 2\pi \int_{a}^{b} r(x) h(x) dx$$

Where $r(x)$ is the radius (usually $x$) and $h(x)$ is the height (usually $f(x)$).

## [[Sequences and Series]]

### Definitions

- **Sequence:** An ordered list of numbers $\{a_n\} = a_1, a_2, a_3, ...$
    
- **Series:** The sum of the terms of a sequence, $\sum_{n=1}^{\infty} a_n$.
    

A series **converges** if the sequence of its partial sums $S_N = \sum_{n=1}^{N} a_n$ approaches a finite limit as $N \to \infty$. Otherwise, it **diverges**.

### [[Convergence Tests]]

|**Test**|**Condition for Convergence**|**Condition for Divergence**|
|---|---|---|
|**[[Integral Test]]**|$\int_1^\infty f(x)dx$ converges|$\int_1^\infty f(x)dx$ diverges|
|**[[Ratio Test]]**|$L = \lim_{n \to \infty} \left\Vert{} \frac{a_{n+1}}{a_n} \right\Vert{} < 1$|$L > 1$|
|**[[Root Test]]**|$L = \lim_{n \to \infty} \sqrt[n]{\Vert{}a_n\Vert{}} < 1$|$L > 1$|
|**[[Alternating Series Test]]**|$\lim a_n = 0$ AND $a_{n+1} \le a_n$|Fails if limits $\neq 0$|

## [[Power Series]]

A [[Power Series]] is an infinite series involving a variable $x$, centered at $x=c$:

$$\sum_{n=0}^{\infty} c_n (x-c)^n = c_0 + c_1(x-c) + c_2(x-c)^2 + ...$$

### [[Radius of Convergence]]

The series converges absolutely for $\Vert{}x - c\Vert{} < R$, where $R$ is the **radius of convergence**. We typically find $R$ using the [[Ratio Test]]. The set of all $x$ for which the series converges is the **Interval of Convergence**.

### [[Taylor and Maclaurin Series]]

If a function $f(x)$ can be represented by a power series, its coefficients are determined by its derivatives. The **Taylor Series** centered at $x=a$ is:

$$f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x-a)^n$$

A **Maclaurin Series** is simply a Taylor Series centered at $a = 0$:

$$f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!} x^n$$

## [[Solved Examples]]

### Example 1: Integration by Parts

**Problem:** Evaluate $\int x e^x dx$.

**Solution:**

1. Choose $u$ and $dv$ using LIATE (Algebraic before Exponential).
    
    Let $u = x$ and $dv = e^x dx$.
    
2. Compute $du$ and $v$:
    
    $du = dx$ and $v = \int e^x dx = e^x$.
    
3. Apply the Integration by Parts formula: $\int u dv = uv - \int v du$
    
    $$\int x e^x dx = x e^x - \int e^x dx$$
    
    $$\int x e^x dx = x e^x - e^x + C$$
    

### Example 2: Volume by Washer Method

**Problem:** Find the volume of the solid formed by revolving the region bounded by $y=x^2$ and $y=x$ around the x-axis.

**Solution:**

1. Find intersection points: $x^2 = x \implies x(x-1) = 0 \implies x=0, 1$.
    
2. Identify Outer ($R$) and Inner ($r$) radii. On $[0,1]$, $x \ge x^2$.
    
    $R(x) = x$ and $r(x) = x^2$.
    
3. Apply the Washer Method formula:
    
    $$V = \pi \int_{0}^{1} \left( (x)^2 - (x^2)^2 \right) dx = \pi \int_{0}^{1} (x^2 - x^4) dx$$
    
4. Evaluate the integral:
    
    $$V = \pi \left[ \frac{x^3}{3} - \frac{x^5}{5} \right]_0^1 = \pi \left( \frac{1}{3} - \frac{1}{5} \right) = \pi \left( \frac{5 - 3}{15} \right) = \frac{2\pi}{15} \text{ cubic units}$$
    

### Example 3: Radius of Convergence

**Problem:** Find the radius of convergence of the power series $\sum_{n=1}^{\infty} \frac{x^n}{n \cdot 2^n}$.

**Solution:**

1. Apply the Ratio Test: $a_n = \frac{x^n}{n \cdot 2^n}$.
    
    $$L = \lim_{n \to \infty} \left\vert{} \frac{x^{n+1}}{(n+1) 2^{n+1}} \cdot \frac{n \cdot 2^n}{x^n} \right\vert{}$$
    
2. Simplify:
    
    $$L = \lim_{n \to \infty} \left\vert{} \frac{x}{2} \cdot \frac{n}{n+1} \right\vert{} = \left\vert{} \frac{x}{2} \right\vert{} \lim_{n \to \infty} \frac{n}{n+1} = \left\vert{} \frac{x}{2} \right\vert{} (1)$$
    
3. For convergence, $L < 1$:
    
    $$\left\vert{} \frac{x}{2} \right\vert{} < 1 \implies \vert{}x\vert{} < 2$$
    
    **Answer:** The radius of convergence is $R = 2$.
    

# [[Formula Sheet]]

- **Basic Integrals:**
    
    $\int x^n dx = \frac{x^{n+1}}{n+1} + C \quad (n \neq -1)$
    
    $\int \frac{1}{x} dx = \ln\Vert{}x\Vert{} + C$
    
    $\int e^x dx = e^x + C$
    
- **Integration by Parts:** $\int u dv = uv - \int v du$
    
- **FTC Part 2:** $\int_{a}^{b} f(x) dx = F(b) - F(a)$
    
- **Volume (Disk):** $V = \pi \int R^2 dx$
    
- **Taylor Series:** $\sum \frac{f^{(n)}(a)}{n!} (x-a)^n$
    
- **Maclaurin Series for $e^x$:** $1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + ...$
    

# [[Problem Solving Strategy]]

1. **For Integrals:**
    
    - Always simplify the integrand algebraically or trigonometrically first.
        
    - Look for an obvious inner function and its derivative (indicates [[u-substitution]]).
        
    - If you see a product of two unrelated functions (like $x \sin x$), use [[Integration by Parts]].
        
    - If it involves $\sqrt{a^2 \pm x^2}$, draw a right triangle and use [[Trigonometric Substitution]].
        
    - If it's a rational polynomial, factor the denominator for [[Partial Fraction Decomposition]].
        
2. **For Area/Volume:**
    
    - Always sketch the curves.
        
    - Find points of intersection to determine your limits of integration ($a$ and $b$).
        
    - Determine which curve is the "upper/outer" and which is the "lower/inner".
        
3. **For Series Convergence:**
    
    - If the terms don't go to zero, it diverges immediately (Nth Term Test).
        
    - If it has factorials ($!$) or constants to the power of $n$ ($2^n$), use the [[Ratio Test]].
        
    - If it alternates sign ($(-1)^n$), use the [[Alternating Series Test]].
        

# [[Common Mistakes]]

- **Forgetting the $+ C$:** The most classic calculus error. Every indefinite integral must include a constant of integration.
    
- **Incorrect limits after u-substitution:** When evaluating a definite integral using $u$-substitution, you must either change the bounds from $x$ to $u$, or substitute back to $x$ before evaluating.
    
- **Confusing Sequences and Series:** A sequence can converge to $0$, but the series built from it might diverge (e.g., the Harmonic Series $\sum 1/n$).
    
- **Radius vs. Interval:** The [[Ratio Test]] gives the radius of convergence, but the interval endpoints must be tested individually, as the Ratio Test is inconclusive ($L=1$) at the boundary points.
    

# [[Applications]]

- **Physics and Mechanics:** Integration is used to calculate Work (integral of force over distance), Center of Mass, and Moments of Inertia.
    
- **Probability and Statistics:** Continuous probability distributions (like the normal bell curve) use definite integrals to calculate the probability of events occurring within a specific range.
    
- **Engineering Computations:** [[Taylor and Maclaurin Series]] are essential in computer science and numerical methods. Because computers can only add and multiply, transcendental functions (like $\sin x$ or $e^x$) are approximated by evaluating the first few terms of their power series.
    

# [[Summary]]

[[Integral Calculus and Infinite Series]] deal with the accumulation of infinitesimal quantities to evaluate macroscopic systems. The [[Fundamental Theorem of Calculus]] elegantly ties integration directly to differentiation. Armed with techniques like [[u-substitution]] and [[Integration by Parts]], we can calculate complex areas, volumes, and physical work. The transition into [[Sequences and Series]] expands this concept from geometric accumulation to infinite algebraic sums. By utilizing [[Convergence Tests]], we can determine if an infinite addition resolves to a finite number, ultimately allowing us to represent complex continuous functions as infinite polynomials via [[Power Series]].

# [[Related Notes]]

- [[Differential Calculus]]
    
- [[Multivariable Calculus]]
    
- [[Differential Equations]]
    
- [[Physics Mechanics]]
    
- [[Numerical Analysis]]