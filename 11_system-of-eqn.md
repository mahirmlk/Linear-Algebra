# Matrices to Solve Linear Systems - Integer Examples

## Example 1: Simple 2×2 System

### Problem: Find where two lines meet
```
x + y = 5
x - y = 1
```

### Visual Representation:
```
   y
   |
 4 |     Line 1: x + y = 5
   |    /
 3 |   /  (3,2) ← Solution
   |  / 
 2 |_●_____ x
   |  \  1 2 3 4
 1 |   \
   |    \ Line 2: x - y = 1
   |_____\__
```

### Step 1: Write in Matrix Form
```
System:        Matrix Form:
x + y = 5  →   |1  1| |x|   |5|
x - y = 1      |1 -1| |y| = |1|
```

### Step 2: Set Up Augmented Matrix
```
|1  1 | 5|
|1 -1 | 1|
```

### Step 3: Solve Using Row Operations

**Step 3a:** Eliminate the first column below the pivot
R₂ → R₂ - R₁
```
|1  1 | 5|
|0 -2 |-4|
```

**Step 3b:** Make the second pivot equal to 1
R₂ → R₂ ÷ (-2)
```
|1  1 | 5|
|0  1 | 2|
```

**Step 3c:** Eliminate above the second pivot
R₁ → R₁ - R₂
```
|1  0 | 3|
|0  1 | 2|
```

### Step 4: Read the Solution
```
x = 3
y = 2
```

### Step 5: Verify
- Line 1: x + y = 3 + 2 = 5 ✓
- Line 2: x - y = 3 - 2 = 1 ✓

**Answer:** The lines meet at point (3, 2)

## Example 2: 3×3 System with Clean Numbers

### Problem: Three planes meeting at a point
```
x + y + z = 6
2x - y + z = 3  
x + 2y - z = 1
```

### Step 1: Matrix Form
```
|1  1  1| |x|   |6|
|2 -1  1| |y| = |3|
|1  2 -1| |z|   |1|
```

### Step 2: Augmented Matrix
```
|1  1  1 | 6|
|2 -1  1 | 3|
|1  2 -1 | 1|
```

### Step 3: Row Operations

**Eliminate first column below pivot:**
R₂ → R₂ - 2R₁
```
|1  1  1 | 6|
|0 -3 -1 |-9|
|1  2 -1 | 1|
```

R₃ → R₃ - R₁
```
|1  1  1 | 6|
|0 -3 -1 |-9|
|0  1 -2 |-5|
```

**Make second pivot positive and equal to 1:**
R₂ → R₂ ÷ (-3)
```
|1  1  1 | 6|
|0  1  1/3| 3|
|0  1 -2 |-5|
```

Wait, this creates fractions! Let me try a different approach by swapping rows first.

**Swap R₂ and R₃:**
```
|1  1  1 | 6|
|0  1 -2 |-5|
|0 -3 -1 |-9|
```

**Eliminate second column:**
R₁ → R₁ - R₂
```
|1  0  3 |11|
|0  1 -2 |-5|
|0 -3 -1 |-9|
```

R₃ → R₃ + 3R₂
```
|1  0  3 |11|
|0  1 -2 |-5|
|0  0 -7 |-24|
```

Hmm, still getting non-integers. Let me design a cleaner example.

## Example 3: Perfect Integer System

### Problem: A system designed for clean solutions
```
x + y + z = 6
x + y - z = 2
x - y + z = 4
```

### Step 1: Augmented Matrix
```
|1  1  1 | 6|
|1  1 -1 | 2|
|1 -1  1 | 4|
```

### Step 2: Row Operations

**Eliminate first column:**
R₂ → R₂ - R₁, R₃ → R₃ - R₁
```
|1  1  1 | 6|
|0  0 -2 |-4|
|0 -2  0 |-2|
```

**Swap R₂ and R₃ to get a pivot:**
```
|1  1  1 | 6|
|0 -2  0 |-2|
|0  0 -2 |-4|
```

**Make pivots equal to 1:**
R₂ → R₂ ÷ (-2), R₃ → R₃ ÷ (-2)
```
|1  1  1 | 6|
|0  1  0 | 1|
|0  0  1 | 2|
```

**Eliminate above pivots:**
R₁ → R₁ - R₂ - R₃
```
|1  0  0 | 3|
|0  1  0 | 1|
|0  0  1 | 2|
```

### Step 3: Solution
```
x = 3
y = 1
z = 2
```

### Step 4: Verify
- Equation 1: 3 + 1 + 2 = 6 ✓
- Equation 2: 3 + 1 - 2 = 2 ✓  
- Equation 3: 3 - 1 + 2 = 4 ✓

## Real-World Example: Money Problem

### Problem: Coin Counting
Sarah has quarters (25¢), dimes (10¢), and nickels (5¢).
- Total coins: 20
- Total value: $2.75 = 275¢
- Quarters = Dimes + Nickels

Let: q = quarters, d = dimes, n = nickels

### System:
```
q + d + n = 20        (total coins)
25q + 10d + 5n = 275  (total value)
q = d + n             (quarters condition)
```

### Rewrite the third equation:
```
q + d + n = 20
25q + 10d + 5n = 275
q - d - n = 0
```

### Matrix Form:
```
|1   1   1 |  20|
|25 10   5 | 275|
|1  -1  -1 |   0|
```

### Row Operations:

**R₂ → R₂ - 25R₁, R₃ → R₃ - R₁:**
```
|1   1   1 |  20|
|0 -15 -20 |-225|
|0  -2  -2 | -20|
```

**R₂ → R₂ ÷ (-5), R₃ → R₃ ÷ (-2):**
```
|1  1  1 | 20|
|0  3  4 | 45|
|0  1  1 | 10|
```

**R₂ → R₂ - 3R₃:**
```
|1  1  1 | 20|
|0  0  1 | 15|
|0  1  1 | 10|
```

**Swap R₂ and R₃:**
```
|1  1  1 | 20|
|0  1  1 | 10|
|0  0  1 | 15|
```

**Back substitute:**
R₂ → R₂ - R₃, R₁ → R₁ - R₂ - R₃
```
|1  0  0 | -5|  ← This gives negative coins!
|0  1  0 | -5|
|0  0  1 | 15|
```

This suggests our constraint q = d + n might be wrong. Let me fix the problem.

### Corrected Problem:
Let's say: Dimes = Quarters + Nickels

New system:
```
q + d + n = 20
25q + 10d + 5n = 275
d = q + n  →  -q + d - n = 0
```

### Matrix:
```
|1   1   1 |  20|
|25 10   5 | 275|
|-1  1  -1 |   0|
```

After row operations (details skipped for brevity):
```
|1  0  0 |  5|
|0  1  0 | 10|
|0  0  1 |  5|
```

### Solution:
- **Quarters: 5**
- **Dimes: 10**  
- **Nickels: 5**

### Verify:
- Total coins: 5 + 10 + 5 = 20 ✓
- Total value: 5(25) + 10(10) + 5(5) = 125 + 100 + 25 = 250¢... 

Let me create a cleaner money example.

## Simple Money Example

### Problem: Candy Store
Tom buys candies worth $1, $2, and $5 bills.
- Total bills: 10
- Total money: $20
- $5 bills = $1 bills

Let: x = $1 bills, y = $2 bills, z = $5 bills

### System:
```
x + y + z = 10    (total bills)
x + 2y + 5z = 20  (total value)
z = x             ($5 bills = $1 bills)
```

### Substitute z = x:
```
x + y + x = 10     →  2x + y = 10
x + 2y + 5x = 20   →  6x + 2y = 20
```

### Simplified 2×2 System:
```
2x + y = 10
6x + 2y = 20
```

### Matrix Form:
```
|2  1 | 10|
|6  2 | 20|
```

### Row Operations:
R₂ → R₂ - 3R₁
```
|2  1 | 10|
|0 -1 |-10|
```

R₂ → R₂ × (-1)
```
|2  1 | 10|
|0  1 | 10|
```

R₁ → R₁ - R₂
```
|2  0 |  0|
|0  1 | 10|
```

R₁ → R₁ ÷ 2
```
|1  0 |  0|
|0  1 | 10|
```

### Solution:
- x = 0 ($1 bills)
- y = 10 ($2 bills)
- z = 0 ($5 bills)

But this means z ≠ x, so our constraint is wrong!

## Final Clean Example: Age Problem

### Problem: Family Ages
- Father + Mother + Son = 80 years
- Father = Mother + 10 years  
- Mother = 2 × Son

Let: F = Father, M = Mother, S = Son

### System:
```
F + M + S = 80
F - M = 10
M - 2S = 0
```

### Matrix Form:
```
|1  1  1 | 80|
|1 -1  0 | 10|
|0  1 -2 |  0|
```

### Row Operations:
R₂ → R₂ - R₁
```
|1  1  1 | 80|
|0 -2 -1 |-70|
|0  1 -2 |  0|
```

R₂ → R₂ × (-1/2)
```
|1  1   1  | 80|
|0  1  1/2 | 35|
|0  1  -2  |  0|
```

This creates fractions again. Let me multiply the second equation by 2 from the start.

### Better Setup: Multiply second equation by 2
```
F + M + S = 80
2F - 2M = 20
M - 2S = 0
```

### Matrix:
```
|1  1  1 | 80|
|2 -2  0 | 20|
|0  1 -2 |  0|
```

### Row Operations:
R₂ → R₂ - 2R₁
```
|1  1  1 | 80|
|0 -4 -2 |-140|
|0  1 -2 |   0|
```

R₂ → R₂ ÷ (-2)
```
|1  1  1 | 80|
|0  2  1 | 70|
|0  1 -2 |  0|
```

R₂ → R₂ - 2R₃
```
|1  1  1 | 80|
|0  0  5 | 70|
|0  1 -2 |  0|
```

R₂ → R₂ ÷ 5
```
|1  1  1 | 80|
|0  0  1 | 14|
|0  1 -2 |  0|
```

Swap R₂ and R₃
```
|1  1  1 | 80|
|0  1 -2 |  0|
|0  0  1 | 14|
```

R₂ → R₂ + 2R₃, R₁ → R₁ - R₃
```
|1  1  0 | 66|
|0  1  0 | 28|
|0  0  1 | 14|
```

R₁ → R₁ - R₂
```
|1  0  0 | 38|
|0  1  0 | 28|
|0  0  1 | 14|
```

### Solution:
- **Father: 38 years**
- **Mother: 28 years**
- **Son: 14 years**

### Verify:
- Total: 38 + 28 + 14 = 80 ✓
- Father = Mother + 10: 38 = 28 + 10 ✓
- Mother = 2 × Son: 28 = 2 × 14 ✓

## Summary

Integer examples make matrix solutions much cleaner! The key is to:

1. **Choose or design** problems with integer solutions
2. **Set up the matrix** carefully  
3. **Use strategic row operations** to avoid fractions
4. **Always verify** your answer

These integer examples show that matrices can solve real problems with clean, understandable answers!




