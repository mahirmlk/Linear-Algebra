### 1. Vector Transformation (general map)

A **vector transformation** is any rule $T:\mathbb{R}^n\to\mathbb{R}^m$ that takes an input vector and spits out another one—no algebraic promises required. Think of it simply as “plug in a vector, get a vector.”

$$
T(\vec{x}) =
\begin{pmatrix}
f_1(\vec{x})\\
\vdots\\
f_m(\vec{x})
\end{pmatrix}
$$

#### Example A: Nonlinear Warp (polar stretch)

Let $\vec{x}=(x_1,x_2)$. Define

$$
T(\vec{x})=
\begin{pmatrix}
x_1^2 - x_2^2\\
2x_1x_2
\end{pmatrix}
=
\begin{pmatrix}
r^2\cos(2\theta)\\
r^2\sin(2\theta)
\end{pmatrix},
\quad r=\sqrt{x_1^2+x_2^2}
$$

Take two vectors

$$
\vec{u}=\begin{pmatrix}1\\1\end{pmatrix},\qquad
\vec{v}=\begin{pmatrix}2\\0\end{pmatrix}
$$

Compute:

$$
T(\vec{u})=
\begin{pmatrix}
0\\
2
\end{pmatrix},\quad
T(\vec{v})=
\begin{pmatrix}
4\\
0
\end{pmatrix},\quad
T(\vec{u}+\vec{v})=
\begin{pmatrix}
5\\
6
\end{pmatrix}
$$

Since $T(\vec{u}+\vec{v}) \neq T(\vec{u})+T(\vec{v})$, this transformation is **not linear**—it merely maps vectors in a nonlinear manner.

#### Example B: Simple Translation

Let $T(\vec{x})=\vec{x}+\begin{pmatrix}1\\0\end{pmatrix}$. For $\vec{u}=(0,0)^T$ and $\vec{v}=(2,-1)^T$,

$$
T(\vec{u})=\begin{pmatrix}1\\0\end{pmatrix},\quad
T(\vec{v})=\begin{pmatrix}3\\-1\end{pmatrix},\quad
T(\vec{u}+\vec{v})=\begin{pmatrix}3\\-1\end{pmatrix}
$$

Here $T(\vec{u})+T(\vec{v})=\begin{pmatrix}4\\-1\end{pmatrix}\neq T(\vec{u}+\vec{v})$, so even a plain translation breaks linearity. This makes the difference between “any transformation” and “linear transformation” tangible.

### 2. Linear Transformation (structure-preserving)

A **linear transformation** $L:\mathbb{R}^n\to\mathbb{R}^m$ must satisfy

$$
L(\vec{x}+\vec{z})=L(\vec{x})+L(\vec{z}),\qquad
L(c\vec{x})=c\,L(\vec{x})
$$

Every linear map on finite-dimensional spaces corresponds to a matrix $A$:

$$
L(\vec{x})=A\vec{x}
$$

#### Example A: Shear Matrix

Let

$$
A=
\begin{pmatrix}
1 & k\\
0 & 1
\end{pmatrix},\quad
\vec{x}=\begin{pmatrix}x_1\\x_2\end{pmatrix},
\quad
L(\vec{x})=
\begin{pmatrix}
x_1 + kx_2\\
x_2
\end{pmatrix}
$$

Choose $k=2$, $\vec{u}=(1,1)^T$, $\vec{v}=(2,-1)^T$:

$$
L(\vec{u})=\begin{pmatrix}3\\1\end{pmatrix},\quad
L(\vec{v})=\begin{pmatrix}0\\-1\end{pmatrix},\quad
L(\vec{u}+\vec{v})=\begin{pmatrix}3\\0\end{pmatrix}
$$

Linearity check:

$$
L(\vec{u})+L(\vec{v})=
\begin{pmatrix}3\\1\end{pmatrix}+
\begin{pmatrix}0\\-1\end{pmatrix}=
\begin{pmatrix}3\\0\end{pmatrix}=
L(\vec{u}+\vec{v})
$$

Likewise $L(c\vec{u})=cL(\vec{u})$ for any scalar $c$.

#### Example B: Projection onto the $x$-axis

Let

$$
P=
\begin{pmatrix}
1 & 0\\
0 & 0
\end{pmatrix},\quad
L(\vec{x})=P\vec{x}
=
\begin{pmatrix}
x_1\\
0
\end{pmatrix}
$$

For $\vec{u}=(2,3)^T$, $\vec{v}=(-1,4)^T$, and $c=-2$:

$$
L(\vec{u})=\begin{pmatrix}2\\0\end{pmatrix},\quad
L(\vec{v})=\begin{pmatrix}-1\\0\end{pmatrix},\quad
L(\vec{u}+\vec{v})=\begin{pmatrix}1\\0\end{pmatrix}
$$

We have $L(\vec{u})+L(\vec{v})=\begin{pmatrix}1\\0\end{pmatrix}=L(\vec{u}+\vec{v})$ and $L(c\vec{u})=cL(\vec{u})=\begin{pmatrix}-4\\0\end{pmatrix}$, confirming linearity with an easy-to-visualize map (drop each vector straight onto the $x$-axis).

