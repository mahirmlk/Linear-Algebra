# Matrices to Solve Vector Combination Problems

## What is a Vector Combination Problem?

A vector combination problem asks: "Can we write vector **b** as a combination of vectors **v₁, v₂, ..., vₙ**?"

In other words: **c₁v₁ + c₂v₂ + ... + cₙvₙ = b**

Find the coefficients c₁, c₂, ..., cₙ.

## Matrix Connection

This is equivalent to solving: **Ax = b**

Where:
- **A** = [v₁ | v₂ | ... | vₙ] (vectors as columns)
- **x** = [c₁, c₂, ..., cₙ]ᵀ (coefficients we want to find)
- **b** = target vector

## Simple 2D Example

### Problem: Express b = [7, 1] as a combination of v₁ = [2, 1] and v₂ = [1, 3]

**Question:** Find c₁ and c₂ such that:
```
c₁[2] + c₂[1] = [7]
  [1]    [3]   [1]
```

### Visual Representation:
```
     y
     |
   3 |     v₂ = [1,3]
     |    /
   2 |   /
     |  /
   1 |_/____ x
     | /  1  2  3
     |/
     v₁ = [2,1]

Target: b = [7,1]
We need: c₁v₁ + c₂v₂ = b
```

### Step 1: Set Up Matrix Equation
```
|2  1| |c₁|   |7|
|1  3| |c₂| = |1|
```

### Step 2: Solve Using Row Operations
```
|2  1 | 7|
|1  3 | 1|
```

**R₁ → (1/2)R₁:**
```
|1  1/2 | 7/2|
|1   3  |  1 |
```

**R₂ → R₂ - R₁:**
```
|1  1/2 | 7/2|
|0  5/2 |-5/2|
```

**R₂ → (2/5)R₂:**
```
|1  1/2 | 7/2|
|0   1  | -1 |
```

**R₁ → R₁ - (1/2)R₂:**
```
|1   0  |  4|
|0   1  | -1|
```

### Step 3: Read Solution
```
c₁ = 4
c₂ = -1
```

### Step 4: Verify
```
4[2] + (-1)[1] = [8] + [-1] = [7] ✓
 [1]      [3]   [4]   [-3]   [1]
```

**Answer:** b = 4v₁ - v₂

## 3D Example

### Problem: Can b = [5, 2, 8] be written as a combination of:
- v₁ = [1, 0, 1]
- v₂ = [2, 1, 1]  
- v₃ = [1, 1, 2]

### Visual Setup:
```
In 3D space, we want:
c₁[1] + c₂[2] + c₃[1] = [5]
  [0]    [1]    [1]   [2]
  [1]    [1]    [2]   [8]
```

### Step 1: Matrix Form
```
|1  2  1| |c₁|   |5|
|0  1  1| |c₂| = |2|
|1  1  2| |c₃|   |8|
```

### Step 2: Augmented Matrix and Row Operations
```
|1  2  1 | 5|
|0  1  1 | 2|
|1  1  2 | 8|
```

**R₃ → R₃ - R₁:**
```
|1  2  1 | 5|
|0  1  1 | 2|
|0 -1  1 | 3|
```

**R₃ → R₃ + R₂:**
```
|1  2  1 | 5|
|0  1  1 | 2|
|0  0  2 | 5|
```

**R₃ → (1/2)R₃:**
```
|1  2  1 | 5  |
|0  1  1 | 2  |
|0  0  1 | 5/2|
```

**R₂ → R₂ - R₃, R₁ → R₁ - R₃:**
```
|1  2  0 | 5/2|
|0  1  0 |-1/2|
|0  0  1 | 5/2|
```

**R₁ → R₁ - 2R₂:**
```
|1  0  0 | 7/2|
|0  1  0 |-1/2|
|0  0  1 | 5/2|
```

### Step 3: Solution
```
c₁ = 7/2 = 3.5
c₂ = -1/2 = -0.5
c₃ = 5/2 = 2.5
```

### Verification:
```
3.5[1] + (-0.5)[2] + 2.5[1] = [3.5] + [-1] + [2.5] = [5] ✓
   [0]         [1]       [1]   [0]    [-0.5]  [2.5]   [2]
   [1]         [1]       [2]   [3.5]  [-0.5]  [5]     [8]
```

## When No Solution Exists

### Problem: Express b = [1, 2, 3] using v₁ = [1, 2, 2] and v₂ = [2, 4, 4]

**Notice:** v₂ = 2v₁ (vectors are linearly dependent!)

### Matrix Setup:
```
|1  2| |c₁|   |1|
|2  4| |c₂| = |2|
|2  4|        |3|
```

### Row Operations:
```
|1  2 | 1|
|2  4 | 2|
|2  4 | 3|
```

**R₂ → R₂ - 2R₁, R₃ → R₃ - 2R₁:**
```
|1  2 | 1|
|0  0 | 0|
|0  0 | 1|  ← This means 0 = 1 (impossible!)
```

**Conclusion:** No solution exists. Vector b cannot be expressed as a combination of v₁ and v₂.

## When Infinite Solutions Exist

### Problem: Express b = [3, 6, 6] using v₁ = [1, 2, 2] and v₂ = [2, 4, 4]

### Matrix Setup:
```
|1  2 | 3|
|2  4 | 6|
|2  4 | 6|
```

### After Row Operations:
```
|1  2 | 3|
|0  0 | 0|
|0  0 | 0|
```

**Solution:** c₁ + 2c₂ = 3, so c₁ = 3 - 2c₂

Let c₂ = t (any real number), then:
- c₁ = 3 - 2t
- c₂ = t

**Answer:** Infinite solutions: b = (3-2t)v₁ + tv₂

## Practical Applications

### Example 1: Force Vectors in Physics
Two forces F₁ = [3, 4] N and F₂ = [1, -2] N act on an object.
What combination creates a resultant force R = [7, 0] N?

**Setup:**
```
c₁[3] + c₂[1] = [7]
  [4]    [-2]   [0]
```

**Matrix:**
```
|3   1 | 7|
|4  -2 | 0|
```

**Solution:** c₁ = 2, c₂ = 1
**Answer:** R = 2F₁ + F₂

