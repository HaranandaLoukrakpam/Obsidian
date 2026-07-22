# NumPy

## Definition

**NumPy** (Numerical Python) is an open-source [[Python]] library used for **numerical computing**. It provides support for large, multi-dimensional arrays and matrices, along with a wide range of mathematical functions to perform fast and efficient numerical operations.

NumPy is the foundation of many scientific computing and [[Data Science]] libraries, including [[Pandas]], [[Scikit-learn]], [[TensorFlow]], and [[PyTorch]].

---

## Key Features

- Fast numerical computations.
- Multi-dimensional array support.
- Efficient memory usage.
- Mathematical and statistical functions.
- Linear algebra operations.
- Random number generation.
- Array broadcasting.
- Shape manipulation.
- Integration with other Python libraries.

---

## Installation

Install NumPy using **pip**:

```bash
pip install numpy
```

Import NumPy in Python:

```python
import numpy as np
```

The alias **`np`** is the standard convention.

---

## Why Use NumPy?

NumPy is designed to:

- Perform numerical calculations efficiently.
- Handle large datasets with high performance.
- Replace slower Python lists for mathematical operations.
- Provide the foundation for [[Machine Learning]] and [[Deep Learning]] computations.
- Simplify scientific and engineering calculations.

---

## Core Data Structure

### [[ndarray]]

The primary data structure in NumPy is the **ndarray (N-dimensional Array)**.

An ndarray stores elements of the same data type in a fixed-size, efficient array.

Example:

```python
import numpy as np

arr = np.array([10, 20, 30, 40])

print(arr)
```

Output:

```
[10 20 30 40]
```

---

## Creating Arrays

### One-Dimensional Array

```python
arr = np.array([1, 2, 3, 4])
```

---

### Two-Dimensional Array

```python
arr = np.array([
    [1, 2],
    [3, 4]
])
```

---

### Three-Dimensional Array

```python
arr = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
```

---

## Special Arrays

### Zeros

```python
np.zeros((3,3))
```

Creates a 3 × 3 array of zeros.

---

### Ones

```python
np.ones((2,4))
```

Creates a 2 × 4 array of ones.

---

### Identity Matrix

```python
np.eye(3)
```

Creates a 3 × 3 identity matrix.

---

### Range

```python
np.arange(0,10,2)
```

Output:

```
[0 2 4 6 8]
```

---

### Evenly Spaced Numbers

```python
np.linspace(0,1,5)
```

Output:

```
[0.00 0.25 0.50 0.75 1.00]
```

---

## Array Attributes

Example:

```python
arr = np.array([[1,2],[3,4]])
```

Shape:

```python
arr.shape
```

Output:

```
(2,2)
```

---

Dimensions:

```python
arr.ndim
```

---

Size:

```python
arr.size
```

---

Data Type:

```python
arr.dtype
```

---

## Array Operations

Addition

```python
a + b
```

Subtraction

```python
a - b
```

Multiplication

```python
a * b
```

Division

```python
a / b
```

Power

```python
a ** 2
```

Square Root

```python
np.sqrt(a)
```

---

## Mathematical Functions

Mean

```python
np.mean(arr)
```

Sum

```python
np.sum(arr)
```

Maximum

```python
np.max(arr)
```

Minimum

```python
np.min(arr)
```

Standard Deviation

```python
np.std(arr)
```

Variance

```python
np.var(arr)
```

---

## Indexing and Slicing

Example:

```python
arr = np.array([10,20,30,40,50])
```

First element

```python
arr[0]
```

Last element

```python
arr[-1]
```

Slice

```python
arr[1:4]
```

Output

```
[20 30 40]
```

---

## Reshaping Arrays

Example:

```python
arr = np.arange(12)

arr.reshape(3,4)
```

Output

```
[[0 1 2 3]
 [4 5 6 7]
 [8 9 10 11]]
```

---

## Broadcasting

Broadcasting allows arrays with different shapes to perform arithmetic operations automatically.

Example:

```python
arr = np.array([1,2,3])

arr + 5
```

Output

```
[6 7 8]
```

---

## Random Module

Random integers

```python
np.random.randint(1,10,size=5)
```

Random decimal numbers

```python
np.random.rand(3)
```

Random normal distribution

```python
np.random.randn(3)
```

---

## Linear Algebra

Matrix Multiplication

```python
np.dot(a,b)
```

Transpose

```python
arr.T
```

Inverse

```python
np.linalg.inv(matrix)
```

Determinant

```python
np.linalg.det(matrix)
```

Eigenvalues

```python
np.linalg.eig(matrix)
```

---

## Advantages

- Extremely fast compared to Python lists.
- Efficient memory management.
- Powerful mathematical operations.
- Supports multi-dimensional arrays.
- Widely used in scientific computing.
- Forms the foundation of many AI and ML libraries.

---

## Limitations

- Arrays store elements of the same data type.
- Less suitable for heterogeneous tabular data (use [[Pandas]] instead).
- Large arrays can consume significant memory.

---

## Applications

- [[Data Science]]
- [[Machine Learning]]
- [[Deep Learning]]
- Scientific computing
- Engineering simulations
- Image processing
- Signal processing
- Financial analysis
- Statistical analysis

---

## NumPy vs Python Lists

| Python List | NumPy Array |
|-------------|-------------|
| Slower | Faster |
| More memory usage | Memory efficient |
| Supports mixed data types | Stores one data type |
| Limited mathematical operations | Rich mathematical functions |
| Best for general-purpose programming | Best for numerical computing |

---

## Integration with Other Libraries

NumPy works seamlessly with:

- [[Pandas]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Scikit-learn]]
- [[SciPy]]
- [[TensorFlow]]
- [[PyTorch]]

---

## Real-World Examples

- Scientific calculations.
- Data preprocessing.
- Machine Learning model training.
- Image and signal processing.
- Financial modeling.
- Weather forecasting.
- Engineering simulations.
- Statistical analysis.

---

## Common NumPy Functions

| Function | Purpose |
|----------|---------|
| `np.array()` | Create an array |
| `np.zeros()` | Array of zeros |
| `np.ones()` | Array of ones |
| `np.eye()` | Identity matrix |
| `np.arange()` | Create evenly spaced values |
| `np.linspace()` | Create evenly spaced numbers |
| `np.reshape()` | Change array shape |
| `np.mean()` | Calculate mean |
| `np.sum()` | Calculate sum |
| `np.max()` | Find maximum value |
| `np.min()` | Find minimum value |
| `np.sqrt()` | Calculate square root |
| `np.dot()` | Matrix multiplication |
| `np.random.rand()` | Random decimal numbers |
| `np.random.randint()` | Random integers |

---

## Related Notes

- [[Python]]
- [[Pandas]]
- [[ndarray]]
- [[Data Science]]
- [[Data Analysis]]
- [[Machine Learning]]
- [[Deep Learning]]
- [[Artificial Intelligence]]
- [[Linear Algebra]]
- [[Matrix]]
- [[Broadcasting]]
- [[Matplotlib]]
- [[Seaborn]]
- [[Scikit-learn]]
- [[SciPy]]
- [[TensorFlow]]
- [[PyTorch]]