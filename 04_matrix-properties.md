# Matrix Properties and Mathematical Formulations

## Overview

Matrix properties are fundamental characteristics that govern how matrices behave under various operations. Understanding these properties is crucial for theoretical development and practical applications in linear algebra.

## 1. Fundamental Properties of Matrix Operations

### Addition Properties

**Commutative Property**
$$A + B = B + A$$

**Proof concept:** Since addition is performed element-wise and real number addition is commutative:
$$(A + B)_{ij} = a_{ij} + b_{ij} = b_{ij} + a_{ij} = (B + A)_{ij}$$

**Associative Property**
$$(A + B) + C = A + (B + C)$$

**Identity Element**
$$A + O = O + A = A$$
where $O$ is the zero matrix of appropriate dimensions.

**Additive Inverse**
$$A + (-A) = O$$
where $-A = (-1) \cdot A$.

**Example:**
$$A = \begin{pmatrix} 3 & -1 \\ 2 & 4 \end{pmatrix}, \quad -A = \begin{pmatrix} -3 & 1 \\ -2 & -4 \end{pmatrix}$$
$$A + (-A) = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = O$$

### Scalar Multiplication Properties

**Associativity with Scalars**
$$(kl)A = k(lA)$$

**Distributivity over Matrix Addition**
$$k(A + B) = kA + kB$$

**Distributivity over Scalar Addition**
$$(k + l)A = kA + lA$$

**Multiplicative Identity**
$$1 \cdot A = A$$

**Example:**
$$A = \begin{pmatrix} 2 & 3 \\ 1 & 4 \end{pmatrix}$$
$$3(2A) = 3 \begin{pmatrix} 4 & 6 \\ 2 & 8 \end{pmatrix} = \begin{pmatrix} 12 & 18 \\ 6 & 24 \end{pmatrix}$$
$$(3 \cdot 2)A = 6A = \begin{pmatrix} 12 & 18 \\ 6 & 24 \end{pmatrix}$$

### Matrix Multiplication Properties

**Associative Property**
$$(AB)C = A(BC)$$

**Proof outline:** Both sides equal $\sum_{j,k} a_{ij}b_{jk}c_{kl}$.

**Distributive Properties**
- Right distributive: $A(B + C) = AB + AC$
- Left distributive: $(A + B)C = AC + BC$

**Identity Element**
$$AI = IA = A$$
for square matrices where $I$ is the identity matrix.

**Generally NOT Commutative**
$$AB \neq BA \quad \text{(in general)}$$

**Zero Property**
$$AO = OA = O$$
where $O$ is the zero matrix of appropriate dimensions.

**Example of Non-Commutativity:**
$$A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}$$

$$AB = \begin{pmatrix} 3 & 2 \\ 1 & 1 \end{pmatrix}, \quad BA = \begin{pmatrix} 1 & 2 \\ 1 & 3 \end{pmatrix}$$

Since $AB \neq BA$, multiplication is not commutative.

## 2. Transpose Properties

### Basic Transpose Properties

**Double Transpose**
$$(A^T)^T = A$$

**Addition**
$$(A + B)^T = A^T + B^T$$

**Scalar Multiplication**
$$(kA)^T = kA^T$$

**Multiplication (Order Reversal)**
$$(AB)^T = B^T A^T$$

**Proof of $(AB)^T = B^T A^T$:**
$$((AB)^T)_{ij} = (AB)_{ji} = \sum_k a_{jk}b_{ki} = \sum_k b_{ki}a_{jk} = (B^T A^T)_{ij}$$

**Power Rule**
$$(A^n)^T = (A^T)^n$$

### Matrix Types and Transpose

**Symmetric Matrix**
$$A^T = A \quad \text{(i.e., } a_{ij} = a_{ji} \text{)}$$

**Skew-Symmetric Matrix**
$$A^T = -A \quad \text{(i.e., } a_{ij} = -a_{ji} \text{)}$$

**Orthogonal Matrix**
$$A^T A = AA^T = I$$

## 3. Properties of Special Matrices

### Identity Matrix Properties

**Definition:** $I_n = [δ_{ij}]$ where $δ_{ij} = \begin{cases} 1 & \text{if } i = j \\ 0 & \text{if } i \neq j \end{cases}$

**Properties:**
- $AI = IA = A$ (multiplicative identity)
- $I^n = I$ for any positive integer $n$
- $I^T = I$ (symmetric)
- $\det(I) = 1$
- All eigenvalues equal 1

### Diagonal Matrix Properties

For diagonal matrix $D = \text{diag}(d_1, d_2, \ldots, d_n)$:

**Powers:** $D^k = \text{diag}(d_1^k, d_2^k, \ldots, d_n^k)$

**Determinant:** $\det(D) = \prod_{i=1}^n d_i$

**Inverse:** $D^{-1} = \text{diag}(d_1^{-1}, d_2^{-1}, \ldots, d_n^{-1})$ (if all $d_i \neq 0$)

**Commutativity:** Two diagonal matrices always commute

### Triangular Matrix Properties

**Upper Triangular Matrix $U$:**
- $\det(U) = \prod_{i=1}^n u_{ii}$ (product of diagonal elements)
- Product of upper triangular matrices is upper triangular
- $(U_1 U_2)_{ij} = 0$ for $i > j$

**Lower Triangular Matrix $L$:**
- Similar properties to upper triangular
- Transpose of upper triangular is lower triangular: $(U^T)$ is lower triangular

## 4. Trace Properties and Formulations

### Definition and Basic Properties

**Definition:** $\text{tr}(A) = \sum_{i=1}^n a_{ii}$

**Linearity:**
$$\text{tr}(A + B) = \text{tr}(A) + \text{tr}(B)$$
$$\text{tr}(kA) = k \cdot \text{tr}(A)$$

**Transpose Invariance:**
$$\text{tr}(A^T) = \text{tr}(A)$$

**Cyclic Property (Most Important):**
$$\text{tr}(AB) = \text{tr}(BA)$$

**Proof of Cyclic Property:**
$$\text{tr}(AB) = \sum_i (AB)_{ii} = \sum_i \sum_j a_{ij}b_{ji} = \sum_j \sum_i b_{ji}a_{ij} = \sum_j (BA)_{jj} = \text{tr}(BA)$$

**Extended Cyclic Property:**
$$\text{tr}(ABC) = \text{tr}(BCA) = \text{tr}(CAB)$$

### Trace and Eigenvalues

For a matrix with eigenvalues $λ_1, λ_2, \ldots, λ_n$:
$$\text{tr}(A) = \sum_{i=1}^n λ_i$$

**Example:**
$$A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$$
- Eigenvalues: $λ_1 = 3, λ_2 = 2$
- $\text{tr}(A) = 3 + 2 = 5 = λ_1 + λ_2$

## 5. Rank Properties

### Definition and Basic Properties

**Rank:** The maximum number of linearly independent rows (or columns).

**Properties:**
- $\text{rank}(A) = \text{rank}(A^T)$
- $\text{rank}(AB) \leq \min(\text{rank}(A), \text{rank}(B))$
- $\text{rank}(A + B) \leq \text{rank}(A) + \text{rank}(B)$
- $\text{rank}(kA) = \text{rank}(A)$ for $k \neq 0$

### Full Rank Matrices

**Full Row Rank:** $\text{rank}(A) = m$ for $m \times n$ matrix
**Full Column Rank:** $\text{rank}(A) = n$ for $m \times n$ matrix
**Full Rank (Square):** $\text{rank}(A) = n$ for $n \times n$ matrix

## 6. Invertibility Properties

### Conditions for Invertibility

A square matrix $A$ is invertible if and only if:
1. $\det(A) \neq 0$
2. $\text{rank}(A) = n$
3. All eigenvalues are non-zero
4. The columns (rows) are linearly independent
5. $A\mathbf{x} = \mathbf{0}$ has only the trivial solution

### Properties of Matrix Inverse

**Uniqueness:** If $A^{-1}$ exists, it is unique.

**Inverse of Inverse:** $(A^{-1})^{-1} = A$

**Inverse of Product:** $(AB)^{-1} = B^{-1}A^{-1}$

**Inverse of Transpose:** $(A^T)^{-1} = (A^{-1})^T$

**Inverse of Scalar Multiple:** $(kA)^{-1} = \frac{1}{k}A^{-1}$ for $k \neq 0$

**Determinant of Inverse:** $\det(A^{-1}) = \frac{1}{\det(A)}$

## 7. Eigenvalue and Eigenvector Properties

### Fundamental Definitions

**Eigenvalue Equation:** $A\mathbf{v} = λ\mathbf{v}$
- $λ$: eigenvalue
- $\mathbf{v}$: eigenvector (non-zero)

**Characteristic Polynomial:** $\det(A - λI) = 0$

### Key Properties

**Trace-Eigenvalue Relationship:**
$$\text{tr}(A) = \sum_{i=1}^n λ_i$$

**Determinant-Eigenvalue Relationship:**
$$\det(A) = \prod_{i=1}n λ_i$$

**Eigenvalues of Special Matrices:**
- **Identity matrix:** All eigenvalues = 1
- **Zero matrix:** All eigenvalues = 0
- **Diagonal matrix:** Eigenvalues = diagonal elements
- **Triangular matrix:** Eigenvalues = diagonal elements

**Similarity Invariance:**
If $B = P^{-1}AP$, then $A$ and $B$ have the same eigenvalues.

### Eigenvalue Properties for Special Matrix Types

**Symmetric Matrices:**
- All eigenvalues are real
- Eigenvectors for distinct eigenvalues are orthogonal

**Skew-Symmetric Matrices:**
- Eigenvalues are purely imaginary or zero
- For real matrices: if $λ$ is an eigenvalue, so is $-λ$

**Orthogonal Matrices:**
- All eigenvalues have absolute value 1
- Eigenvalues are on the unit circle in the complex plane

**Positive Definite Matrices:**
- All eigenvalues are positive

## 8. Matrix Norm Properties

### Common Matrix Norms

**Frobenius Norm:**
$$\|A\|_F = \sqrt{\sum_{i,j} |a_{ij}|^2} = \sqrt{\text{tr}(A^T A)}$$

**Spectral Norm (2-norm):**
$$\|A\|_2 = \sqrt{λ_{\max}(A^T A)}$$

**1-norm (Maximum Column Sum):**
$$\|A\|_1 = \max_{1 \leq j \leq n} \sum_{i=1}^m |a_{ij}|$$

**∞-norm (Maximum Row Sum):**
$$\|A\|_\infty = \max_{1 \leq i \leq m} \sum_{j=1}^n |a_{ij}|$$

### Norm Properties

**Non-negativity:** $\|A\| \geq 0$, with equality iff $A = O$

**Homogeneity:** $\|kA\| = |k| \cdot \|A\|$

**Triangle Inequality:** $\|A + B\| \leq \|A\| + \|B\|$

**Submultiplicativity:** $\|AB\| \leq \|A\| \cdot \|B\|$

## 9. Positive Definite Matrix Properties

### Definition
A symmetric matrix $A$ is positive definite if:
$$\mathbf{x}^T A \mathbf{x} > 0 \quad \text{for all } \mathbf{x} \neq \mathbf{0}$$

### Equivalent Conditions

A symmetric matrix $A$ is positive definite if and only if:
1. All eigenvalues are positive
2. All leading principal minors are positive
3. $A = B^T B$ for some invertible matrix $B$
4. There exists a Cholesky decomposition $A = LL^T$

### Properties

**Inverse:** If $A$ is positive definite, then $A^{-1}$ is positive definite.

**Sum:** The sum of positive definite matrices is positive definite.

**Congruence:** If $A$ is positive definite and $P$ is invertible, then $P^T AP$ is positive definite.

## 10. Matrix Decomposition Properties

### LU Decomposition
$$A = LU$$
where $L$ is lower triangular and $U$ is upper triangular.

**Existence:** Every invertible matrix has an LU decomposition (with possible row permutations).

### QR Decomposition
$$A = QR$$
where $Q$ is orthogonal and $R$ is upper triangular.

**Existence:** Every matrix has a QR decomposition.

**Properties:**
- $\|Q\mathbf{x}\| = \|\mathbf{x}\|$ (orthogonal matrices preserve length)
- $\det(Q) = \pm 1$

### Singular Value Decomposition (SVD)
$$A = UΣV^T$$
where $U$ and $V$ are orthogonal and $Σ$ is diagonal.

**Properties:**
- Every matrix (including non-square) has an SVD
- Singular values are non-negative
- $\text{rank}(A) =$ number of non-zero singular values

## Summary

Matrix properties provide the theoretical foundation for understanding matrix behavior:

- **Algebraic Properties:** Govern how matrices combine under operations
- **Structural Properties:** Determine computational complexity and special cases
- **Spectral Properties:** Connect to eigenvalues and geometric interpretation
- **Norm Properties:** Quantify matrix "size" and condition
- **Decomposition Properties:** Enable efficient algorithms and analysis

These properties are interconnected and form the basis for advanced topics in linear algebra, numerical analysis, and applications across mathematics and science.