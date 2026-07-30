# [[Eigenvalues, Eigenvectors, and Orthogonality]]

## [[Eigenvalues and Eigenvectors]]

In linear algebra, a matrix acts as a [[Linear Transformation]] that rotates, stretches, or shears space. Most vectors change direction when this transformation is applied. However, for a given square matrix $A$, there exist special non-zero vectors that only stretch or shrink (scale) without changing their underlying direction. These are called [[Eigenvectors]], and the scalar by which they stretch or shrink is the [[Eigenvalue]].

Mathematically, for an $n \times n$ matrix $A$, an eigenvector is a non-zero vector $x$ such that:

$$Ax = \lambda x$$

**Variables:**

- $A$: A square $n \times n$ matrix (dimensionless in pure math, though it can carry units depending on the physical system)
    
- $x$: The [[Eigenvector]] (a non-zero column vector in $\mathbb{R}^n$)
    
- $\lambda$: The [[Eigenvalue]] (a scalar, can be real or complex)
    

**Geometric Significance:**

If you imagine $A$ as a force warping a 2D plane, the eigenvectors form the rigid axes of that warp. They are the fundamental directions intrinsic to the matrix itself.

**ASCII Diagram of an Eigenvector:**

Plaintext

```
      y                                  y
      |     . Ax = \lambda x (scaled)    |
      |    /                             |
      |   /                              |      . v (ordinary vector)
      |  / x (eigenvector)               |     /|  changes direction
      | /                                |    / |  when multiplied by A
      |/                                 |   /  V Av
------|--------> x                 ------|/-------> x
```

### [[The Characteristic Equation]]

To find the eigenvalues of a matrix $A$, we rewrite the definition equation:

$$Ax = \lambda Ix$$

$$Ax - \lambda Ix = 0$$

$$(A - \lambda I)x = 0$$

For $x$ to be a non-zero vector, the matrix $(A - \lambda I)$ must not be invertible. According to the [[Invertible Matrix Theorem]], a matrix is non-invertible if and only if its determinant is zero. This leads to the **Characteristic Equation**:

$$\det(A - \lambda I) = 0$$

Solving this polynomial equation for $\lambda$ yields the eigenvalues. To find the corresponding eigenvectors, we substitute each $\lambda$ back into $(A - \lambda I)x = 0$ and find the [[Null Space]] (or eigenspace) of that new matrix.

## [[Diagonalization]]

A square matrix $A$ is said to be diagonalizable if it is similar to a diagonal matrix $D$. This means there exists an invertible matrix $P$ such that:

$$A = PDP^{-1}$$

**Variables:**

- $D$: A diagonal matrix containing the eigenvalues of $A$ along its main diagonal.
    
- $P$: An invertible matrix whose columns are the corresponding linearly independent eigenvectors of $A$.
    

### [[The Diagonalization Theorem]]

An $n \times n$ matrix $A$ is diagonalizable if and only if it has exactly $n$ linearly independent eigenvectors.

**Physical Significance:**

Calculating $A^k$ (matrix exponentiation) is computationally exhausting. However, if $A$ is diagonalizable, then $A^k = PD^kP^{-1}$. Since $D$ is a diagonal matrix, $D^k$ is simply calculated by raising each individual diagonal entry to the power of $k$. This property is critical in solving linear [[Differential Equations]] and modeling discrete dynamical systems (like Markov chains).

## [[Orthogonality]]

### [[Inner Product]] (Dot Product)

The inner product of two vectors $u$ and $v$ in $\mathbb{R}^n$ is a scalar value calculated by multiplying corresponding entries and summing them.

$$u \cdot v = u^T v = \sum_{i=1}^{n} u_i v_i$$

### [[Length and Distance]]

The length (or **norm**) of a vector $v$ is the square root of the inner product of the vector with itself.

$$\Vert{}v\Vert{} = \sqrt{v \cdot v} = \sqrt{v_1^2 + v_2^2 + ... + v_n^2}$$

The distance between two vectors $u$ and $v$ is the length of their difference: $\Vert{}u - v\Vert{}$.

### [[Orthogonal Sets]]

Two vectors $u$ and $v$ are **orthogonal** (perpendicular in multidimensional space) if and only if their inner product is zero:

$$u \cdot v = 0$$

A set of vectors $\{u_1, u_2, ..., u_p\}$ is an [[Orthogonal Set]] if every pair of distinct vectors in the set is orthogonal ($u_i \cdot u_j = 0$ for $i \neq j$). If the vectors also have a length of $1$ ($\Vert{}u_i\Vert{} = 1$), it is an **Orthonormal Set**.

## [[Orthogonal Projections]]

An [[Orthogonal Projection]] allows us to decompose a vector $y$ into two components: one component $\hat{y}$ that is parallel to a subspace (or vector $u$), and one component $z$ that is orthogonal to that subspace.

The projection of a vector $y$ onto a non-zero vector $u$ is given by:

$$\text{proj}_u y = \hat{y} = \left( \frac{y \cdot u}{u \cdot u} \right) u$$

**ASCII Diagram of Orthogonal Projection:**

Plaintext

```
           y
          /|
         / |
        /  | z = (y - \hat{y})
       /   | (orthogonal error)
      /    |
     *-----*----------> u
       \hat{y} (projection)
```

### [[Gram-Schmidt Process]]

The [[Gram-Schmidt Process]] is a simple algorithm for producing an orthogonal (or orthonormal) basis for any non-zero subspace of $\mathbb{R}^n$.

Given a basis $\{x_1, x_2, ..., x_p\}$ for a subspace $W$, we construct an orthogonal basis $\{v_1, v_2, ..., v_p\}$ step-by-step:

1. $v_1 = x_1$
    
2. $v_2 = x_2 - \text{proj}_{v_1} x_2 = x_2 - \left( \frac{x_2 \cdot v_1}{v_1 \cdot v_1} \right) v_1$
    
3. $v_3 = x_3 - \text{proj}_{v_1} x_3 - \text{proj}_{v_2} x_3 = x_3 - \left( \frac{x_3 \cdot v_1}{v_1 \cdot v_1} \right) v_1 - \left( \frac{x_3 \cdot v_2}{v_2 \cdot v_2} \right) v_2$
    
4. And so on for all $p$ vectors.
    

To make this an **orthonormal basis**, normalize each vector by dividing by its length: $u_i = \frac{v_i}{\Vert{}v_i\Vert{}}$.

## [[Least Squares Problems]]

In real-world data science and engineering, systems of equations $Ax = b$ are almost always **inconsistent** (i.e., there are more equations than unknowns, and no single line/plane passes perfectly through all data points).

Instead of an exact solution, we seek a [[Least Squares]] solution $\hat{x}$ that makes $A\hat{x}$ as close to $b$ as possible. We want to minimize the length of the error vector $\Vert{}b - A\hat{x}\Vert{}$.

Geometrically, the closest point in the [[Column Space]] of $A$ to the vector $b$ is the orthogonal projection of $b$ onto $Col(A)$.

### [[Normal Equations]]

To find the least squares solution $\hat{x}$, we solve the **Normal Equations**:

$$A^T A \hat{x} = A^T b$$

If $A^T A$ is invertible (which occurs when the columns of $A$ are linearly independent), the unique least-squares solution is:

$$\hat{x} = (A^T A)^{-1} A^T b$$

## [[Solved Examples]]

### Example 1: Finding Eigenvalues and Eigenvectors

**Problem:** Find the eigenvalues and eigenvectors of $A = \begin{bmatrix} 2 & 3 \\ 3 & 2 \end{bmatrix}$.

**Solution:**

1. Setup the Characteristic Equation: $\det(A - \lambda I) = 0$
    
    $$\det \begin{bmatrix} 2-\lambda & 3 \\ 3 & 2-\lambda \end{bmatrix} = 0$$
    
2. Expand the determinant:
    
    $$(2-\lambda)(2-\lambda) - (3)(3) = 0$$
    
    $$4 - 4\lambda + \lambda^2 - 9 = 0 \implies \lambda^2 - 4\lambda - 5 = 0$$
    
3. Factor to find Eigenvalues:
    
    $$(\lambda - 5)(\lambda + 1) = 0 \implies \lambda_1 = 5, \lambda_2 = -1$$
    
4. Find the Eigenvector for $\lambda_1 = 5$:
    
    Substitute $\lambda=5$ into $(A - \lambda I)x = 0$:
    
    $$\begin{bmatrix} -3 & 3 \\ 3 & -3 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$
    
    This reduces to $-3x_1 + 3x_2 = 0 \implies x_1 = x_2$. Let $x_2 = 1$, then $v_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$.
    
5. Find the Eigenvector for $\lambda_2 = -1$:
    
    $$\begin{bmatrix} 3 & 3 \\ 3 & 3 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$
    
    This reduces to $3x_1 + 3x_2 = 0 \implies x_1 = -x_2$. Let $x_2 = 1$, then $v_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$.
    

### Example 2: The Least Squares Solution

**Problem:** Find the least squares solution to $Ax = b$ where $A = \begin{bmatrix} 1 & 1 \\ 1 & -1 \\ 1 & 1 \end{bmatrix}$ and $b = \begin{bmatrix} 2 \\ 1 \\ 3 \end{bmatrix}$.

**Solution:**

1. Find $A^T A$:
    
    $$A^T A = \begin{bmatrix} 1 & 1 & 1 \\ 1 & -1 & 1 \end{bmatrix} \begin{bmatrix} 1 & 1 \\ 1 & -1 \\ 1 & 1 \end{bmatrix} = \begin{bmatrix} 3 & 1 \\ 1 & 3 \end{bmatrix}$$
    
2. Find $A^T b$:
    
    $$A^T b = \begin{bmatrix} 1 & 1 & 1 \\ 1 & -1 & 1 \end{bmatrix} \begin{bmatrix} 2 \\ 1 \\ 3 \end{bmatrix} = \begin{bmatrix} (2+1+3) \\ (2-1+3) \end{bmatrix} = \begin{bmatrix} 6 \\ 4 \end{bmatrix}$$
    
3. Solve the normal equations $(A^T A)\hat{x} = A^T b$:
    
    $$\begin{bmatrix} 3 & 1 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 6 \\ 4 \end{bmatrix}$$
    
4. Using the $2 \times 2$ inverse formula for $(A^T A)^{-1}$:
    
    $$(A^T A)^{-1} = \frac{1}{(3)(3) - (1)(1)} \begin{bmatrix} 3 & -1 \\ -1 & 3 \end{bmatrix} = \frac{1}{8} \begin{bmatrix} 3 & -1 \\ -1 & 3 \end{bmatrix}$$
    
5. Multiply by $A^T b$:
    
    $$\hat{x} = \frac{1}{8} \begin{bmatrix} 3 & -1 \\ -1 & 3 \end{bmatrix} \begin{bmatrix} 6 \\ 4 \end{bmatrix} = \frac{1}{8} \begin{bmatrix} 18 - 4 \\ -6 + 12 \end{bmatrix} = \frac{1}{8} \begin{bmatrix} 14 \\ 6 \end{bmatrix} = \begin{bmatrix} 7/4 \\ 3/4 \end{bmatrix}$$
    

# [[Formula Sheet]]

- **Eigenvalue Equation:** $Ax = \lambda x$
    
- **Characteristic Equation:** $\det(A - \lambda I) = 0$
    
- **Diagonalization:** $A = PDP^{-1}$
    
- **Matrix Exponentiation:** $A^k = PD^kP^{-1}$
    
- **Inner (Dot) Product:** $u \cdot v = u^T v$
    
- **Length (Norm):** $\Vert{}v\Vert{} = \sqrt{v \cdot v}$
    
- **Orthogonal Projection of $y$ onto $u$:** $\hat{y} = \left( \frac{y \cdot u}{u \cdot u} \right) u$
    
- **Gram-Schmidt Step:** $v_k = x_k - \sum_{i=1}^{k-1} \text{proj}_{v_i} x_k$
    
- **Normal Equations (Least Squares):** $A^T A \hat{x} = A^T b$
    

# [[Problem Solving Strategy]]

1. **For Eigenvalues/Vectors:**
    
    - Always subtract $\lambda$ from the main diagonal of $A$ to set up $\det(A - \lambda I) = 0$.
        
    - For a $3 \times 3$ or larger, look for rows or columns with multiple zeros to make cofactor expansion easier.
        
    - When solving $(A - \lambda I)x = 0$ for the eigenvectors, you _must_ end up with at least one row of zeros (a free variable). If you don't, your eigenvalue is incorrect.
        
2. **For Diagonalization:**
    
    - Arrange the eigenvalues in $D$ in any order, but make absolutely sure that the corresponding eigenvectors in $P$ match the exact same column order.
        
3. **For Gram-Schmidt:**
    
    - It is often easier to clear fractions when finding $v_2, v_3, \dots$ before moving to the next step. Scaling an orthogonal vector by a constant does not change its orthogonality, but it prevents arithmetic mistakes.
        
4. **For Least Squares:**
    
    - Never attempt to invert a non-square matrix. Form the normal equations $A^TA$ first, which always yields a square, symmetric, and usually invertible matrix.
        

# [[Common Mistakes]]

- **The Trivial Vector Trap:** Forgetting that an eigenvector $x$ must be non-zero by definition. (If $x=0$, $A0 = \lambda 0$ is trivially true for any $\lambda$).
    
- **Failing to Match $P$ and $D$:** When diagonalizing, putting $\lambda_1$ in column 1 of $D$, but putting $v_2$ in column 1 of $P$. The columns must correspond exactly.
    
- **Normalizing Too Early in Gram-Schmidt:** Normalizing the vectors at every step (turning them into unit vectors) introduces nasty square roots into the middle of the calculation. Wait until the very end to normalize the entire basis.
    
- **Misinterpreting the Error Vector in Least Squares:** The projection $\hat{y}$ is not the error; the error is the orthogonal vector $z = y - \hat{y}$.
    

# [[Applications]]

- **Principal Component Analysis (PCA):** In data science and machine learning, PCA uses the eigenvectors of a dataset's covariance matrix to identify the directions of maximum variance. This allows high-dimensional data (like 1000-pixel images) to be compressed into a few principal dimensions.
    
- **Mechanical Engineering (Vibrations):** The [[Eigenvalues]] of a system's mass-stiffness matrix represent the natural frequencies (resonant frequencies) of the structure. The [[Eigenvectors]] represent the "mode shapes" (how the structure physically deforms at that frequency).
    
- **Quantum Mechanics:** Observables like energy, momentum, and spin are represented by operators (matrices). The possible measurement outcomes are strictly the [[Eigenvalues]] of the operator, and the quantum states correspond to the [[Eigenvectors]].
    
- **Regression Analysis:** The [[Least Squares]] method is the mathematical engine behind almost all curve-fitting and linear regression algorithms used in statistics, economics, and artificial intelligence.
    

# [[Summary]]

The concepts of [[Eigenvalues and Eigenvectors]] unlock the intrinsic properties of square matrices, revealing the hidden axes along which transformations simply scale space. This leads directly to [[Diagonalization]], heavily simplifying complex matrix operations and dynamical system analysis. Moving into geometric vector space, [[Orthogonality]] provides a framework to measure distance and independence. When real-world data presents inconsistent equations, we utilize [[Orthogonal Projections]] and the [[Normal Equations]] to find the [[Least Squares]] solution, forming the backbone of modern data analysis and approximation theory.

# [[Related Notes]]

- [[Linear Systems and Matrix Algebra]]
    
- [[Vector Spaces and Linear Transformations]]
    
- [[Differential Equations]]
    
- [[Quantum Mechanics]]
    
- [[Machine Learning Linear Regression]]
    
- [[Principal Component Analysis]]