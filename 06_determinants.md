# Determinants: Concept and Definition

## What is a Determinant?

A determinant is a scalar value that can be computed from the elements of a square matrix. It provides important information about the matrix and the linear transformation it represents.

## Notation

For a square matrix A, the determinant is denoted as:
- det(A)
- |A|
- |a₁₁ a₁₂ ... a₁ₙ|
  |a₂₁ a₂₂ ... a₂ₙ|
  |... ... ... ...|
  |aₙ₁ aₙ₂ ... aₙₙ|

## Determinant Formulas

### 1×1 Matrix
For a 1×1 matrix A = [a], det(A) = a

### 2×2 Matrix
For a 2×2 matrix:
```
A = |a b|
    |c d|
```
det(A) = ad - bc

### 3×3 Matrix
For a 3×3 matrix:
```
A = |a₁₁ a₁₂ a₁₃|
    |a₂₁ a₂₂ a₂₃|
    |a₃₁ a₃₂ a₃₃|
```

**Method 1: Rule of Sarrus**
det(A) = a₁₁a₂₂a₃₃ + a₁₂a₂₃a₃₁ + a₁₃a₂₁a₃₂ - a₁₃a₂₂a₃₁ - a₁₂a₂₁a₃₃ - a₁₁a₂₃a₃₂

**Method 2: Cofactor Expansion**
Expanding along the first row:
det(A) = a₁₁|a₂₂ a₂₃| - a₁₂|a₂₁ a₂₃| + a₁₃|a₂₁ a₂₂|
            |a₃₂ a₃₃|      |a₃₁ a₃₃|      |a₃₁ a₃₂|

## General n×n Matrix

For an n×n matrix, the determinant can be calculated using:

### Cofactor Expansion (Laplace Expansion)
det(A) = Σⱼ₌₁ⁿ aᵢⱼ · Cᵢⱼ (expansion along row i)
or
det(A) = Σᵢ₌₁ⁿ aᵢⱼ · Cᵢⱼ (expansion along column j)

Where Cᵢⱼ = (-1)ⁱ⁺ʲ · Mᵢⱼ is the cofactor, and Mᵢⱼ is the minor (determinant of the (n-1)×(n-1) submatrix obtained by deleting row i and column j).

## Geometric Interpretation

### 2D Case
The absolute value of the determinant of a 2×2 matrix represents the area of the parallelogram formed by the column vectors.

### 3D Case
The absolute value of the determinant of a 3×3 matrix represents the volume of the parallelepiped formed by the column vectors.

### General Case
The determinant represents the "signed volume" of the n-dimensional parallelepiped formed by the column vectors in n-dimensional space.

## Key Applications

1. **Invertibility**: A matrix is invertible if and only if its determinant is non-zero
2. **System of Linear Equations**: Cramer's rule uses determinants to solve linear systems
3. **Linear Transformations**: The determinant gives the scaling factor of the transformation
4. **Eigenvalues**: The characteristic polynomial involves determinants
5. **Vector Operations**: Cross products and volumes in geometry

## Examples

### Example 1: 2×2 Matrix
```
A = |3  -2|
    |1   4|
```
det(A) = (3)(4) - (-2)(1) = 12 + 2 = 14

### Example 2: 3×3 Matrix
```
A = |2  1  3|
    |0  4  1|
    |1  2  1|
```
Using cofactor expansion along the first row:
det(A) = 2|4 1| - 1|0 1| + 3|0 4|
          |2 1|    |1 1|    |1 2|
       = 2(4-2) - 1(0-1) + 3(0-4)
       = 2(2) - 1(-1) + 3(-4)
       = 4 + 1 - 12 = -7

## Special Cases

- **Identity Matrix**: det(I) = 1
- **Zero Matrix**: det(0) = 0
- **Diagonal Matrix**: det(A) = product of diagonal elements
- **Triangular Matrix**: det(A) = product of diagonal elements
- **Singular Matrix**: det(A) = 0 (not invertible)