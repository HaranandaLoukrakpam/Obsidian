# [[Linear Systems and Matrix Algebra]]

## [[Systems of Linear Equations]]

A linear equation in $n$ variables $x_1, x_2, ..., x_n$ is an equation that can be written in the form:

$$a_1x_1 + a_2x_2 + ... + a_nx_n = b$$

A **system of linear equations** is a collection of one or more linear equations involving the same variables.

### Geometric Interpretation

In two dimensions ($\mathbb{R}^2$), a linear equation represents a line. A system of two equations represents two lines, and their solution is the point of intersection.

Plaintext

```
    y (Unique)             y (No Solution)          y (Infinite)
    |   / Line 1           |   / Line 1             |   / Both Lines
    |  /                   |  /                     |  /
----|-/---- x          ----|-/----/---- x       ----|-/---- x
    |/ \                   |/    /                  |/
    /   \ Line 2           /    / Line 2            /
   /     \                /    /                   /
```

- **Consistent System:** Has one unique solution (lines intersect at one point) or infinitely many solutions (lines lie on top of each other).
    
- **Inconsistent System:** Has no solution (lines are parallel and never intersect).
    

### [[Row Reduction]] and [[Echelon Forms]]

To solve systems systematically, we represent the coefficients and constants in an **Augmented Matrix**. We then apply elementary row operations (swapping rows, multiplying a row by a non-zero scalar, adding a multiple of one row to another) to simplify the matrix.

The goal is to reach **Row Echelon Form (REF)** or **Reduced Row Echelon Form (RREF)**:

1. **REF:** All non-zero rows are above any rows of all zeros. The leading coefficient (pivot) of a non-zero row is always strictly to the right of the leading coefficient of the row above it.
    
2. **RREF:** It is in REF, every leading coefficient is $1$, and each leading $1$ is the only non-zero entry in its column.
    

## [[Matrix Algebra]]

A **Matrix** is a rectangular array of numbers arranged in rows and columns. A matrix $A$ with $m$ rows and $n$ columns has dimensions $m \times n$.

### Matrix Addition and Scalar Multiplication

- **Addition:** Two matrices can be added _only_ if they have the exact same dimensions. Addition is performed element-wise.
    
    $$(A + B)_{ij} = A_{ij} + B_{ij}$$
    
- **Scalar Multiplication:** Multiplying a matrix by a real number (scalar) scales every element in the matrix.
    
    $$(cA)_{ij} = c(A_{ij})$$
    

### [[Matrix Multiplication]]

The product of two matrices $A$ (of size $m \times n$) and $B$ (of size $n \times p$) is a new matrix $C$ (of size $m \times p$). The number of columns in $A$ must equal the number of rows in $B$.

$$C_{ij} = \sum_{k=1}^{n} A_{ik}B_{kj}$$

**Variables:**

- $C_{ij}$: The element in the $i$-th row and $j$-th column of the product matrix.
    
- $A_{ik}$: Element of the first matrix.
    
- $B_{kj}$: Element of the second matrix.
    

**Geometric Significance:** Matrices act as linear transformations on vectors (e.g., rotations, scaling, shearing). Multiplying two matrices is geometrically equivalent to composing two consecutive linear transformations.

_Note: Matrix multiplication is strictly NON-commutative ($AB \neq BA$ in general)._

## [[Matrix Inverses]]

For a square $n \times n$ matrix $A$, if there exists an $n \times n$ matrix $B$ such that:

$$AB = BA = I_n$$

(where $I_n$ is the Identity Matrix with $1$s on the diagonal and $0$s elsewhere), then $A$ is invertible, and $B$ is the **inverse** of $A$, denoted as $A^{-1}$.

### Inverse of a 2x2 Matrix

For a $2 \times 2$ matrix $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$, the inverse is defined as:

$$A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$$

If $(ad - bc) = 0$, the matrix is non-invertible (singular).

### The [[Invertible Matrix Theorem]]

This theorem connects several fundamental concepts. For an $n \times n$ square matrix $A$, the following statements are logically equivalent:

1. $A$ is an invertible matrix.
    
2. The equation $Ax = 0$ has only the trivial solution $x = 0$.
    
3. The RREF of $A$ is the identity matrix $I_n$.
    
4. The columns of $A$ form a linearly independent set.
    
5. The equation $Ax = b$ has at least one solution for each $b$ in $\mathbb{R}^n$.
    
6. The determinant of $A$ is not zero ($\det(A) \neq 0$).
    

## [[Determinants]]

The [[Determinant]] is a scalar value calculated from the elements of a square matrix.

**Geometric Significance:** The determinant represents the **volume scaling factor** of the linear transformation described by the matrix.

- If $\det(A) = 2$, the transformation doubles the area (in 2D) or volume (in 3D) of any shape.
    
- If $\det(A) = 0$, it squishes the space into a lower dimension (e.g., flattening a 3D space into a 2D plane), which is why a matrix with a zero determinant cannot be inverted (information is lost).
    
- A negative determinant indicates a reversal of orientation (e.g., flipping space inside out).
    

### [[Cofactor Expansion]]

To find the determinant of larger matrices ($3 \times 3$ and above), we use cofactor expansion along any row or column.

The cofactor $C_{ij}$ is defined as:

$$C_{ij} = (-1)^{i+j} \det(M_{ij})$$

Where $M_{ij}$ is the **minor** matrix formed by deleting the $i$-th row and $j$-th column of $A$.

The determinant of $A$ (expanded along the $i$-th row) is:

$$\det(A) = \sum_{j=1}^{n} A_{ij} C_{ij}$$

### [[Cramer's Rule]]

[[Cramer's Rule]] provides an explicit formula for the solution of a system of linear equations with as many equations as unknowns, provided the system has a unique solution ($\det(A) \neq 0$).

For the system $Ax = b$:

$$x_i = \frac{\det(A_i)}{\det(A)}$$

**Variables:**

- $x_i$: The $i$-th unknown variable.
    
- $\det(A)$: Determinant of the original coefficient matrix.
    
- $\det(A_i)$: Determinant of the matrix formed by replacing the $i$-th column of $A$ with the column vector $b$.
    

## [[Solved Examples]]

### Example 1: Solving a 3x3 System using Row Reduction

**Problem:** Solve the following system:

$x + 2y + z = 5$

$2x + 5y + 3z = 13$

$x + y + 2z = 6$

**Solution:**

1. Write the augmented matrix:
    
    $$\begin{bmatrix} 1 & 2 & 1 & \vert{} & 5 \\ 2 & 5 & 3 & \vert{} & 13 \\ 1 & 1 & 2 & \vert{} & 6 \end{bmatrix}$$
    
2. $R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$:
    
    $$\begin{bmatrix} 1 & 2 & 1 & \vert{} & 5 \\ 0 & 1 & 1 & \vert{} & 3 \\ 0 & -1 & 1 & \vert{} & 1 \end{bmatrix}$$
    
3. $R_3 \leftarrow R_3 + R_2$:
    
    $$\begin{bmatrix} 1 & 2 & 1 & \vert{} & 5 \\ 0 & 1 & 1 & \vert{} & 3 \\ 0 & 0 & 2 & \vert{} & 4 \end{bmatrix}$$
    
4. Scale $R_3 \leftarrow \frac{1}{2}R_3$:
    
    $$\begin{bmatrix} 1 & 2 & 1 & \vert{} & 5 \\ 0 & 1 & 1 & \vert{} & 3 \\ 0 & 0 & 1 & \vert{} & 2 \end{bmatrix}$$
    
5. Back substitution:
    
    $z = 2$
    
    $y + (2) = 3 \implies y = 1$
    
    $x + 2(1) + (2) = 5 \implies x = 1$
    

**Answer:** The unique solution is $x=1, y=1, z=2$.

### Example 2: Matrix Multiplication

**Problem:** Multiply $A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$ and $B = \begin{bmatrix} 2 & 0 \\ 1 & 5 \end{bmatrix}$.

**Solution:**

$$C = AB = \begin{bmatrix} (1)(2) + (2)(1) & (1)(0) + (2)(5) \\ (3)(2) + (4)(1) & (3)(0) + (4)(5) \end{bmatrix}$$

$$C = \begin{bmatrix} 4 & 10 \\ 10 & 20 \end{bmatrix}$$

### Example 3: Determinant via Cofactor Expansion

**Problem:** Evaluate the determinant of $A = \begin{bmatrix} 2 & -1 & 3 \\ 0 & 4 & 1 \\ 5 & 0 & -2 \end{bmatrix}$.

**Solution:**

Expand along the first column (because it has a zero):

$$\det(A) = 2 \det\begin{bmatrix} 4 & 1 \\ 0 & -2 \end{bmatrix} - 0 \det\begin{bmatrix} -1 & 3 \\ 0 & -2 \end{bmatrix} + 5 \det\begin{bmatrix} -1 & 3 \\ 4 & 1 \end{bmatrix}$$

$$\det(A) = 2( (4)(-2) - (1)(0) ) - 0 + 5( (-1)(1) - (3)(4) )$$

$$\det(A) = 2(-8) + 5(-1 - 12)$$

$$\det(A) = -16 + 5(-13) = -16 - 65 = -81$$

# [[Formula Sheet]]

- **2x2 Inverse:** $A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$
    
- **Determinant of 2x2:** $\det(A) = ad - bc$
    
- **Cofactor:** $C_{ij} = (-1)^{i+j} \det(M_{ij})$
    
- **Matrix Product Element:** $C_{ij} = \sum_{k=1}^{n} A_{ik}B_{kj}$
    
- **Cramer's Rule:** $x_i = \frac{\det(A_i)}{\det(A)}$
    
- **Properties of Transpose:** $(AB)^T = B^TA^T$
    
- **Properties of Inverse:** $(AB)^{-1} = B^{-1}A^{-1}$
    

# [[Problem Solving Strategy]]

1. **For Systems of Equations:** Always write the system as an augmented matrix. Use Gaussian elimination to systematically create zeros below the main diagonal from left to right. Avoid fractions until the very last step if possible by swapping rows or scaling.
    
2. **For Matrix Operations:** Check dimensions first. You can only multiply an $m \times n$ matrix by an $n \times p$ matrix. The inner dimensions must match, and the result is $m \times p$.
    
3. **For Determinants:** Before doing raw calculation, look for a row or column with the most zeros to minimize computations. Remember the alternating sign pattern $+ - +$ for cofactor expansion. If a matrix is triangular (upper or lower), its determinant is simply the product of its main diagonal entries.
    
4. **For Inverses:** Check the determinant first. If $\det(A) = 0$, stop immediately—the inverse does not exist.
    

# [[Common Mistakes]]

- **Assuming $AB = BA$:** Matrix multiplication is fundamentally not commutative. Never assume the order of multiplication doesn't matter.
    
- **Distributing Inverses Incorrectly:** $(A+B)^{-1} \neq A^{-1} + B^{-1}$. Furthermore, $(AB)^{-1} = B^{-1}A^{-1}$ (the order reverses).
    
- **Losing Track of Signs in Determinants:** When applying cofactor expansion, the checkerboard sign pattern $(-1)^{i+j}$ dictates whether to add or subtract the minor determinant. Forgetting to apply this sign is the most frequent error.
    
- **Row Reduction Arithmetic:** Performing elementary row operations in your head often leads to dropped minus signs. Always write down the operation (e.g., $R_2 - 3R_1 \rightarrow R_2$) explicitly.
    

# [[Applications]]

- **Computer Graphics:** Matrices are used to transform 3D coordinates into 2D screens. Rotations, translations, and scaling of virtual objects are all accomplished via matrix multiplication.
    
- **Circuit Analysis:** [[Kirchhoff's Laws]] yield systems of linear equations to solve for unknown currents or node voltages in complex electrical networks, easily solved via [[Row Reduction]] or [[Cramer's Rule]].
    
- **Structural Engineering:** Used in Finite Element Analysis (FEA) to map the stiffness and stress of thousands of interconnected nodes on a bridge or building structure.
    
- **Machine Learning & AI:** Neural networks rely heavily on matrix algebra. A "layer" in a neural network is essentially a matrix of weights multiplied by an input vector, passed through an activation function.
    

# [[Summary]]

[[Linear Systems and Matrix Algebra]] provide the foundational language for multidimensional mathematics. By abstracting systems of linear equations into matrices, we can solve them systematically using [[Row Reduction]] to reach [[Echelon Forms]]. [[Matrix Algebra]] governs how these structures interact, revealing non-commutative properties unique to multidimensional space. Tools like the [[Determinant]] and [[Matrix Inverses]] allow us to understand the geometric scaling and reversibility of transformations, ultimately culminating in the [[Invertible Matrix Theorem]] which unifies these concepts. These principles form the bedrock of modern computational algorithms, physics engines, and engineering analyses.

# [[Related Notes]]

- [[Vector Spaces]]
    
- [[Eigenvalues and Eigenvectors]]
    
- [[Linear Transformations]]
    
- [[Calculus of Variations]]
    
- [[Circuit Theory]]
    
- [[Differential Equations]]