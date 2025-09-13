# 3-Variable Equations

## What are 3-Variable Equations?

Equations with three unknowns: **x, y, and z**

### General Form:
```
ax + by + cz = d
```

Where a, b, c, d are constants.

## Simple Examples

### Example 1: Basic Linear Equation
```
x + y + z = 10
```
**Meaning:** Three numbers that add up to 10

**Some solutions:**
- x = 1, y = 2, z = 7
- x = 0, y = 5, z = 5  
- x = 3, y = 3, z = 4

### Example 2: With Coefficients
```
2x + 3y + z = 12
```
**Solutions include:**
- x = 1, y = 2, z = 4 → 2(1) + 3(2) + 4 = 12 ✓
- x = 0, y = 4, z = 0 → 2(0) + 3(4) + 0 = 12 ✓

## Geometric Interpretation

Each 3-variable equation represents a **PLANE** in 3D space.

### Visualization:
```
        z
        ↑
        |     🔵 PLANE: x + y + z = 6
        |    ╱│╲
        |   ╱ │ ╲ Every point (x,y,z) on this
        |  ╱  │  ╲ plane satisfies the equation
        | ╱   │   ╲
        |╱    │    ╲
   ────●──────┼─────●───→ y
       ╱      │    ╱
      ╱       │   ╱
     ╱        │  ╱
    ↙         │ ╱
             x
```

## Types of 3-Variable Equations

### Type 1: All Variables Present
```
2x + 3y + 4z = 24
```

### Type 2: Missing Variables
```
x + y = 5        (no z term)
2z = 8           (only z term)
3x + z = 10      (no y term)
```

### Type 3: Special Forms
```
x + y + z = 0    (sum equals zero)
x² + y² + z² = 9 (non-linear - sphere)
```

## Finding Solutions

### Method 1: Guess and Check
For: x + 2y + z = 8

**Try different values:**
- Let x = 0, y = 1 → z = 6 
  Check: 0 + 2(1) + 6 = 8 ✓
- Let x = 2, y = 2 → z = 2
  Check: 2 + 2(2) + 2 = 8 ✓

### Method 2: Express One Variable
From: 3x + y + 2z = 12

**Solve for z:**
```
2z = 12 - 3x - y
z = (12 - 3x - y)/2
```

Now choose any x and y, calculate z.

## Real-World Examples

### Example 1: Shopping Problem
```
Apples + Bananas + Oranges = 10 fruits total
2A + B + 3O = 15 dollars total cost
```

### Example 2: Mixture Problem
```
Red paint + Blue paint + White paint = 5 gallons
R + B + W = 5
```

### Example 3: Time Allocation
```
Study + Work + Sleep = 24 hours per day
S + W + L = 24
```

## Working with Multiple Equations

Usually, we need **THREE equations** to find unique values for three variables.

### System Example:
```
x + y + z = 6     (Equation 1)
2x - y + z = 3    (Equation 2)  
x + 2y - z = 1    (Equation 3)
```

Each equation is a plane. The solution is where all three planes meet.

### Visual Intersection:
```
        z
        |
        |   🔴 Plane 1
        |  ╱ ╲🔵 Plane 2
        | ╱   ╲ ╲
        |╱  ●  ╲ ╲🟢 Plane 3
   ────●────────╲─●──→ y
       ╱         ╲╱
      ╱           ●
     ╱
    x
    
● = Intersection point = Solution (x,y,z)
```

## Solution Scenarios

### Scenario 1: Unique Solution
Three planes meet at exactly one point.
```
x = 3, y = 1, z = 2
```

### Scenario 2: No Solution  
Three planes don't have a common intersection point.
```
Inconsistent system - no solution exists
```

### Scenario 3: Infinite Solutions
All three planes intersect along a line or are the same plane.
```
Infinitely many solutions exist
```

## Quick Examples by Variable Isolation

### Isolate x:
From: 3x + 2y + z = 15
```
3x = 15 - 2y - z
x = (15 - 2y - z)/3
```

### Isolate y:
From: x + 4y + 2z = 20
```
4y = 20 - x - 2z  
y = (20 - x - 2z)/4
```

### Isolate z:
From: 2x + y + 5z = 25
```
5z = 25 - 2x - y
z = (25 - 2x - y)/5
```

## Common Patterns

### Pattern 1: Sum Equation
```
x + y + z = constant
```
Many solutions possible - choose two variables freely.

### Pattern 2: Weighted Sum  
```
2x + 3y + 4z = constant
```
Different "weights" for each variable.

### Pattern 3: Mixed Signs
```
x - y + z = constant
2x + y - 3z = constant
```
Some coefficients positive, some negative.

## Checking Solutions

### Always verify by substitution!

**Given solution:** x = 2, y = 1, z = 3
**Check in:** 2x + y + z = 8

```
2(2) + 1 + 3 = 4 + 1 + 3 = 8 ✓
```

## Tips 

### 1. Start Simple
```
x + y + z = 9
Try: x = 3, y = 3, z = 3
```

### 2. Use Substitution
```
If x + y + z = 10 and x = 4
Then: 4 + y + z = 10
So: y + z = 6
```

### 3. Check Your Work
Always substitute back into the original equation!

### 4. Look for Patterns
```
2x + 2y + 2z = 12
Divide by 2: x + y + z = 6
```

## Summary

3-Variable equations are:
- **Planes in 3D space**
- **Have infinite solutions** individually  
- **Need 3 equations** for unique solution
- **Useful for real-world problems** with three constraints
- **Solved systematically** using matrix methods

**Next step:** Learn to solve systems of three equations with three unknowns!