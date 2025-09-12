# Determinant Properties

## Fundamental Properties

### 1. Determinant of Identity Matrix
det(I) = 1, where I is the n×n identity matrix

### 2. Determinant of Zero Matrix
det(0) = 0, where 0 is the n×n zero matrix

### 3. Determinant and Matrix Multiplication
For square matrices A and B of the same size:
**det(AB) = det(A) · det(B)**

This is one of the most important properties of determinants.

### 4. Determinant of Transpose
**det(Aᵀ) = det(A)**

The determinant of a matrix equals the determinant of its transpose.

### 5. Determinant of Inverse
If A is invertible:
**det(A⁻¹) = 1/det(A) = [det(A)]⁻¹**

## Row and Column Operations

### Row Operations and Their Effects

1. **Row Swapping**: Swapping two rows multiplies the determinant by -1
   - If B is obtained from A by swapping two rows, then det(B) = -det(A)

2. **Row Scaling**: Multiplying a row by a scalar k multiplies the determinant by k
   - If B is obtained from A by multiplying row i by k, then det(B) = k · det(A)

3. **Row Addition**: Adding a multiple of one row to another doesn't change the determinant
   - If B is obtained from A by adding c times row j to row i, then det(B) = det(A)

### Column Operations
The same rules apply to column operations:
- Column swapping: det changes sign
- Column scaling by k: det is multiplied by k
- Adding multiple of one column to another: det unchanged

### Consequences

- **Linear Dependence**: If two rows (or columns) are identical or proportional, det(A) = 0
- **Zero Row/Column**: If any row or column is zero, det(A) = 0
- **Triangular Matrices**: For upper or lower triangular matrices, det(A) = product of diagonal elements

## Scalar Multiplication

For a scalar k and n×n matrix A:
**det(kA) = kⁿ · det(A)**

Note: This is kⁿ, not just k, because each of the n rows is multiplied by k.

## Special Matrix Types

### 1. Diagonal Matrix
For a diagonal matrix D = diag(d₁, d₂, ..., dₙ):
**det(D) = d₁ · d₂ · ... · dₙ**

### 2. Triangular Matrix
For upper triangular matrix U or lower triangular matrix L:
**det(U) = det(L) = u₁₁ · u₂₂ · ... · uₙₙ**
(product of diagonal elements)

### 3. Block Matrices
For a block triangular matrix:
```
A = |A₁₁  A₁₂|
    |0    A₂₂|
```
**det(A) = det(A₁₁) · det(A₂₂)**

### 4. Orthogonal Matrix
For an orthogonal matrix Q (where QᵀQ = I):
**det(Q) = ±1**

### 5. Permutation Matrix
For a permutation matrix P:
**det(P) = ±1**
- det(P) = 1 for even permutations
- det(P) = -1 for odd permutations

## Advanced Properties

### 1. Multilinearity
The determinant is linear in each row (and each column) separately when other rows are held fixed.

### 2. Alternating Property
If any two rows (or columns) are swapped, the determinant changes sign.

### 3. Vandermonde Matrix
For a Vandermonde matrix:
```
V = |1   1   ...  1  |
    |x₁  x₂  ...  xₙ |
    |x₁² x₂² ...  xₙ²|
    |... ... ...  ...|
    |x₁ⁿ⁻¹ x₂ⁿ⁻¹ ... xₙⁿ⁻¹|
```
**det(V) = ∏₁≤i<j≤n (xⱼ - xᵢ)**

### 4. Determinant and Rank
- det(A) ≠ 0 if and only if rank(A) = n (full rank)
- det(A) = 0 if and only if rank(A) < n

### 5. Cofactor Matrix
If C is the cofactor matrix of A, then:
**det(C) = [det(A)]ⁿ⁻¹**

## Computational Properties

### 1. LU Decomposition
If A = LU (LU decomposition), then:
**det(A) = det(L) · det(U)**

Since L and U are triangular:
**det(A) = (product of L's diagonal) × (product of U's diagonal)**

### 2. Gaussian Elimination
When using Gaussian elimination:
- Each row swap changes sign of determinant
- Row scaling by k multiplies determinant by k
- Row additions don't change determinant
- Final result: det(A) = ±(product of pivots)

## Examples

### Property Verification
Given:
```
A = |2  1|    B = |1  0|
    |3  4|        |2  1|
```

**Example 1: det(AB) = det(A)det(B)**

```
AB = |2  1||1  0| = |2+2  0+1| = |4  1|
     |3  4||2  1|   |3+8  0+4|   |11 4|

det(AB) = 4·4 - 1·11 = 16 - 11 = 5
det(A) = 8 - 3 = 5
det(B) = 1 - 0 = 1
det(A)det(B) = 5·1 = 5 ✓
```

