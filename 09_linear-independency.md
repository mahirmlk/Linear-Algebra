# Linear Independence

## Definition

A set of vectors {v₁, v₂, ..., vₙ} is **linearly independent** if the only solution to the equation:

**c₁v₁ + c₂v₂ + ... + cₙvₙ = 0**

is the **trivial solution**: c₁ = c₂ = ... = cₙ = 0.

In other words, no vector in the set can be expressed as a linear combination of the others.

## Equivalent Conditions

A set of vectors is linearly independent if and only if:

1. **No vector can be written as a linear combination of the others**
2. **The matrix formed by these vectors (as columns) has non-zero determinant** (for square matrices)
3. **The vectors span a space of dimension equal to the number of vectors**
4. **The rank of the matrix formed by these vectors equals the number of vectors**
5. **Each vector contributes a new dimension to the span**

## Geometric Interpretation

### In 2D:
- Two vectors are linearly independent if they are **not collinear** (not parallel)
- They point in different directions and can span the entire 2D plane

### In 3D:
- Two vectors are linearly independent if they are **not collinear**
- Three vectors are linearly independent if they are **not coplanar** (don't all lie in the same plane)
- They can span the entire 3D space

### In nD:
- n vectors are linearly independent if they span the full n-dimensional space
- They form a basis for that space

## Examples

### Example 1: Two Vectors in 2D
```
v₁ = [1, 0]
v₂ = [0, 1]
```

Check: Solve c₁v₁ + c₂v₂ = 0
```
c₁[1, 0] + c₂[0, 1] = [0, 0]
[c₁, c₂] = [0, 0]
```

This gives us: c₁ = 0 and c₂ = 0 (only trivial solution)

Therefore, the vectors are **linearly independent**.

### Example 2: Three Vectors in 3D
```
v₁ = [1, 0, 0]
v₂ = [0, 1, 0] 
v₃ = [0, 0, 1]
```

Form the matrix and check its determinant:
```
A = |1  0  0|
    |0  1  0|
    |0  0  1|
```

det(A) = 1 ≠ 0

Since det(A) ≠ 0, the vectors are **linearly independent**.

### Example 3: Non-Obvious Case
```
v₁ = [1, 2, 1]
v₂ = [2, 1, 3]
v₃ = [1, -1, 2]
```

Form the matrix:
```
A = |1  2  1|
    |2  1 -1|
    |1  3  2|
```

Calculate determinant:
det(A) = 1|1 -1| - 2|2 -1| + 1|2  1|
           |3  2|    |1  2|    |1  3|
       = 1(2-(-3)) - 2(4-(-1)) + 1(6-1)
       = 1(5) - 2(5) + 1(5)
       = 5 - 10 + 5 = 0

Since det(A) = 0, these vectors are **linearly dependent** (not independent).

### Example 4: Two Vectors in 3D
```
v₁ = [1, 0, 1]
v₂ = [0, 1, 2]
```

To check linear independence, solve c₁v₁ + c₂v₂ = 0:
```
c₁[1, 0, 1] + c₂[0, 1, 2] = [0, 0, 0]
[c₁, c₂, c₁ + 2c₂] = [0, 0, 0]
```

This gives us:
- c₁ = 0
- c₂ = 0  
- c₁ + 2c₂ = 0 (automatically satisfied)

Only trivial solution exists, so the vectors are **linearly independent**.

## Tests for Linear Independence

### Method 1: Solve the Homogeneous System
Set up c₁v₁ + c₂v₂ + ... + cₙvₙ = 0 and solve:
- If only trivial solution (all cᵢ = 0) → linearly independent
- If non-trivial solutions exist → linearly dependent

### Method 2: Determinant Test (Square Cases)
For n vectors in n-dimensional space:
- If det(A) ≠ 0 → linearly independent
- If det(A) = 0 → linearly dependent

### Method 3: Row Reduction (RREF)
Perform row reduction on the matrix with vectors as columns:
- If every column has a pivot → linearly independent
- If some columns lack pivots → linearly dependent

### Method 4: Rank Test
- If rank(A) = number of vectors → linearly independent
- If rank(A) < number of vectors → linearly dependent

## Maximum Number of Independent Vectors

**Key Theorem**: In n-dimensional space, you can have at most n linearly independent vectors.

### Examples:
- In 2D: At most 2 linearly independent vectors
- In 3D: At most 3 linearly independent vectors
- In nD: At most n linearly independent vectors

If you have more than n vectors in n-dimensional space, they **must** be linearly dependent.

## Properties of Linearly Independent Sets

### 1. Subset Property
Any subset of a linearly independent set is also linearly independent.

### 2. Extension Property
A linearly independent set can be extended to form a basis (by adding more independent vectors).

### 3. Uniqueness of Linear Combinations
If vectors are linearly independent and v = c₁v₁ + ... + cₙvₙ, then the coefficients cᵢ are uniquely determined.

### 4. Spanning and Independence
If n linearly independent vectors exist in n-dimensional space, they span the entire space.

## Applications

### 1. Basis Formation
- A basis for a vector space consists of linearly independent vectors that span the space
- The standard basis vectors (e₁, e₂, ..., eₙ) are always linearly independent

### 2. Matrix Invertibility  
A square matrix is invertible if and only if its columns (or rows) are linearly independent.

### 3. Coordinate Systems
Linearly independent vectors can serve as coordinate axes for representing any vector in the space.

### 4. Solving Linear Systems
When the coefficient matrix has linearly independent columns, the system Ax = b has a unique solution (if consistent).

## Connection to Other Concepts

### Determinants
For square matrices: **det(A) ≠ 0 ⟺ columns are linearly independent**

### Rank
**rank(A) = maximum number of linearly independent columns (or rows)**

### Nullspace
Columns are linearly independent ⟺ nullspace contains only the zero vector ⟺ null(A) = {0}

### Span
If vectors v₁, ..., vₙ are linearly independent, then dim(span{v₁, ..., vₙ}) = n

## Practical Examples

### Example 1: Physics - Force Vectors
Three force vectors in 3D space:
```
F₁ = [1, 0, 0] N (along x-axis)
F₂ = [0, 1, 0] N (along y-axis)  
F₃ = [0, 0, 1] N (along z-axis)
```
These are linearly independent and can represent any force vector in 3D.

### Example 2: Economics - Market Variables
Variables representing different economic factors:
- Interest rate changes
- Inflation rate
- GDP growth

If these variables are linearly independent, each provides unique information about the economy.

## Common Mistakes

### 1. Confusing with Orthogonality
- Linearly independent ≠ orthogonal
- Orthogonal vectors are always linearly independent
- But linearly independent vectors need not be orthogonal

### 2. Wrong Dimension Count
- In n-dimensional space, more than n vectors are always dependent
- Exactly n independent vectors span the full space

### 3. Zero Vector Inclusion
- Any set containing the zero vector is linearly dependent
- The zero vector can always be written as 0 = 0·v₁ + 0·v₂ + ... + 1·0

## Summary

Linear independence is a fundamental concept that ensures:
- No redundancy among vectors
- Maximum spanning capability
- Unique representation of linear combinations
- Basis formation possibility
- Matrix invertibility (for square matrices)

Understanding linear independence is crucial for grasping concepts like dimension, basis, rank, and the solvability of linear systems.