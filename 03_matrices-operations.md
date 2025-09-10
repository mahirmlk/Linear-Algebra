# Matrix Operations

## Overview

Matrix operations are fundamental procedures that allow us to manipulate and combine matrices. These operations form the foundation of linear algebra and have extensive applications in mathematics, physics, computer science, and engineering.

## 1. Matrix Addition and Subtraction

### Matrix Addition

Two matrices can be added if and only if they have the same dimensions.

**Definition:** If $A = [a_{ij}]_{m \times n}$ and $B = [b_{ij}]_{m \times n}$, then:
$$A + B = [a_{ij} + b_{ij}]_{m \times n}$$

**Examples:**

**Basic Addition:**
$$\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{pmatrix} + \begin{pmatrix}
7 & 8 & 9 \\
10 & 11 & 12
\end{pmatrix} = \begin{pmatrix}
8 & 10 & 12 \\
14 & 16 & 18
\end{pmatrix}$$

**With Negative Elements:**
$$\begin{pmatrix}
2 & -3 \\
1 & 4
\end{pmatrix} + \begin{pmatrix}
-1 & 5 \\
2 & -2
\end{pmatrix} = \begin{pmatrix}
1 & 2 \\
3 & 2
\end{pmatrix}$$

### Matrix Subtraction

**Definition:** If $A = [a_{ij}]_{m \times n}$ and $B = [b_{ij}]_{m \times n}$, then:
$$A - B = [a_{ij} - b_{ij}]_{m \times n}$$

**Example:**
$$\begin{pmatrix}
5 & 8 & 2 \\
3 & 1 & 6
\end{pmatrix} - \begin{pmatrix}
2 & 3 & 1 \\
1 & 0 & 4
\end{pmatrix} = \begin{pmatrix}
3 & 5 & 1 \\
2 & 1 & 2
\end{pmatrix}$$

### Properties of Addition and Subtraction

1. **Commutative Property:** $A + B = B + A$
2. **Associative Property:** $(A + B) + C = A + (B + C)$
3. **Identity Element:** $A + O = O + A = A$ (where $O$ is the zero matrix)
4. **Additive Inverse:** $A + (-A) = O$

## 2. Scalar Multiplication

Multiplying a matrix by a scalar (real number) multiplies every element by that scalar.

**Definition:** If $A = [a_{ij}]_{m \times n}$ and $k$ is a scalar, then:
$$kA = [ka_{ij}]_{m \times n}$$

**Examples:**

**Positive Scalar:**
$$3 \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix} = \begin{pmatrix}
3 & 6 \\
9 & 12
\end{pmatrix}$$

**Negative Scalar:**
$$-2 \begin{pmatrix}
1 & -3 & 2 \\
0 & 4 & -1
\end{pmatrix} = \begin{pmatrix}
-2 & 6 & -4 \\
0 & -8 & 2
\end{pmatrix}$$

**Fractional Scalar:**
$$\frac{1}{2} \begin{pmatrix}
4 & 6 \\
8 & 10
\end{pmatrix} = \begin{pmatrix}
2 & 3 \\
4 & 5
\end{pmatrix}$$

### Properties of Scalar Multiplication

1. **Associativity:** $(kl)A = k(lA)$
2. **Distributivity over Matrix Addition:** $k(A + B) = kA + kB$
3. **Distributivity over Scalar Addition:** $(k + l)A = kA + lA$
4. **Identity:** $1 \cdot A = A$

## 3. Matrix Multiplication

Matrix multiplication is more complex and requires specific dimensional compatibility.

### Condition for Multiplication

Matrices $A_{m \times p}$ and $B_{p \times n}$ can be multiplied if the number of columns in $A$ equals the number of rows in $B$.

**Result:** The product $AB$ is an $m \times n$ matrix.

### Definition of Matrix Multiplication

If $A = [a_{ij}]_{m \times p}$ and $B = [b_{ij}]_{p \times n}$, then $C = AB = [c_{ij}]_{m \times n}$ where:

$$c_{ij} = \sum_{k=1}^{p} a_{ik}b_{kj} = a_{i1}b_{1j} + a_{i2}b_{2j} + \cdots + a_{ip}b_{pj}$$

### Step-by-Step Examples

**Example 1: 2×2 matrices**
$$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}, \quad B = \begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}$$

$$AB = \begin{pmatrix}
1 \cdot 5 + 2 \cdot 7 & 1 \cdot 6 + 2 \cdot 8 \\
3 \cdot 5 + 4 \cdot 7 & 3 \cdot 6 + 4 \cdot 8
\end{pmatrix} = \begin{pmatrix}
19 & 22 \\
43 & 50
\end{pmatrix}$$

**Example 2: Non-square matrices**
$$A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{pmatrix}_{2 \times 3}, \quad B = \begin{pmatrix}
7 & 8 \\
9 & 10 \\
11 & 12
\end{pmatrix}_{3 \times 2}$$

$$AB = \begin{pmatrix}
1 \cdot 7 + 2 \cdot 9 + 3 \cdot 11 & 1 \cdot 8 + 2 \cdot 10 + 3 \cdot 12 \\
4 \cdot 7 + 5 \cdot 9 + 6 \cdot 11 & 4 \cdot 8 + 5 \cdot 10 + 6 \cdot 12
\end{pmatrix}$$

$$AB = \begin{pmatrix}
58 & 64 \\
139 & 154
\end{pmatrix}_{2 \times 2}$$

**Example 3: Matrix-Vector multiplication**
$$A = \begin{pmatrix}
2 & 1 & 3 \\
1 & 0 & 2
\end{pmatrix}, \quad \mathbf{x} = \begin{pmatrix}
1 \\
2 \\
3
\end{pmatrix}$$

$$A\mathbf{x} = \begin{pmatrix}
2 \cdot 1 + 1 \cdot 2 + 3 \cdot 3 \\
1 \cdot 1 + 0 \cdot 2 + 2 \cdot 3
\end{pmatrix} = \begin{pmatrix}
13 \\
7
\end{pmatrix}$$

### Properties of Matrix Multiplication

1. **Associativity:** $(AB)C = A(BC)$
2. **Distributivity over Addition:** 
   - $A(B + C) = AB + AC$ (right distributive)
   - $(A + B)C = AC + BC$ (left distributive)
3. **Scalar Associativity:** $k(AB) = (kA)B = A(kB)$
4. **Identity Element:** $AI = IA = A$ (for square matrices)
5. **Generally NOT Commutative:** $AB \neq BA$ (in general)

### Non-Commutativity Example

$$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}, \quad B = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}$$

$$AB = \begin{pmatrix}
2 & 1 \\
4 & 3
\end{pmatrix}, \quad BA = \begin{pmatrix}
3 & 4 \\
1 & 2
\end{pmatrix}$$

Since $AB \neq BA$, matrix multiplication is not commutative.

## 4. Matrix Transpose

The transpose of a matrix interchanges its rows and columns.

**Definition:** If $A = [a_{ij}]_{m \times n}$, then $A^T = [a_{ji}]_{n \times m}$

### Examples

**Basic Transpose:**
$A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{pmatrix} \Rightarrow A^T = \begin{pmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{pmatrix}$

**Square Matrix Transpose:**
$B = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix} \Rightarrow B^T = \begin{pmatrix}
1 & 4 & 7 \\
2 & 5 & 8 \\
3 & 6 & 9
\end{pmatrix}$

**Column Vector Transpose:**
$\mathbf{v} = \begin{pmatrix}
a \\
b \\
c
\end{pmatrix} \Rightarrow \mathbf{v}^T = \begin{pmatrix}
a & b & c
\end{pmatrix}$

### Properties of Transpose

1. **Double Transpose:** $(A^T)^T = A$
2. **Addition:** $(A + B)^T = A^T + B^T$
3. **Scalar Multiplication:** $(kA)^T = kA^T$
4. **Multiplication:** $(AB)^T = B^T A^T$ (note the order reversal)
5. **Inverse:** $(A^{-1})^T = (A^T)^{-1}$

### Transpose Multiplication Example

$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}, \quad B = \begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}$

$AB = \begin{pmatrix}
19 & 22 \\
43 & 50
\end{pmatrix}$

$(AB)^T = \begin{pmatrix}
19 & 43 \\
22 & 50
\end{pmatrix}$

$B^T A^T = \begin{pmatrix}
5 & 7 \\
6 & 8
\end{pmatrix} \begin{pmatrix}
1 & 3 \\
2 & 4
\end{pmatrix} = \begin{pmatrix}
19 & 43 \\
22 & 50
\end{pmatrix}$

Indeed, $(AB)^T = B^T A^T$.

## 5. Matrix Powers

For a square matrix $A$, we can define powers:

**Definition:**
- $A^0 = I$ (identity matrix)
- $A^1 = A$
- $A^n = A \cdot A \cdot \ldots \cdot A$ ($n$ times for $n > 1$)

### Examples

**Power of 2:**
$A = \begin{pmatrix}
2 & 1 \\
0 & 3
\end{pmatrix}$

$A^2 = \begin{pmatrix}
2 & 1 \\
0 & 3
\end{pmatrix} \begin{pmatrix}
2 & 1 \\
0 & 3
\end{pmatrix} = \begin{pmatrix}
4 & 5 \\
0 & 9
\end{pmatrix}$

**Diagonal Matrix Powers:**
$D = \begin{pmatrix}
3 & 0 & 0 \\
0 & -2 & 0 \\
0 & 0 & 4
\end{pmatrix}$

$D^3 = \begin{pmatrix}
27 & 0 & 0 \\
0 & -8 & 0 \\
0 & 0 & 64
\end{pmatrix}$

## 6. Trace of a Matrix

The trace is the sum of diagonal elements of a square matrix.

**Definition:** For $A = [a_{ij}]_{n \times n}$:
$\text{tr}(A) = \sum_{i=1}^{n} a_{ii} = a_{11} + a_{22} + \cdots + a_{nn}$

### Examples

$A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix} \Rightarrow \text{tr}(A) = 1 + 5 + 9 = 15$

$B = \begin{pmatrix}
-2 & 5 \\
1 & 3
\end{pmatrix} \Rightarrow \text{tr}(B) = -2 + 3 = 1$

### Properties of Trace

1. **Linearity:** $\text{tr}(A + B) = \text{tr}(A) + \text{tr}(B)$
2. **Scalar Multiplication:** $\text{tr}(kA) = k \cdot \text{tr}(A)$
3. **Transpose:** $\text{tr}(A^T) = \text{tr}(A)$
4. **Cyclic Property:** $\text{tr}(AB) = \text{tr}(BA)$
5. **Similarity Invariant:** If $B = P^{-1}AP$, then $\text{tr}(B) = \text{tr}(A)$

## 7. Block Matrix Operations

Matrices can be partitioned into blocks for easier computation.

### Block Addition

$\begin{pmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22}
\end{pmatrix} + \begin{pmatrix}
B_{11} & B_{12} \\
B_{21} & B_{22}
\end{pmatrix} = \begin{pmatrix}
A_{11}+B_{11} & A_{12}+B_{12} \\
A_{21}+B_{21} & A_{22}+B_{22}
\end{pmatrix}$

### Block Multiplication

$\begin{pmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22}
\end{pmatrix} \begin{pmatrix}
B_{11} & B_{12} \\
B_{21} & B_{22}
\end{pmatrix} = \begin{pmatrix}
A_{11}B_{11}+A_{12}B_{21} & A_{11}B_{12}+A_{12}B_{22} \\
A_{21}B_{11}+A_{22}B_{21} & A_{21}B_{12}+A_{22}B_{22}
\end{pmatrix}$

### Example

$A = \begin{pmatrix}
1 & 2 & | & 3 & 0 \\
4 & 5 & | & 6 & 1 \\
\hline
7 & 8 & | & 9 & 2 \\
\end{pmatrix} = \begin{pmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22}
\end{pmatrix}$

Where:
$A_{11} = \begin{pmatrix} 1 & 2 \\ 4 & 5 \end{pmatrix}, \quad A_{12} = \begin{pmatrix} 3 & 0 \\ 6 & 1 \end{pmatrix}$
$A_{21} = \begin{pmatrix} 7 & 8 \end{pmatrix}, \quad A_{22} = \begin{pmatrix} 9 & 2 \end{pmatrix}$

## 8. Kronecker Product

The Kronecker product (tensor product) creates larger matrices from smaller ones.

**Definition:** If $A$ is $m \times n$ and $B$ is $p \times q$, then $A \otimes B$ is $mp \times nq$:

$A \otimes B = \begin{pmatrix}
a_{11}B & a_{12}B & \cdots & a_{1n}B \\
a_{21}B & a_{22}B & \cdots & a_{2n}B \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1}B & a_{m2}B & \cdots & a_{mn}B
\end{pmatrix}$

### Example

$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}, \quad B = \begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}$

$A \otimes B = \begin{pmatrix}
1 \cdot \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} & 2 \cdot \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} \\
3 \cdot \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} & 4 \cdot \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}
\end{pmatrix} = \begin{pmatrix}
5 & 6 & 10 & 12 \\
7 & 8 & 14 & 16 \\
15 & 18 & 20 & 24 \\
21 & 24 & 28 & 32
\end{pmatrix}$

## 9. Hadamard Product (Element-wise)

The Hadamard product multiplies corresponding elements.

**Definition:** If $A = [a_{ij}]$ and $B = [b_{ij}]$ have the same dimensions:
$A \circ B = [a_{ij} \cdot b_{ij}]$

### Example

$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}, \quad B = \begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}$

$A \circ B = \begin{pmatrix}
1 \cdot 5 & 2 \cdot 6 \\
3 \cdot 7 & 4 \cdot 8
\end{pmatrix} = \begin{pmatrix}
5 & 12 \\
21 & 32
\end{pmatrix}$

## 10. Common Operation Combinations

### Matrix-Vector Products in Systems

Linear system $A\mathbf{x} = \mathbf{b}$:
$\begin{pmatrix}
2 & 1 & -1 \\
1 & 3 & 2 \\
-1 & 2 & 1
\end{pmatrix} \begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix} = \begin{pmatrix}
1 \\
2 \\
3
\end{pmatrix}$

### Quadratic Forms

$\mathbf{x}^T A \mathbf{x} = \begin{pmatrix} x_1 & x_2 \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = ax_1^2 + (b+c)x_1x_2 + dx_2^2$

## Summary

Matrix operations provide the computational foundation for linear algebra. Key points:

- **Addition/Subtraction**: Requires same dimensions, performed element-wise
- **Scalar Multiplication**: Multiplies every element by the scalar
- **Matrix Multiplication**: Requires compatible dimensions, not commutative
- **Transpose**: Interchanges rows and columns, reverses order in products
- **Trace**: Sum of diagonal elements, has useful properties
- **Block Operations**: Partition matrices for efficient computation

Understanding these operations and their properties is essential for solving linear systems, transformations, eigenvalue problems, and applications across science and engineering.