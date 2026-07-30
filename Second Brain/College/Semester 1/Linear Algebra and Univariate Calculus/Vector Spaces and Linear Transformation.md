# [[Vector Spaces and Linear Transformations]]

## [[Vector Spaces]]

A [[Vector Space]] (or linear space) is a fundamental mathematical structure consisting of a set of objects, called **vectors**, along with two operations: vector addition and scalar multiplication.

To formally be a vector space, the set $V$ and the operations must satisfy a set of ten axioms (such as commutativity, associativity, distributive properties, and the existence of a zero vector and additive inverses).

**Canonical Example ($\mathbb{R}^n$):**

The most common vector space in engineering is $\mathbb{R}^n$, which consists of all $n$-tuples of real numbers. For example, $\mathbb{R}^2$ represents the 2D Cartesian plane, and $\mathbb{R}^3$ represents 3D physical space.

### [[Subspaces]]

A [[Subspace]] $H$ is a subset of a vector space $V$ that is, in itself, a valid vector space under the same operations as $V$. To prove that a subset $H$ is a subspace, you only need to verify three specific conditions:

1. **The Zero Vector:** The zero vector of $V$ must be in $H$.
    
2. **Closure under Addition:** If $u$ and $v$ are in $H$, then $u + v$ must be in $H$.
    
3. **Closure under Scalar Multiplication:** If $u$ is in $H$ and $c$ is a scalar, then $cu$ must be in $H$.
    

_Geometric Significance:_ In $\mathbb{R}^3$, the valid subspaces are the origin itself (a point), any line passing strictly through the origin, any plane passing strictly through the origin, and the entire space $\mathbb{R}^3$ itself.

## [[Linear Independence]] and [[Bases]]

### [[Spanning Sets]]

Given a set of vectors $S = \{v_1, v_2, ..., v_p\}$ in a vector space $V$, a [[Linear Combination]] is any expression of the form:

$$y = c_1v_1 + c_2v_2 + ... + c_pv_p$$

The set of _all_ possible linear combinations of $S$ is called the **Span** of $S$, denoted as $\text{Span}\{v_1, v_2, ..., v_p\}$.

### [[Linear Independence]]

A set of vectors $\{v_1, v_2, ..., v_p\}$ is said to be **linearly independent** if the vector equation:

$$c_1v_1 + c_2v_2 + ... + c_pv_p = 0$$

has _only_ the trivial solution (i.e., $c_1 = c_2 = ... = c_p = 0$).

If there is any non-trivial solution (where at least one $c_i \neq 0$), the set is **linearly dependent**.

_Intuition:_ If a set is linearly dependent, at least one vector in the set can be written as a linear combination of the others. It represents "redundant" geometric information.

### [[Basis Vectors]]

A [[Basis]] for a vector space $H$ is a set of vectors $\mathcal{B} = \{b_1, b_2, ..., b_p\}$ that satisfies two conditions:

1. $\mathcal{B}$ is a linearly independent set.
    
2. $\text{Span}\{b_1, ..., b_p\} = H$.
    

_Physical Significance:_ A basis represents the most efficient, non-redundant set of "building blocks" needed to construct every point in the space.

### [[Coordinate Systems]]

If $\mathcal{B} = \{b_1, b_2, ..., b_n\}$ is a basis for $V$, then for each $x$ in $V$, there exists a unique set of scalars $c_1, ..., c_n$ such that:

$$x = c_1b_1 + c_2b_2 + ... + c_nb_n$$

These scalars are the **coordinates** of $x$ relative to the basis $\mathcal{B}$, denoted as $[x]_\mathcal{B}$.

## [[Dimension and Structure]]

### [[Dimension]]

The [[Dimension]] of a non-zero vector space $V$, denoted as $\dim(V)$, is defined as the number of vectors in any basis for $V$. (All bases for a specific vector space have the exact same number of vectors).

### [[Null Space]] and [[Column Space]]

For an $m \times n$ matrix $A$:

- **[[Null Space]] ($Nul A$):** The set of all solutions to the homogeneous equation $Ax = 0$. It is a subspace of $\mathbb{R}^n$.
    
- **[[Column Space]] ($Col A$):** The set of all linear combinations of the columns of $A$. It represents all possible vectors $b$ for which $Ax = b$ has a solution. It is a subspace of $\mathbb{R}^m$.
    

### [[The Rank Theorem]]

The **Rank** of a matrix $A$ is the dimension of its column space (which also equals the dimension of its row space). The **Nullity** is the dimension of its null space.

$$\text{Rank}(A) + \text{Nullity}(A) = n$$

**Variables:**

- $\text{Rank}(A)$: Number of pivot columns in $A$.
    
- $\text{Nullity}(A)$: Number of free variables in the equation $Ax=0$.
    
- $n$: The total number of columns in $A$ (the dimension of the domain).
    

## [[Linear Transformations]]

A [[Linear Transformation]] $T$ from a vector space $V$ into a vector space $W$ is a rule that assigns each vector $x$ in $V$ a unique vector $T(x)$ in $W$, such that:

1. $T(u + v) = T(u) + T(v)$ for all $u, v$ in $V$.
    
2. $T(cu) = cT(u)$ for all $u$ in $V$ and all scalars $c$.
    

### Matrix Representations

Every linear transformation $T: \mathbb{R}^n \to \mathbb{R}^m$ can be represented by standard matrix multiplication $T(x) = Ax$.

The standard matrix $A$ is found by evaluating the transformation on the columns of the identity matrix $I_n$:

$$A = [T(e_1) \quad T(e_2) \quad ... \quad T(e_n)]$$

### [[Kernel]] and [[Range]]

- The **[[Kernel]]** of $T$ (equivalent to the Null Space of $A$) is the set of all vectors $u$ in the domain $V$ such that $T(u) = 0$.
    
- The **[[Range]]** of $T$ (equivalent to the Column Space of $A$) is the set of all vectors $T(x)$ in the codomain $W$ that are actually mapped to by some $x$.
    

**ASCII Diagram of a Linear Transformation:**

Plaintext

```
   Domain (V)                       Codomain (W)
  _____________                    _____________
 |             |       T          |             |
 |   x ._______|__________________|_____. T(x)  |
 |             |                  |             |
 |    Kernel   |                  |    Range    |
 |    (...)____|__________________|_____(0)     |
 |             |                  |             |
 |_____________|                  |_____________|
```

## [[Solved Examples]]

### Example 1: Checking for a Subspace

**Problem:** Let $H$ be the set of all vectors in $\mathbb{R}^2$ of the form $\begin{bmatrix} x \\ y \end{bmatrix}$ where $x \ge 0$ and $y \ge 0$ (the first quadrant). Is $H$ a subspace of $\mathbb{R}^2$?

**Solution:**

Test the three subspace criteria:

1. **Zero vector:** $\begin{bmatrix} 0 \\ 0 \end{bmatrix}$ is in $H$ because $0 \ge 0$. (Passes)
    
2. **Addition:** If $u = \begin{bmatrix} x_1 \\ y_1 \end{bmatrix}$ and $v = \begin{bmatrix} x_2 \\ y_2 \end{bmatrix}$ are in $H$, then $u+v = \begin{bmatrix} x_1+x_2 \\ y_1+y_2 \end{bmatrix}$. Since sum of positive numbers is positive, $u+v$ is in $H$. (Passes)
    
3. **Scalar Multiplication:** Let $u = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$ (which is in $H$). Let scalar $c = -1$.
    
    Then $cu = \begin{bmatrix} -1 \\ -1 \end{bmatrix}$.
    
    Because $-1 < 0$, $cu$ is **not** in $H$. (Fails)
    

**Answer:** $H$ is not a subspace because it is not closed under scalar multiplication.

### Example 2: Finding Bases for Col A and Nul A

**Problem:** Let $A = \begin{bmatrix} 1 & -3 & 2 \\ -2 & 6 & -4 \\ 3 & -9 & 6 \end{bmatrix}$. Find a basis for $Col A$ and $Nul A$.

**Solution:**

1. **Row reduce A to find pivots:**
    
    $R_2 \leftarrow R_2 + 2R_1$
    
    $R_3 \leftarrow R_3 - 3R_1$
    
    $$RREF = \begin{bmatrix} 1 & -3 & 2 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}$$
    
2. **Basis for Col A:** The pivot is only in the first column. To form the basis, use the **original** first column of $A$.
    
    $$\text{Basis for Col A} = \left\{ \begin{bmatrix} 1 \\ -2 \\ 3 \end{bmatrix} \right\}$$
    
3. **Basis for Nul A:** Solve $Ax = 0$ using the RREF.
    
    $x_1 - 3x_2 + 2x_3 = 0 \implies x_1 = 3x_2 - 2x_3$
    
    $x_2$ and $x_3$ are free variables. Write the solution in parametric vector form:
    
    $$\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = x_2 \begin{bmatrix} 3 \\ 1 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} -2 \\ 0 \\ 1 \end{bmatrix}$$
    
    $$\text{Basis for Nul A} = \left\{ \begin{bmatrix} 3 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} -2 \\ 0 \\ 1 \end{bmatrix} \right\}$$
    

_Note: Verifying the Rank Theorem: Rank (1) + Nullity (2) = 3 (Total columns)._

# [[Formula Sheet]]

- **Linear Independence:** $c_1v_1 + ... + c_pv_p = 0 \implies c_i = 0$ for all $i$
    
- **Rank Theorem:** $\text{Rank}(A) + \dim(Nul A) = n$
    
- **Standard Matrix of a Transformation:** $A = [T(e_1) \quad T(e_2) \quad ... \quad T(e_n)]$
    
- **Change of Coordinates:** $x = P_{\mathcal{B}} [x]_{\mathcal{B}}$ (where $P_{\mathcal{B}}$ is the matrix with basis vectors as columns).
    

# [[Problem Solving Strategy]]

1. **To determine if a set of vectors is linearly independent:** Form a matrix with the vectors as columns. Row reduce to Echelon Form. If every column contains a pivot, they are independent. If there are free variables, they are dependent.
    
2. **To find a Basis for Column Space ($Col A$):** Row reduce $A$ to identify the pivot columns. **Crucial step:** The basis consists of those specific columns from the _original_ matrix $A$, not from the reduced matrix.
    
3. **To find a Basis for Null Space ($Nul A$):** Set up the augmented matrix $[A \vert{} 0]$. Row reduce to RREF. Express the pivot variables in terms of the free variables. Factor out the free variables to get the basis vectors.
    

# [[Common Mistakes]]

- **Using RREF columns for Column Space:** The row operations change the column space of a matrix. You must always use the columns from the _original_ matrix to form the basis for Col A.
    
- **Confusing domains:** For an $m \times n$ matrix, remember that vectors in the Null Space have $n$ entries (they live in $\mathbb{R}^n$), while vectors in the Column Space have $m$ entries (they live in $\mathbb{R}^m$).
    
- **Assuming $n$ vectors in $\mathbb{R}^m$ form a basis when $n \neq m$:** A basis for $\mathbb{R}^n$ must contain _exactly_ $n$ vectors. If you have 3 vectors in $\mathbb{R}^4$, they can never span the space. If you have 5 vectors in $\mathbb{R}^4$, they are guaranteed to be linearly dependent.
    

# [[Applications]]

- **Image Compression and Data Reduction:** Techniques like Principal Component Analysis (PCA) find a new, smaller [[Basis]] for a massive dataset, projecting high-dimensional data onto a lower-dimensional [[Subspace]] while retaining the most important variances.
    
- **Computer Graphics:** Scaling, rotation, and shear of 3D models are executed by multiplying coordinate vectors by standard transformation matrices.
    
- **Quantum Mechanics:** The state of a quantum system is described as a vector in a complex vector space (Hilbert space). Observables (like momentum or position) are modeled as [[Linear Transformations]] acting on these state vectors.
    
- **Control Theory:** The [[Column Space]] relates to the "controllability" of an engineering system (where can the system be driven?), while the [[Null Space]] relates to "observability" (which states produce zero output?).
    

# [[Summary]]

The study of [[Vector Spaces and Linear Transformations]] lifts the mechanics of solving linear equations into a broader, more geometric framework. By defining spaces through axioms, we identify [[Subspaces]] governed by rigid rules of closure. Understanding how to construct these spaces using a [[Basis]] and testing for [[Linear Independence]] allows engineers to remove redundancy from mathematical models. Matrices stop being mere grids of numbers and are understood as mappings—[[Linear Transformations]]—that morph one vector space into another, governed elegantly by the [[Rank Theorem]] balancing their [[Kernel]] and [[Range]].

# [[Related Notes]]

- [[Linear Systems and Matrix Algebra]]
    
- [[Eigenvalues and Eigenvectors]]
    
- [[Orthogonality and Least Squares]]
    
- [[Differential Equations]]
    
- [[Quantum Mechanics]]