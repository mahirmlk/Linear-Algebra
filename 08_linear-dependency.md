# Linear Dependency

## Definition

A set of vectors {v₁, v₂, ..., vₙ} is **linearly dependent** if there exist scalars c₁, c₂, ..., cₙ, not all zero, such that:

**c₁v₁ + c₂v₂ + ... + cₙvₙ = 0**

In other words, at least one vector in the set can be expressed as a linear combination of the others.

## Equivalent Conditions

A set of vectors is linearly dependent if and only if:

1. **At least one vector can be written as a linear combination of the others**
2. **The matrix formed by these vectors (as columns) has determinant zero** (for square matrices)
3. **The vectors do not span the full space** they live in
4. **The rank of the matrix formed by these vectors is less than the number of vectors**

## Geometric Interpretation

### In 2D:
- Two vectors are linearly dependent if they are **collinear** (parallel)
- They lie on the same line through the origin

### In 3D:
- Two vectors are linearly dependent if they are **collinear**
- Three vectors are linearly dependent if they are **coplanar** (lie in the same plane)

### In nD:
- Vectors are linearly dependent if they lie in a subspace of dimension less than n

## Examples

### Example 1: Two Vectors in 2D
```
v₁ = [2, 4]
v₂ = [1, 2]
```

Check: Is there a non-zero solution to c₁v₁ + c₂v₂ = 0?
```
c₁[2, 4] + c₂[1, 2] = [0, 0]
2c₁ + c₂ = 0
4c₁ + 2c₂ = 0
```

From the first equation: c₂ = -2c₁
Substituting: 4c₁ + 2(-2c₁) = 4c₁ - 4c₁ = 0 ✓

Solution: c₁ = 1, c₂ = -2 (for example)
Therefore: v₁ - 2v₂ = 0, so **v₁ = 2v₂**

The vectors are **linearly dependent**.

### Example 2: Three Vectors in 3D
```
v₁ = [1, 0, 1]
v₂ = [2, 1, 0]
v₃ = [0, -1, 2]
```

Form the matrix and check its determinant:
```
A = |1  2  0|
    |0  1 -1|
    |1  0  2|
```

det(A) = 1|1 -1| - 2|0 -1| + 0|0 1|
           |0  2|    |1  2|    |1 0|
       = 1(2-0) - 2(0-(-1)) + 0
       = 2 - 2 = 0

Since det(A) = 0, the vectors are **linearly dependent**.

### Example 3: Linear Combination Form
```
v₁ = [1, 2, 3]
v₂ = [2, 4, 6]
v₃ = [1, 1, 1]
```

Notice that v₂ = 2v₁, so:
1·v₁ + (-1/2)·v₂ + 0·v₃ = 0

The vectors are **linearly dependent** because v₂ is a scalar multiple of v₁.

## Tests for Linear Dependence

### Method 1: Solve the Homogeneous System
Set up c₁v₁ + c₂v₂ + ... + cₙvₙ = 0 and solve for the coefficients.
- If only the trivial solution (all cᵢ = 0) exists → linearly independent
- If non-trivial solutions exist → linearly dependent

### Method 2: Determinant Test (Square Matrices)
For n vectors in n-dimensional space:
- If det(A) ≠ 0 → linearly independent
- If det(A) = 0 → linearly dependent

### Method 3: Row Reduction
Perform row reduction on the matrix formed by the vectors:
- If all columns have pivots → linearly independent
- If some columns don't have pivots → linearly dependent

### Method 4: Rank Analysis
- If rank(A) = n (number of vectors) → linearly independent
- If rank(A) < n → linearly dependent

## Common Cases of Linear Dependence

### 1. Zero Vector Present
If the zero vector is in the set, the vectors are automatically linearly dependent.

### 2. Repeated Vectors
If any vector appears more than once, the set is linearly dependent.

### 3. Scalar Multiples
If one vector is a scalar multiple of another, they are linearly dependent.

### 4. Too Many Vectors
If you have more than n vectors in n-dimensional space, they must be linearly dependent (pigeonhole principle).

## Applications

### 1. Solving Systems of Linear Equations
If the coefficient matrix has linearly dependent columns:
- The system may have no solution or infinitely many solutions
- The system cannot have a unique solution

### 2. Vector Spaces and Spanning
- Linearly dependent vectors create redundancy in spanning sets
- They don't contribute to the dimension of the space

### 3. Matrix Invertibility
A square matrix is non-invertible (singular) if and only if its columns (or rows) are linearly dependent.

### 4. Basis and Dimension
- A basis cannot contain linearly dependent vectors
- The dimension of a space is the maximum number of linearly independent vectors

## Connection to Determinants

For square matrices, linear dependence is equivalent to having determinant zero:

**det(A) = 0 ⟺ columns of A are linearly dependent**

This provides a quick test for linear dependence when working with square matrices.

## Practical Example: Economics

In economic modeling, if we have variables:
- x₁ = total income
- x₂ = salary income  
- x₃ = investment income

And x₁ = x₂ + x₃, then the vectors representing these variables are linearly dependent because one is the sum of the others.

## Summary

Linear dependence occurs when vectors are "redundant" - when at least one vector can be expressed in terms of the others. This concept is fundamental to understanding:
- Matrix invertibility
- System solvability  
- Vector space dimension
- Basis construction
- Geometric relationships between vectors