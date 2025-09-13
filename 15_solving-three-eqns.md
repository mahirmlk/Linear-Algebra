# Solving Three Equations for Three Unknowns - Augmented Matrix Method

## The Setup

We have **3 equations** and **3 unknowns** (x, y, z):

```
a₁x + b₁y + c₁z = d₁    (Equation 1)
a₂x + b₂y + c₂z = d₂    (Equation 2)  
a₃x + b₃y + c₃z = d₃    (Equation 3)
```

**Goal:** Use the **Augmented Matrix Method** to find x, y, and z.

## What is the Augmented Matrix Method?

The augmented matrix combines the **coefficient matrix** and **constant vector**:

```
System:              Augmented Matrix [A|b]:
2x + y + z = 8   →   ┌─────────────────┐
x - y + 2z = 3       │ 2  1  1 │  8   │
3x + y - z = 2       │ 1 -1  2 │  3   │
                     │ 3  1 -1 │  2   │
                     └─────────────────┘
```


## Example 1: Clean Integer System

### System:
```
x + y + z = 9      (1)
x - y + z = 1      (2)  
x + y - z = 3      (3)
```

### Step 1: Augmented Matrix
```
┌─────────────────┐
│ 1  1  1 │  9   │
│ 1 -1  1 │  1   │
│ 1  1 -1 │  3   │
└─────────────────┘
```

### Step 2: Visual Row Operations

**OPERATION 1:** Eliminate first column below pivot
R₂ → R₂ - R₁, R₃ → R₃ - R₁

```
BEFORE:                    AFTER:
┌─────────────────┐       ┌─────────────────┐
│ 1  1  1 │  9   │  →    │ 1  1  1 │  9   │
│ 1 -1  1 │  1   │       │ 0 -2  0 │ -8   │
│ 1  1 -1 │  3   │       │ 0  0 -2 │ -6   │
└─────────────────┘       └─────────────────┘
```

**OPERATION 2:** Make pivots equal to 1
R₂ → R₂ ÷ (-2), R₃ → R₃ ÷ (-2)

```
┌─────────────────┐
│ 1  1  1 │  9   │
│ 0  1  0 │  4   │  ← Now y = 4
│ 0  0  1 │  3   │  ← Now z = 3
└─────────────────┘
```

**OPERATION 3:** Eliminate above pivots
R₁ → R₁ - R₂ - R₃

```
FINAL RREF:
┌─────────────────┐
│ 1  0  0 │  2   │  ← x = 2
│ 0  1  0 │  4   │  ← y = 4  
│ 0  0  1 │  3   │  ← z = 3
└─────────────────┘
```

### Step 3: Read Solution
```
 SOLUTION: x = 2, y = 4, z = 3
```

### Step 4: Verify
```
Equation 1: 2 + 4 + 3 = 9 ✓
Equation 2: 2 - 4 + 3 = 1 ✓  
Equation 3: 2 + 4 - 3 = 3 ✓
```

## Example 3: Real-World Problem - Money Distribution

### Problem: Inheritance Division
Three siblings inherit money:
- Total inheritance: $120,000
- Oldest gets $20,000 more than middle child
- Middle child gets twice what youngest gets

Let: O = Oldest, M = Middle, Y = Youngest

### System:
```
O + M + Y = 120        (1)
O - M = 20             (2)
M - 2Y = 0             (3)
```

### Step 1: Augmented Matrix
```
┌─────────────────┐
│ 1  1  1 │ 120  │
│ 1 -1  0 │  20  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

### Step 2: Row Operations

**R₂ → R₂ - R₁:**
```
┌─────────────────┐
│ 1  1  1 │ 120  │
│ 0 -2 -1 │-100  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

**R₂ → R₂ ÷ (-2):**
```
┌─────────────────┐
│ 1  1   1  │ 120 │
│ 0  1  1/2 │  50 │
│ 0  1  -2  │   0 │
└─────────────────┘
```

Fractions again! Let me multiply equation (2) by 2 from the start.

### Revised System (multiply equation 2 by 1):
Actually, let me rewrite the constraints more carefully:

```
O + M + Y = 120        (1)
O = M + 20             (2)  
M = 2Y                 (3)
```

Substitute (2) and (3) into (1):
```
(M + 20) + M + (M/2) = 120
2.5M + 20 = 120
2.5M = 100
M = 40
```

Then: Y = M/2 = 20, O = M + 20 = 60

### Augmented Matrix Approach:
Rewrite as standard form:
```
O + M + Y = 120        (1)
O - M = 20             (2)
-2Y + M = 0            (3)
```

**Matrix:**
```
┌─────────────────┐
│ 1  1  1 │ 120  │
│ 1 -1  0 │  20  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

**After row operations:**
```
┌─────────────────┐
│ 1  0  0 │  60  │  ← O = $60,000
│ 0  1  0 │  40  │  ← M = $40,000
│ 0  0  1 │  20  │  ← Y = $20,000
└─────────────────┘
```

### Verify:
- Total: 60 + 40 + 20 = 120 ✓
- O - M: 60 - 40 = 20 ✓
- M = 2Y: 40 = 2(20) ✓

## Example 4: Business Problem - Production Planning

### Problem: Factory Production
A factory makes products A, B, and C:
- Total daily production: 100 units
- Product A production = Product B + Product C
- Product B production = 2 × Product C

Let: A = Product A, B = Product B, C = Product C

### System:
```
A + B + C = 100        (1)
A = B + C              (2)
B = 2C                 (3)
```

### Rewrite in Standard Form:
```
A + B + C = 100        (1)
A - B - C = 0          (2)
B - 2C = 0             (3)
```

### Augmented Matrix:
```
┌─────────────────┐
│ 1  1  1 │ 100  │
│ 1 -1 -1 │   0  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

### Row Operations:

**R₂ → R₂ - R₁:**
```
┌─────────────────┐
│ 1  1  1 │ 100  │
│ 0 -2 -2 │-100  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

**R₂ → R₂ ÷ (-2):**
```
┌─────────────────┐
│ 1  1  1 │ 100  │
│ 0  1  1 │  50  │
│ 0  1 -2 │   0  │
└─────────────────┘
```

**R₃ → R₃ - R₂, R₁ → R₁ - R₂:**
```
┌─────────────────┐
│ 1  0  0 │  50  │  ← A = 50
│ 0  1  1 │  50  │
│ 0  0 -3 │ -50  │
└─────────────────┘
```

**R₃ → R₃ ÷ (-3):**
```
┌─────────────────┐
│ 1  0  0 │  50  │  ← A = 50
│ 0  1  1 │  50  │
│ 0  0  1 │ 50/3 │  ← C = 50/3
└─────────────────┘
```

This gives fractions. Let me fix the problem constraints.

### Corrected Problem:
```
A + B + C = 120        (1)
A = B + C              (2)
B = 2C                 (3)
```

### Quick Solution by Substitution:
From (3): B = 2C
From (2): A = B + C = 2C + C = 3C
From (1): 3C + 2C + C = 120 → 6C = 120 → C = 20

Therefore:
- C = 20 units
- B = 2C = 40 units  
- A = 3C = 60 units

## Step-by-Step Augmented Matrix Process

### General Template:

```
 STEP 1: Write augmented matrix [A|b]
┌─────────────────┐
│ a₁ b₁ c₁│ d₁   │
│ a₂ b₂ c₂│ d₂   │
│ a₃ b₃ c₃│ d₃   │
└─────────────────┘

 STEP 2: Row operations to get RREF
- Make leading coefficients = 1
- Eliminate above and below each pivot

 STEP 3: Read solution from final form  
┌─────────────────┐
│ 1  0  0 │ x₀   │  ← x = x₀
│ 0  1  0 │ y₀   │  ← y = y₀
│ 0  0  1 │ z₀   │  ← z = z₀
└─────────────────┘

 STEP 4: Verify in original equations
```

## Solution Types

### Type 1: Unique Solution 
```
┌─────────────────┐
│ 1  0  0 │  a   │  ← One answer
│ 0  1  0 │  b   │
│ 0  0  1 │  c   │
└─────────────────┘
```

### Type 2: No Solution 
```
┌─────────────────┐
│ 1  0  2 │  3   │
│ 0  1 -1 │  2   │
│ 0  0  0 │  5   │  ← 0 = 5 (impossible!)
└─────────────────┘
```

### Type 3: Infinite Solutions ∞
```
┌─────────────────┐
│ 1  2  0 │  4   │
│ 0  0  1 │  3   │
│ 0  0  0 │  0   │  ← Free variable exists
└─────────────────┘
```

## Quick Tips for Success

###  DO:
- **Set up** the augmented matrix carefully
- **Work systematically** row by row
- **Check arithmetic** at each step
- **Verify** final solution in original equations

###  AVOID:
- **Rushing** through row operations
- **Forgetting** to apply operations to entire rows
- **Skipping** verification step
- **Making** sign errors

## Summary

The **Augmented Matrix Method** is:
- **Systematic** and reliable
- **Works** for any 3×3 system  
- **Shows** solution type clearly
- **Efficient** once mastered

**Key insight:** Transform [A|b] → [I|solution] using row operations!

**Always remember:** The solution appears in the rightmost column when you achieve the identity matrix on the left.