# Matrix-Vector Products as Linear Transformations

A **linear transformation** is a function $T: \mathbb{R}^n \to \mathbb{R}^m$ that preserves vector addition and scalar multiplication. Every linear transformation can be represented as a matrix-vector product.

## Concept

For a matrix $A \in \mathbb{R}^{m \times n}$ and vector $\mathbf{x} \in \mathbb{R}^n$, the product $A\mathbf{x}$ defines a linear transformation:

$$T(\mathbf{x}) = A\mathbf{x}$$

This transformation maps vectors from $\mathbb{R}^n$ to $\mathbb{R}^m$.

## Properties of Linear Transformations

A transformation $T$ is linear if and only if:

1. **Additivity**: $T(\mathbf{u} + \mathbf{v}) = T(\mathbf{u}) + T(\mathbf{v})$
2. **Homogeneity**: $T(c\mathbf{u}) = cT(\mathbf{u})$ for any scalar $c$

These can be combined as: $T(c\mathbf{u} + d\mathbf{v}) = cT(\mathbf{u}) + dT(\mathbf{v})$

## Example 1: 2D Rotation

A rotation by angle $\theta$ counterclockwise is given by:

$$A = \begin{bmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{bmatrix}$$

For $\theta = 90°$ (or $\frac{\pi}{2}$ radians):

$$A = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$$

Applying this to vector $\mathbf{x} = \begin{bmatrix} 3 \\ 2 \end{bmatrix}$:

$$A\mathbf{x} = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} 3 \\ 2 \end{bmatrix} = \begin{bmatrix} 0(3) + (-1)(2) \\ 1(3) + 0(2) \end{bmatrix} = \begin{bmatrix} -2 \\ 3 \end{bmatrix}$$

The point $(3, 2)$ rotates to $(-2, 3)$.

## Example 2: 2D Scaling

A scaling transformation that stretches by factor $s_x$ horizontally and $s_y$ vertically:

$$A = \begin{bmatrix} s_x & 0 \\ 0 & s_y \end{bmatrix}$$

With $s_x = 3$ and $s_y = 2$:

$$A = \begin{bmatrix} 3 & 0 \\ 0 & 2 \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} 1 \\ 4 \end{bmatrix}$$

$$A\mathbf{x} = \begin{bmatrix} 3 & 0 \\ 0 & 2 \end{bmatrix} \begin{bmatrix} 1 \\ 4 \end{bmatrix} = \begin{bmatrix} 3 \\ 8 \end{bmatrix}$$

## Example 3: Projection onto a Line

Projection onto the $x$-axis (setting $y$-coordinate to zero):

$$P = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}$$

For $\mathbf{x} = \begin{bmatrix} 5 \\ 7 \end{bmatrix}$:

$$P\mathbf{x} = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} 5 \\ 7 \end{bmatrix} = \begin{bmatrix} 5 \\ 0 \end{bmatrix}$$

## Example 4: Reflection

Reflection across the $x$-axis (negating $y$-coordinate):

$$R = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$$

For $\mathbf{x} = \begin{bmatrix} 4 \\ 3 \end{bmatrix}$:

$$R\mathbf{x} = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix} \begin{bmatrix} 4 \\ 3 \end{bmatrix} = \begin{bmatrix} 4 \\ -3 \end{bmatrix}$$

## Example 5: General 3D to 2D Transformation

Consider $T: \mathbb{R}^3 \to \mathbb{R}^2$ defined by:

$$A = \begin{bmatrix} 2 & 1 & -1 \\ 0 & 3 & 2 \end{bmatrix}$$

For $\mathbf{x} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$:

$$A\mathbf{x} = \begin{bmatrix} 2 & 1 & -1 \\ 0 & 3 & 2 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 2(1) + 1(2) + (-1)(3) \\ 0(1) + 3(2) + 2(3) \end{bmatrix} = \begin{bmatrix} 1 \\ 12 \end{bmatrix}$$

## Matrix Columns as Transformed Basis Vectors

A key insight: The columns of matrix $A$ tell us where the standard basis vectors go under transformation $T$.

For $A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}$:

- $T(\mathbf{e}_1) = T\left(\begin{bmatrix} 1 \\ 0 \end{bmatrix}\right) = \begin{bmatrix} a_{11} \\ a_{21} \end{bmatrix}$ (first column)

- $T(\mathbf{e}_2) = T\left(\begin{bmatrix} 0 \\ 1 \end{bmatrix}\right) = \begin{bmatrix} a_{12} \\ a_{22} \end{bmatrix}$ (second column)

For any vector $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = x_1\mathbf{e}_1 + x_2\mathbf{e}_2$:

$$T(\mathbf{x}) = x_1 T(\mathbf{e}_1) + x_2 T(\mathbf{e}_2)$$

This is a **linear combination** of the matrix columns!

## Composition of Transformations

If $T_1(\mathbf{x}) = A\mathbf{x}$ and $T_2(\mathbf{y}) = B\mathbf{y}$, then their composition is:

$$(T_2 \circ T_1)(\mathbf{x}) = T_2(T_1(\mathbf{x})) = B(A\mathbf{x}) = (BA)\mathbf{x}$$

The composition corresponds to matrix multiplication!

### Example: Rotation followed by Scaling

$$\text{Scale: } S = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}, \quad \text{Rotate 90°: } R = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$$

$$SR = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix} \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} = \begin{bmatrix} 0 & -2 \\ 3 & 0 \end{bmatrix}$$

Apply to $\mathbf{x} = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$:

$$(SR)\mathbf{x} = \begin{bmatrix} 0 & -2 \\ 3 & 0 \end{bmatrix} \begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} -2 \\ 3 \end{bmatrix}$$

---

Matrix-vector multiplication $A\mathbf{x}$ represents a linear transformation where:

- The matrix $A$ completely determines the transformation
- Columns of $A$ show where basis vectors are mapped
- The transformation preserves linearity properties
- Composition of transformations corresponds to matrix multiplication

---
---

# Linear Transformations as Matrix–Vector Products

In linear algebra, **every linear transformation** $T : \mathbb{R}^n \to \mathbb{R}^m$ can be represented as **matrix–vector multiplication**:

$$
T(\mathbf{x}) = A \mathbf{x}
$$

for some matrix $A \in \mathbb{R}^{m \times n}$.


---

## From linear transformation to matrix

Consider the **standard basis** of $\mathbb{R}^n$:

$$
\mathbf{e}_1 = \begin{bmatrix}1 \\ 0 \\ \vdots \\ 0\end{bmatrix},\quad
\mathbf{e}_2 = \begin{bmatrix}0 \\ 1 \\ \vdots \\ 0\end{bmatrix},\quad
\dots,\quad
\mathbf{e}_n = \begin{bmatrix}0 \\ 0 \\ \vdots \\ 1\end{bmatrix}.
$$

If $T : \mathbb{R}^n \to \mathbb{R}^m$ is linear, define the matrix $A$ by:

$$
A = \begin{bmatrix} T(\mathbf{e}_1) & T(\mathbf{e}_2) & \cdots & T(\mathbf{e}_n) \end{bmatrix}.
$$

So the **$j$-th column** of $A$ is:

$$
\mathbf{a}_j = T(\mathbf{e}_j), \quad j = 1,2,\dots,n.
$$

Then for any vector $\mathbf{x} \in \mathbb{R}^n$,

$$
\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}
\quad\Rightarrow\quad
T(\mathbf{x}) = A\mathbf{x} = x_1 T(\mathbf{e}_1) + x_2 T(\mathbf{e}_2) + \cdots + x_n T(\mathbf{e}_n).
$$

So **knowing $T$ on the basis vectors uniquely determines the matrix**.

---

## Example 1 — Building a matrix from a formula

Let $T : \mathbb{R}^2 \to \mathbb{R}^2$ be defined by

$$
T(x, y) = (2x - y,\; x + 3y).
$$

### Write in vector form

$$
T\left(\begin{bmatrix} x \\ y \end{bmatrix}\right)
  = \begin{bmatrix}
      2x - y \\
      x + 3y
    \end{bmatrix}.
$$

We want a matrix $A$ such that

$$
T(\mathbf{x}) = A\mathbf{x}.
$$

### Use images of basis vectors

Take the standard basis of $\mathbb{R}^2$:

$$
\mathbf{e}_1 = \begin{bmatrix}1 \\ 0\end{bmatrix}, \quad
\mathbf{e}_2 = \begin{bmatrix}0 \\ 1\end{bmatrix}.
$$

Compute:

$$
T(\mathbf{e}_1) =
T(1, 0) = (2\cdot 1 - 0,\; 1 + 3\cdot 0) = (2, 1),
$$

$$
T(\mathbf{e}_2) =
T(0, 1) = (2\cdot 0 - 1,\; 0 + 3\cdot 1) = (-1, 3).
$$

So the matrix of $T$ is

$$
A = \begin{bmatrix}
2 & -1 \\
1 & 3
\end{bmatrix},
$$

where the first column is $T(\mathbf{e}_1)$ and the second is $T(\mathbf{e}_2)$.

### Check on a sample vector

Let $\mathbf{x} = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$.

1. Using the formula:

$$
T(2, -1) = (2\cdot 2 - (-1),\; 2 + 3(-1)) = (4 + 1,\; 2 - 3) = (5, -1).
$$

2. Using the matrix:

$$
A\mathbf{x}
  = \begin{bmatrix}
      2 & -1 \\
      1 & 3
    \end{bmatrix}
    \begin{bmatrix}2 \\ -1\end{bmatrix}
  = \begin{bmatrix}
      2\cdot 2 + (-1)\cdot(-1) \\
      1\cdot 2 + 3\cdot(-1)
    \end{bmatrix}
  = \begin{bmatrix}
      4 + 1 \\
      2 - 3
    \end{bmatrix}
  = \begin{bmatrix}
      5 \\
     -1
    \end{bmatrix}.
$$

They match, so $T(\mathbf{x}) = A\mathbf{x}$.

---

## Example 2 — Given action on basis vectors

Suppose $T : \mathbb{R}^2 \to \mathbb{R}^2$ satisfies:

$$
T(\mathbf{e}_1) = \begin{bmatrix} 3 \\ 1 \end{bmatrix},
\quad
T(\mathbf{e}_2) = \begin{bmatrix} -2 \\ 4 \end{bmatrix}.
$$

### Build the matrix

Place these as columns:

$$
A = \begin{bmatrix}
3 & -2 \\
1 & 4
\end{bmatrix}.
$$

Then for any $\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}$,

$$
T(\mathbf{x}) = A\mathbf{x}
= x\,T(\mathbf{e}_1) + y\,T(\mathbf{e}_2)
= x\begin{bmatrix}3 \\ 1\end{bmatrix} + y\begin{bmatrix}-2 \\ 4\end{bmatrix}.
$$

### Test on a vector

Take $\mathbf{x} = \begin{bmatrix}1 \\ 2\end{bmatrix}$.

$$
T(\mathbf{x}) = A\mathbf{x}
  = \begin{bmatrix}
      3 & -2 \\
      1 & 4
    \end{bmatrix}
    \begin{bmatrix}
      1 \\
      2
    \end{bmatrix}
  = \begin{bmatrix}
      3\cdot 1 + (-2)\cdot 2 \\
      1\cdot 1 + 4\cdot 2
    \end{bmatrix}
  = \begin{bmatrix}
      3 - 4 \\
      1 + 8
    \end{bmatrix}
  = \begin{bmatrix}
     -1 \\
      9
    \end{bmatrix}.
$$

So the linear transformation is fully captured by the matrix $A$.

---

## Example 3 — Non-square: $\mathbb{R}^2 \to \mathbb{R}^3$

Let $T : \mathbb{R}^2 \to \mathbb{R}^3$ be defined by its action on basis vectors:

$$
T(\mathbf{e}_1) = \begin{bmatrix}1 \\ 0 \\ 2\end{bmatrix},
\quad
T(\mathbf{e}_2) = \begin{bmatrix}-1 \\ 3 \\ 4\end{bmatrix}.
$$

### Build the matrix

$$
A = \begin{bmatrix}
1 & -1 \\
0 & 3  \\
2 & 4
\end{bmatrix}.
$$

### Apply $T$ to a vector

For $\mathbf{x} = \begin{bmatrix} a \\ b \end{bmatrix}$,

$$
T(\mathbf{x}) = A\mathbf{x}
  = \begin{bmatrix}
      1 & -1 \\
      0 & 3  \\
      2 & 4
    \end{bmatrix}
    \begin{bmatrix}
      a \\
      b
    \end{bmatrix}
  = \begin{bmatrix}
      a - b \\
      3b \\
      2a + 4b
    \end{bmatrix}.
$$

You can also see this as

$$
T(\mathbf{x}) = a\,T(\mathbf{e}_1) + b\,T(\mathbf{e}_2).
$$

---

## Example 4 — Rotation as a linear transformation

Consider the **90° counterclockwise rotation** $R : \mathbb{R}^2 \to \mathbb{R}^2$.

We know that:

- $R(1,0) = (0,1)$
- $R(0,1) = (-1,0)$

So

$$
R(\mathbf{e}_1) = \begin{bmatrix}0 \\ 1\end{bmatrix},
\quad
R(\mathbf{e}_2) = \begin{bmatrix}-1 \\ 0\end{bmatrix}.
$$

Thus the matrix is

$$
R = \begin{bmatrix}
0 & -1 \\
1 & 0
\end{bmatrix}.
$$

For any vector $\mathbf{x} = \begin{bmatrix}x \\ y\end{bmatrix}$,

$$
R\mathbf{x}
  = \begin{bmatrix}
      0 & -1 \\
      1 & 0
    \end{bmatrix}
    \begin{bmatrix}
      x \\
      y
    \end{bmatrix}
  = \begin{bmatrix}
      -y \\
      x
    \end{bmatrix},
$$

which is exactly the formula for a 90° rotation.

---

1. **Start with a linear transformation** $T : \mathbb{R}^n \to \mathbb{R}^m$.
2. **Check linearity** (additivity + homogeneity).
3. **Compute images of basis vectors** $T(\mathbf{e}_1), \dots, T(\mathbf{e}_n)$.
4. **Build the matrix** $A$ by using these images as columns.
5. **Use matrix–vector products**:
   $$
   T(\mathbf{x}) = A\mathbf{x}
   $$
   for any $\mathbf{x} \in \mathbb{R}^n$.
