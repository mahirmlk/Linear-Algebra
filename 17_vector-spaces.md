# Vector Spaces

A nonempty set $V$ with two operations (vector addition and scalar multiplication) over a field $\mathbb{F}$ (usually $\mathbb{R}$ or $\mathbb{Z}$) is a vector space if for all $\mathbf{u},\mathbf{v},\mathbf{w}\in V$ and $a,b\in\mathbb{F}$ the following hold:

- $\mathbf{u}+\mathbf{v}\in V$ (closure under addition)
- $a\mathbf{v}\in V$ (closure under scalar multiplication)
- $\mathbf{u}+\mathbf{v}=\mathbf{v}+\mathbf{u}$ (commutativity)
- $(\mathbf{u}+\mathbf{v})+\mathbf{w}=\mathbf{u}+(\mathbf{v}+\mathbf{w})$ (associativity)
- There exists $\mathbf{0}\in V$ with $\mathbf{v}+\mathbf{0}=\mathbf{v}$ (additive identity)
- For each $\mathbf{v}\in V$ there exists $-\mathbf{v}\in V$ with $\mathbf{v}+(-\mathbf{v})=\mathbf{0}$ (additive inverse)
- $a(\mathbf{u}+\mathbf{v})=a\mathbf{u}+a\mathbf{v}$ (distributivity over vectors)
- $(a+b)\mathbf{v}=a\mathbf{v}+b\mathbf{v}$ (distributivity over scalars)
- $a(b\mathbf{v})=(ab)\mathbf{v}$ (associativity of scalars)
- $1\mathbf{v}=\mathbf{v}$ (scalar identity)

In computations we often build vectors by linear combinations. For vectors $\mathbf{u}_1,\dots,\mathbf{u}_k\in V$ and scalars $c_1,\dots,c_k$, any vector of the form
$$
\mathbf{v}=c_1\mathbf{u}_1+\cdots+c_k\mathbf{u}_k
$$
is a linear combination. The set of all such combinations is the span $\operatorname{span}\{\mathbf{u}_1,\dots,\mathbf{u}_k\}$.

## Core examples

- $\mathbf{R}^n$: Column vectors with real entries, standard operations. For $\mathbf{x},\mathbf{y}\in\mathbb{R}^n$ and $a\in\mathbb{R}$,
  $$
  a\mathbf{x}+\mathbf{y}=\begin{bmatrix}ax_1+y_1\\\vdots\\ax_n+y_n\end{bmatrix}.
  $$

- Polynomial space $\mathcal{P}_n$: Real polynomials of degree $\le n$; basis $\{1,x,\dots,x^n\}$, so $\dim(\mathcal{P}_n)=n+1$.

- Matrix space $\mathbb{R}^{m\times n}$: All $m\times n$ real matrices; dimension $mn$. Example of a linear combination:
  $$
  A=2\begin{bmatrix}1&0\\0&1\end{bmatrix}-\begin{bmatrix}0&1\\1&0\end{bmatrix}=\begin{bmatrix}2&-1\\-1&2\end{bmatrix}.
  $$

- Function space $C[a,b]$: All continuous functions on $[a,b]$ with $(af+g)(x)=af(x)+g(x)$.


## Real-world example: forces in mechanics

In planar mechanics, forces are vectors in $\mathbb{R}^2$. If a body experiences forces $\mathbf{F}_1$ and $\mathbf{F}_2$, the net force is the vector sum $\mathbf{F}_\text{net}=\mathbf{F}_1+\mathbf{F}_2$. Scaling a force by $a\in\mathbb{R}$ corresponds to changing its magnitude (and direction if $a<0$). With components,
$$
\mathbf{F}_1=\begin{bmatrix}F_{1x}\\F_{1y}\end{bmatrix},\quad
\mathbf{F}_2=\begin{bmatrix}F_{2x}\\F_{2y}\end{bmatrix}
\;\Rightarrow\;
\mathbf{F}_\text{net}=\begin{bmatrix}F_{1x}+F_{2x}\\F_{1y}+F_{2y}\end{bmatrix}.
$$
Any combination $a\mathbf{F}_1+b\mathbf{F}_2$ is physically meaningful and remains a vector in the same space, illustrating closure and linearity.


## Basis and dimension

A set $\mathcal{B}=\{\mathbf{b}_1,\dots,\mathbf{b}_k\}$ is a basis for $V$ if it is linearly independent and spans $V$. The number $k$ is the dimension $\dim(V)$. For $\mathbb{R}^n$, the standard basis is
$$
\{\mathbf{e}_1,\dots,\mathbf{e}_n\},\quad \mathbf{e}_1=\begin{bmatrix}1\\0\\\vdots\\0\end{bmatrix},\;\dots,\;\mathbf{e}_n=\begin{bmatrix}0\\\vdots\\0\\1\end{bmatrix}.
$$

## Visual intuition (for $\mathbb{R}^2$ and $\mathbb{R}^3$)

- $\mathbb{R}^2$: The span of one nonzero vector is a line through the origin; the span of two non-collinear vectors is the whole plane.

```
R^2 visualization (ASCII)

Span{u} = all points on the line through 0 and u.

   ^ y
   |
   |        u
   |       /
   |      /
---+-----/------> x
   |    /
   |   /
   |  /
   |

Span{u,v} with u and v not collinear = entire plane.
```

- $\mathbb{R}^3$: The span of one nonzero vector is a line; of two non-collinear vectors is a plane through the origin; of three non-coplanar vectors is all of $\mathbb{R}^3$.


