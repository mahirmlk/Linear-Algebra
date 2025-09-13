# Singular Matrices

## What is a Singular Matrix?

A **singular matrix** is a square matrix that:
- Has **determinant = 0**
- Is **NOT invertible** (no inverse exists)
- Has **linearly dependent** rows or columns

## Quick Test: Is a Matrix Singular?

**Rule:** If det(A) = 0, then A is singular

### Example 1: 2×2 Singular Matrix
```
A = |2  4|
    |1  2|
```

**Calculate determinant:**
det(A) = (2)(2) - (4)(1) = 4 - 4 = **0**

Since det(A) = 0, matrix A is **SINGULAR** 

### Visual Why:
```
Row 1: [2, 4] = 2 × [1, 2] = 2 × Row 2
       ↑                    ↑
   Same direction!      Linearly dependent!
```

## Example 2: 3×3 Singular Matrix

```
B = |1  2  3|
    |2  4  6|
    |0  1  1|
```

**Notice:** Row 2 = 2 × Row 1

**Calculate determinant:** (expanding along first column)
```
det(B) = 1|4  6| - 2|2  3| + 0|2  3|
          |1  1|    |1  1|    |4  6|
       = 1(4-6) - 2(2-3) + 0
       = 1(-2) - 2(-1)
       = -2 + 2 = 0
```

Since det(B) = 0, matrix B is **SINGULAR** 

## Common Patterns of Singular Matrices

### Pattern 1: Identical Rows/Columns
```
|1  2|  ← Same rows
|1  2|  ← det = 0
```

### Pattern 2: Proportional Rows/Columns
```
|2  4|  ← Row 2 = 2 × Row 1
|1  2|  ← det = 0
```

### Pattern 3: Zero Row/Column
```
|3  5|  ← Row 2 is all zeros
|0  0|  ← det = 0
```

### Pattern 4: Linear Combination
```
|1  2  3|
|2  4  6|  ← Row 2 = 2 × Row 1
|3  6  9|  ← Row 3 = 3 × Row 1
```

## What Makes a Matrix NON-Singular?

A matrix is **non-singular** (invertible) when:
- det(A) ≠ 0
- All rows/columns are linearly independent
- Inverse A⁻¹ exists

### Example: Non-Singular Matrix
```
C = |1  2|
    |3  4|
```

det(C) = (1)(4) - (2)(3) = 4 - 6 = -2 ≠ 0

Since det(C) ≠ 0, matrix C is **NON-SINGULAR** 

## Impact on Systems of Equations

### When Coefficient Matrix is Singular:

**System: Ax = b**

If A is singular, then:
- **Either:** No solution exists (inconsistent)
- **Or:** Infinite solutions exist

### Example: Singular System
```
2x + 4y = 6   |2  4||x|   |6|
x + 2y = 3    |1  2||y| = |3|
```

**Matrix A is singular** (Row 1 = 2 × Row 2)

**Notice:** Equation 1 = 2 × Equation 2
- 2x + 4y = 6 is the same as 2(x + 2y) = 2(3)
- Both equations say the same thing!

**Result:** **Infinite solutions** along the line x + 2y = 3

### Example: No Solution Case
```
2x + 4y = 6   |2  4||x|   |6|
x + 2y = 4    |1  2||y| = |4|
```

**Matrix A is still singular**, but now:
- Equation 1: 2x + 4y = 6 → x + 2y = 3
- Equation 2: x + 2y = 4

**Contradiction!** x + 2y cannot equal both 3 and 4.

**Result:** **No solution exists**

## Quick Detection Methods

### Method 1: Row Inspection
Look for:
- Identical rows
- One row = multiple of another
- Zero rows

### Method 2: Determinant
- Calculate det(A)
- If det(A) = 0 → Singular
- If det(A) ≠ 0 → Non-singular

### Method 3: Row Reduction
- Apply row operations
- If you get a zero row → Singular
- If you get identity matrix → Non-singular

## Real-World Example: Business Problem

### Problem: Production Planning
A factory makes products A and B:
- Machine 1: 2 hours for A, 4 hours for B
- Machine 2: 1 hour for A, 2 hours for B

**Matrix:**
```
|2  4|  Hours needed per product
|1  2|  
```

This is **SINGULAR**! (Row 1 = 2 × Row 2)

**Interpretation:** 
- Both machines have the same productivity ratio
- Cannot uniquely determine production levels
- Need additional constraints or different machine capabilities

## Summary

| Property | Singular Matrix | Non-Singular Matrix |
|----------|-----------------|---------------------|
| **Determinant** | = 0 | ≠ 0 |
| **Inverse** | Does not exist | Exists |
| **Rows/Columns** | Linearly dependent | Linearly independent |
| **System Ax = b** | 0 or ∞ solutions | Unique solution |

### Key Takeaways:
- **Singular = No inverse possible**
- **Quick test: det(A) = 0?**
- **Systems with singular matrices have special solution patterns**
- **Common in real problems with redundant constraints**