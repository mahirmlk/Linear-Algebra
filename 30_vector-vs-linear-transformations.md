### Vector Transformation (General Mapping)

A **vector transformation** is any rule that takes an input vector and returns another vector:

$$
T:\mathbb{R}^n \rightarrow \mathbb{R}^m,\quad \vec{y}=T(\vec{x})
$$

No algebraic structure is required beyond being a well-defined function. Examples can bend, scale, or wrap space in arbitrary ways.

#### Example: Nonlinear Polar Stretch

Let $\vec{x}=(x_1,x_2)$. Define

$$
T(\vec{x})=
\begin{pmatrix}
x_1^2-x_2^2\\
2x_1x_2
\end{pmatrix}
=
\begin{pmatrix}
r^2\cos(2\theta)\\
r^2\sin(2\theta)
\end{pmatrix},
\quad r=\sqrt{x_1^2+x_2^2},\;\theta=\arctan2(x_2,x_1)
$$

This wraps each input vector around the origin and stretches it by $r^2$. It respects continuity but **is not linear** because:

$$
T(\vec{x}+\vec{z}) \neq T(\vec{x})+T(\vec{z}),\qquad
T(c\vec{x}) \neq c\,T(\vec{x})
$$

### Linear Transformation (Structure-Preserving)

A **linear transformation** is a special vector transformation that satisfies both additivity and homogeneity:

$$
L(\vec{x}+\vec{z}) = L(\vec{x}) + L(\vec{z}),\qquad
L(c\vec{x}) = c\,L(\vec{x})
$$

Linear transformations between finite-dimensional spaces are exactly the mappings that can be represented by a matrix:

$$
L(\vec{x}) = A\vec{x},\quad A\in\mathbb{R}^{m\times n}
$$

#### Example: Shear in the Plane

Let

$$
A =
\begin{pmatrix}
1 & k\\
0 & 1
\end{pmatrix},\quad
\vec{x}=
\begin{pmatrix}
x_1\\
x_2
\end{pmatrix}
\Rightarrow
L(\vec{x})=
\begin{pmatrix}
x_1 + kx_2\\
x_2
\end{pmatrix}
$$

This shears vectors horizontally by an amount proportional to their vertical component. Because $L$ is matrix-induced, it automatically satisfies linearity.

### Side-by-Side Differences

| Feature | Vector Transformation | Linear Transformation |
| --- | --- | --- |
| Definition | Any mapping $T:\mathbb{R}^n\to\mathbb{R}^m$ | Mapping that preserves vector addition and scalar multiplication |
| Algebraic constraints | None beyond being a function | Must satisfy $L(\vec{x}+\vec{z})=L(\vec{x})+L(\vec{z})$ and $L(c\vec{x})=cL(\vec{x})$ |
| Matrix representation | Not guaranteed | Always representable by a matrix $A$ |
| Origin behavior | Can move the origin | Must map $\vec{0}$ to $\vec{0}$ |
| Typical examples | Rotations with scaling by $r^2$, nonlinear warps | Projections, rotations, reflections, scalings, shears |

### Quick Test

check linearity with the **two-step test**:

1. Verify $T(\vec{0})=\vec{0}$. Failure implies nonlinearity.
2. Test additivity and homogeneity on basis vectors or symbolic inputs.

If either condition fails, $T$ is merely a vector transformation, not linear.


