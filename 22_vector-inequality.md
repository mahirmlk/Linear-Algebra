# Cauchy-Schwarz Inequality and Vector Triangle Inequality

## Introduction

The **Cauchy-Schwarz inequality** and **vector triangle inequality** are fundamental results in linear algebra that provide important bounds on vector operations. These inequalities have deep geometric meaning and wide applications in mathematics and engineering.

---

# Cauchy-Schwarz Inequality

## Statement

For any two vectors $\vec{a}$ and $\vec{b}$ in $\mathbb{R}^n$:

$$|\vec{a} \cdot \vec{b}| \leq |\vec{a}||\vec{b}|$$

**Equality holds if and only if** $\vec{a}$ and $\vec{b}$ are linearly dependent (i.e., one is a scalar multiple of the other).

## Alternative Forms

### Form 1: Component-wise
For vectors $\vec{a} = (a_1, a_2, \ldots, a_n)$ and $\vec{b} = (b_1, b_2, \ldots, b_n)$:

$$\left|\sum_{i=1}^{n} a_i b_i\right| \leq \sqrt{\sum_{i=1}^{n} a_i^2} \sqrt{\sum_{i=1}^{n} b_i^2}$$

### Form 2: Using Dot Product
$$(\vec{a} \cdot \vec{b})^2 \leq (\vec{a} \cdot \vec{a})(\vec{b} \cdot \vec{b})$$

## Geometric Interpretation

The Cauchy-Schwarz inequality states that the absolute value of the dot product of two vectors is at most the product of their magnitudes. This makes sense because:

$$\vec{a} \cdot \vec{b} = |\vec{a}||\vec{b}|\cos\theta$$

Since $|\cos\theta| \leq 1$, we have:
$$|\vec{a} \cdot \vec{b}| = |\vec{a}||\vec{b}||\cos\theta| \leq |\vec{a}||\vec{b}|$$

## Examples

### Example 1: 2D Vectors

Let $\vec{a} = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$

**Verification:**
- Left side: $|\vec{a} \cdot \vec{b}| = |(3)(1) + (4)(2)| = |3 + 8| = 11$
- Right side: $|\vec{a}||\vec{b}| = \sqrt{3^2 + 4^2} \cdot \sqrt{1^2 + 2^2} = 5 \cdot \sqrt{5} \approx 11.18$

Since $11 \leq 11.18$ ✓, the inequality holds.

### Example 2: 3D Vectors

Let $\vec{u} = \begin{pmatrix} 1 \\ -2 \\ 3 \end{pmatrix}$ and $\vec{v} = \begin{pmatrix} 2 \\ 1 \\ -1 \end{pmatrix}$

**Verification:**
- Left side: $|\vec{u} \cdot \vec{v}| = |(1)(2) + (-2)(1) + (3)(-1)| = |2 - 2 - 3| = 3$
- Right side: $|\vec{u}||\vec{v}| = \sqrt{1^2 + (-2)^2 + 3^2} \cdot \sqrt{2^2 + 1^2 + (-1)^2} = \sqrt{14} \cdot \sqrt{6} \approx 9.17$

Since $3 \leq 9.17$ ✓, the inequality holds.

### Example 3: Equality Case

Let $\vec{p} = \begin{pmatrix} 2 \\ 4 \end{pmatrix}$ and $\vec{q} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$ (Note: $\vec{p} = 2\vec{q}$)

**Verification:**
- Left side: $|\vec{p} \cdot \vec{q}| = |(2)(1) + (4)(2)| = |2 + 8| = 10$
- Right side: $|\vec{p}||\vec{q}| = \sqrt{2^2 + 4^2} \cdot \sqrt{1^2 + 2^2} = \sqrt{20} \cdot \sqrt{5} = 2\sqrt{5} \cdot \sqrt{5} = 10$

Since $10 = 10$ ✓, equality holds (as expected since the vectors are linearly dependent).

## Proof

# Cauchy–Schwarz Inequality -


**Statement.**  
For vectors $\mathbf{u}, \mathbf{v} \in \mathbb{R}^n$ we have the inequality

$\langle \mathbf{u}, \mathbf{v} \rangle| \leq \|\mathbf{u}\|\,\|\mathbf{v}\|$


**Inner product and norm (inline).**  
Here, $\langle \mathbf{u},\mathbf{v}\rangle = \sum_{i=1}^n u_i v_i $ and $ |\mathbf{u}\| = \sqrt{\langle \mathbf{u},\mathbf{u}\rangle} $

---

## Proof (using nonnegativity)

Consider the scalar function of $(t\in\mathbb{R})$:
$$
f(t) = \|\mathbf{u} - t\mathbf{v}\|^2.
$$
Since norms are nonnegative, we have $( f(t) \ge 0 )$ for all real \(t\). Expand \(f(t)\) using the inner product:
$$
\begin{aligned}
f(t)
&= \langle \mathbf{u} - t\mathbf{v}, \mathbf{u} - t\mathbf{v} \rangle \\
&= \langle \mathbf{u},\mathbf{u}\rangle - 2t\langle \mathbf{u},\mathbf{v}\rangle + t^2\langle \mathbf{v},\mathbf{v}\rangle \\
&= \|\mathbf{u}\|^2 - 2t\langle \mathbf{u},\mathbf{v}\rangle + t^2\|\mathbf{v}\|^2.
\end{aligned}
$$

Thus \(f(t)\) is the quadratic
$$
f(t) = \|\mathbf{v}\|^2 t^2 - 2\langle \mathbf{u},\mathbf{v}\rangle t + \|\mathbf{u}\|^2 \ge 0 \quad\text{for all } t\in\mathbb{R}.
$$

A real quadratic $(at^2+bt+c)$ is nonnegative for all \(t\) iff its discriminant satisfies $(b^2 - 4ac \le 0)$. Here $(a=\|\mathbf{v}\|^2)$, $(b=-2\langle \mathbf{u},\mathbf{v}\rangle)$, $(c=\|\mathbf{u}\|^2)$. Hence
$$
\begin{aligned}
0 &\ge b^2 - 4ac \\
  &= \big(-2\langle \mathbf{u},\mathbf{v}\rangle\big)^2 - 4\|\mathbf{v}\|^2\|\mathbf{u}\|^2 \\
  &= 4\langle \mathbf{u},\mathbf{v}\rangle^2 - 4\|\mathbf{u}\|^2\|\mathbf{v}\|^2.
\end{aligned}
$$

Dividing by \(4\) gives
$$
\langle \mathbf{u},\mathbf{v}\rangle^2 \le \|\mathbf{u}\|^2 \|\mathbf{v}\|^2,
$$
and taking square roots yields the desired result:
$$
\boxed{\;|\langle \mathbf{u},\mathbf{v}\rangle| \le \|\mathbf{u}\|\,\|\mathbf{v}\|\;}.
$$

---



---

# Vector Triangle Inequality

## Statement

For any two vectors $\vec{a}$ and $\vec{b}$ in $\mathbb{R}^n$:

$$|\vec{a} + \vec{b}| \leq |\vec{a}| + |\vec{b}|$$

**Equality holds if and only if** one vector is a non-negative scalar multiple of the other.

## Geometric Interpretation

The triangle inequality states that the length of the sum of two vectors is at most the sum of their lengths. This is called the "triangle inequality" because it corresponds to the fact that in any triangle, the length of one side is at most the sum of the lengths of the other two sides.

## Simple Examples

### Example 1: 2D Vectors

Let $\vec{a} = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$

**Verification:**
- Left side: $|\vec{a} + \vec{b}| = |\begin{pmatrix} 4 \\ 6 \end{pmatrix}| = \sqrt{4^2 + 6^2} = \sqrt{52} \approx 7.21$
- Right side: $|\vec{a}| + |\vec{b}| = \sqrt{3^2 + 4^2} + \sqrt{1^2 + 2^2} = 5 + \sqrt{5} \approx 7.24$

Since $7.21 \leq 7.24$ ✓, the inequality holds.

### Example 2: 3D Vectors

Let $\vec{u} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ and $\vec{v} = \begin{pmatrix} 2 \\ 1 \\ 1 \end{pmatrix}$

**Verification:**
- Left side: $|\vec{u} + \vec{v}| = |\begin{pmatrix} 3 \\ 3 \\ 4 \end{pmatrix}| = \sqrt{3^2 + 3^2 + 4^2} = \sqrt{34} \approx 5.83$
- Right side: $|\vec{u}| + |\vec{v}| = \sqrt{1^2 + 2^2 + 3^2} + \sqrt{2^2 + 1^2 + 1^2} = \sqrt{14} + \sqrt{6} \approx 6.32$

Since $5.83 \leq 6.32$ ✓, the inequality holds.

### Example 3: Equality Case

Let $\vec{p} = \begin{pmatrix} 2 \\ 4 \end{pmatrix}$ and $\vec{q} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$ (Note: $\vec{p} = 2\vec{q}$)

**Verification:**
- Left side: $|\vec{p} + \vec{q}| = |\begin{pmatrix} 3 \\ 6 \end{pmatrix}| = \sqrt{3^2 + 6^2} = \sqrt{45} = 3\sqrt{5}$
- Right side: $|\vec{p}| + |\vec{q}| = \sqrt{2^2 + 4^2} + \sqrt{1^2 + 2^2} = \sqrt{20} + \sqrt{5} = 2\sqrt{5} + \sqrt{5} = 3\sqrt{5}$

Since $3\sqrt{5} = 3\sqrt{5}$ ✓, equality holds (as expected since the vectors are in the same direction).

## Proof Using Cauchy-Schwarz

Starting with:
$$|\vec{a} + \vec{b}|^2 = (\vec{a} + \vec{b}) \cdot (\vec{a} + \vec{b})$$
$$|\vec{a} + \vec{b}|^2 = |\vec{a}|^2 + 2(\vec{a} \cdot \vec{b}) + |\vec{b}|^2$$

Using Cauchy-Schwarz inequality: $|\vec{a} \cdot \vec{b}| \leq |\vec{a}||\vec{b}|$

Since $\vec{a} \cdot \vec{b} \leq |\vec{a} \cdot \vec{b}| \leq |\vec{a}||\vec{b}|$:

$$|\vec{a} + \vec{b}|^2 \leq |\vec{a}|^2 + 2|\vec{a}||\vec{b}| + |\vec{b}|^2$$
$$|\vec{a} + \vec{b}|^2 \leq (|\vec{a}| + |\vec{b}|)^2$$

Taking square roots:
$$|\vec{a} + \vec{b}| \leq |\vec{a}| + |\vec{b}|$$

## Extended Triangle Inequality

For any number of vectors:
$$|\vec{a}_1 + \vec{a}_2 + \cdots + \vec{a}_n| \leq |\vec{a}_1| + |\vec{a}_2| + \cdots + |\vec{a}_n|$$


---


# Summary

## Key Takeaways

1. **Cauchy-Schwarz Inequality**: $|\vec{a} \cdot \vec{b}| \leq |\vec{a}||\vec{b}|$
   - Provides bounds on dot products
   - Equality when vectors are linearly dependent
   - Fundamental in many mathematical proofs

2. **Vector Triangle Inequality**: $|\vec{a} + \vec{b}| \leq |\vec{a}| + |\vec{b}|$
   - Provides bounds on vector sums
   - Equality when vectors are in the same direction
   - Essential for defining distance metrics

3. **Geometric Meaning**:
   - Cauchy-Schwarz: Limits the "alignment" of vectors
   - Triangle Inequality: Limits the "combined length" of vectors

4. **Applications**: Both inequalities are fundamental in:
   - Mathematical analysis
   - Optimization theory
   - Signal processing
   - Machine learning
   - Physics and engineering
