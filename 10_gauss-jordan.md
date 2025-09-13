# Gauss-Jordan Elimination Method

## Overview

The Gauss-Jordan elimination method is an algorithm used to solve systems of linear equations by transforming the augmented matrix into **Reduced Row Echelon Form (RREF)**. Unlike Gaussian elimination, which produces an upper triangular matrix, Gauss-Jordan elimination continues until the matrix is in its simplest form.

## Goals

1. **Solve systems of linear equations**
2. **Find matrix inverses**
3. **Determine matrix rank**
4. **Analyze solution existence and uniqueness**

## Reduced Row Echelon Form (RREF)

A matrix is in RREF if it satisfies:

1. **All zero rows are at the bottom**
2. **The leading entry (pivot) of each non-zero row is 1**
3. **Each leading 1 is to the right of the leading 1 in the row above**
4. **All entries above and below each leading 1 are zero**

### Example of RREF:
```
|1  0  3  0  |  5|
|0  1 -2  0  |  3|
|0  0  0  1  | -1|
|0  0  0  0  |  0|
```

## Elementary Row Operations

The three allowed operations that don't change the solution set:

1. **Row Swapping**: Rᵢ ↔ Rⱼ (swap rows i and j)
2. **Row Scaling**: kRᵢ → Rᵢ (multiply row i by non-zero scalar k)
3. **Row Addition**: Rᵢ + kRⱼ → Rᵢ (add k times row j to row i)

## Step-by-Step Algorithm

### Step 1: Form the Augmented Matrix
For the system Ax = b, create [A|b]

### Step 2: Create Leading 1's
- Find the leftmost non-zero column
- Make the top entry a 1 (using row scaling or swapping)

### Step 3: Eliminate Above and Below
- Use row addition to make all other entries in that column zero

### Step 4: Move to Next Row and Column
- Repeat steps 2-3 for the remaining submatrix

### Step 5: Continue Until RREF
- Stop when no more leading 1's can be created

## Detailed Example 1: Unique Solution

Solve the system:
```
2x + y - z = 8
-3x - y + 2z = -11
-2x + y + 2z = -3
```

### Step 1: Form Augmented Matrix
```
|  2   1  -1 |  8|
| -3  -1   2 |-11|
| -2   1   2 | -3|
```

### Step 2: Create Leading 1 in Position (1,1)
Divide R₁ by 2: R₁ → (1/2)R₁
```
|  1  1/2  -1/2 |  4|
| -3   -1    2  |-11|
| -2    1    2  | -3|
```

### Step 3: Eliminate Below Leading 1
R₂ → R₂ + 3R₁:
```
|  1  1/2  -1/2 |  4 |
|  0  1/2   1/2 |  1 |
| -2    1    2  | -3 |
```

R₃ → R₃ + 2R₁:
```
|  1  1/2  -1/2 |  4|
|  0  1/2   1/2 |  1|
|  0    2    1  |  5|
```

### Step 4: Create Leading 1 in Position (2,2)
R₂ → 2R₂:
```
|  1  1/2  -1/2 |  4|
|  0    1    1  |  2|
|  0    2    1  |  5|
```

### Step 5: Eliminate Above and Below the New Leading 1
R₁ → R₁ - (1/2)R₂:
```
|  1    0   -1  |  3|
|  0    1    1  |  2|
|  0    2    1  |  5|
```

R₃ → R₃ - 2R₂:
```
|  1    0   -1  |  3|
|  0    1    1  |  2|
|  0    0   -1  |  1|
```

### Step 6: Create Leading 1 in Position (3,3)
R₃ → -R₃:
```
|  1    0   -1  |  3|
|  0    1    1  |  2|
|  0    0    1  | -1|
```

### Step 7: Eliminate Above the Leading 1 in Column 3
R₁ → R₁ + R₃:
```
|  1    0    0  |  2|
|  0    1    1  |  2|
|  0    0    1  | -1|
```

R₂ → R₂ - R₃:
```
|  1    0    0  |  2|
|  0    1    0  |  3|
|  0    0    1  | -1|
```

### Final RREF and Solution
The matrix is now in RREF:
```
|  1    0    0  |  2|
|  0    1    0  |  3|
|  0    0    1  | -1|
```

**Solution**: x = 2, y = 3, z = -1

### Verification:
- 2(2) + 3 - (-1) = 4 + 3 + 1 = 8 ✓
- -3(2) - 3 + 2(-1) = -6 - 3 - 2 = -11 ✓
- -2(2) + 3 + 2(-1) = -4 + 3 - 2 = -3 ✓

## Example 2: Infinitely Many Solutions

Solve the system:
```
x + 2y - z = 4
2x + 4y - 2z = 8
x + 2y + z = 6
```

### Step 1: Augmented Matrix
```
|  1   2  -1 |  4|
|  2   4  -2 |  8|
|  1   2   1 |  6|
```

### Step 2: Eliminate Below Leading 1
R₂ → R₂ - 2R₁:
```
|  1   2  -1 |  4|
|  0   0   0 |  0|
|  1   2   1 |  6|
```

R₃ → R₃ - R₁:
```
|  1   2  -1 |  4|
|  0   0   0 |  0|
|  0   0   2 |  2|
```

### Step 3: Rearrange Rows (Move Zero Row Down)
```
|  1   2  -1 |  4|
|  0   0   2 |  2|
|  0   0   0 |  0|
```

### Step 4: Create Leading 1 in Position (2,3)
R₂ → (1/2)R₂:
```
|  1   2  -1 |  4|
|  0   0   1 |  1|
|  0   0   0 |  0|
```

### Step 5: Eliminate Above Leading 1
R₁ → R₁ + R₂:
```
|  1   2   0 |  5|
|  0   0   1 |  1|
|  0   0   0 |  0|
```

### Final RREF and Solution
The RREF shows:
- x + 2y = 5
- z = 1

**Solution**: 
- x = 5 - 2y
- y = t (free variable)
- z = 1

**General Solution**: (5 - 2t, t, 1) where t ∈ ℝ

## Example 3: No Solution

Solve the system:
```
x + y + z = 1
2x + 2y + 2z = 3
x + y + z = 2
```

### Step 1: Augmented Matrix
```
|  1   1   1 |  1|
|  2   2   2 |  3|
|  1   1   1 |  2|
```

### Step 2: Eliminate Below Leading 1
R₂ → R₂ - 2R₁:
```
|  1   1   1 |  1|
|  0   0   0 |  1|
|  1   1   1 |  2|
```

R₃ → R₃ - R₁:
```
|  1   1   1 |  1|
|  0   0   0 |  1|
|  0   0   0 |  1|
```

### Final Analysis
The second row represents: 0x + 0y + 0z = 1
This is **impossible** (0 ≠ 1).

**Conclusion**: The system has **no solution** (inconsistent).

## Finding Matrix Inverse Using Gauss-Jordan

To find A⁻¹, apply Gauss-Jordan to [A|I] to get [I|A⁻¹].

### Example: Find the Inverse of A
```
A = |  2   1|
    |  1   1|
```

### Step 1: Form [A|I]
```
|  2   1 |  1   0|
|  1   1 |  0   1|
```

### Step 2: Apply Gauss-Jordan
R₁ → (1/2)R₁:
```
|  1  1/2 | 1/2   0|
|  1    1 |   0   1|
```

R₂ → R₂ - R₁:
```
|  1  1/2 | 1/2   0|
|  0  1/2 |-1/2   1|
```

R₂ → 2R₂:
```
|  1  1/2 | 1/2   0|
|  0    1 |  -1   2|
```

R₁ → R₁ - (1/2)R₂:
```
|  1    0 |   1  -1|
|  0    1 |  -1   2|
```

### Result
```
A⁻¹ = |  1  -1|
      | -1   2|
```

## Applications

### 1. Solving Linear Systems
- Unique solution: One solution exists
- Infinite solutions: Free variables present
- No solution: Inconsistent system detected

### 2. Matrix Operations
- Finding matrix inverses
- Computing matrix rank
- Determining linear independence

### 3. Linear Programming
- Simplex method uses row operations
- Finding basic feasible solutions

### 4. Engineering Applications
- Circuit analysis (Kirchhoff's laws)
- Structural analysis
- Control systems

## Computational Considerations

### Advantages:
- Systematic and reliable
- Works for any system size
- Provides complete solution information
- Handles all solution types

### Disadvantages:
- Can be computationally expensive for large matrices
- Sensitive to round-off errors
- More work than back-substitution for triangular systems

### Complexity:
- Time complexity: O(n³)
- Space complexity: O(n²)

## Summary

Gauss-Jordan elimination is a powerful method that:
- **Completely solves** linear systems
- **Identifies** solution type (unique, infinite, none)
- **Computes** matrix inverses
- **Determines** matrix properties (rank, linear independence)

The key is systematic application of elementary row operations to achieve RREF, making the solution immediately readable from the final matrix.