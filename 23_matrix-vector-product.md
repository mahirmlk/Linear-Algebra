## Matrix–Vector Product 

Given a matrix $A \in \mathbb{R}^{m\times n}$ and a vector $\vec{x} \in \mathbb{R}^n$, the matrix–vector product $\vec{y} = A\vec{x} \in \mathbb{R}^m$ is defined row-by-row using dot products:

$[\begin{aligned}
A &= \begin{pmatrix}
\text{— } \vec{a}_1^{\,T} \text{ —}\\
\text{— } \vec{a}_2^{\,T} \text{ —}\\
\vdots \\
\text{— } \vec{a}_m^{\,T} \text{ —}
\end{pmatrix},\quad \vec{x} = \begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix},\\[6pt]
\vec{y} &= A\vec{x} = \begin{pmatrix}
\vec{a}_1^{\,T}\\
\vec{a}_2^{\,T}\\
\vdots\\
\vec{a}_m^{\,T}
\end{pmatrix}\!\vec{x}
= \begin{pmatrix}
\vec{a}_1^{\,T}\vec{x}\\
\vec{a}_2^{\,T}\vec{x}\\
\vdots\\
\vec{a}_m^{\,T}\vec{x}
\end{pmatrix}.
\end{aligned}]$

Equivalently, using columns $\{\vec{c}_j\}_{j=1}^n$ of $A$ (so $A=[\vec{c}_1\;\vec{c}_2\;\cdots\;\vec{c}_n]$):

$[ A\vec{x} = x_1\vec{c}_1 + x_2\vec{c}_2 + \cdots + x_n\vec{c}_n. ]$

### Compatibility Rule
- $A$ has size $m\times n$ and $\vec{x}$ has length $n$. The inner dimensions must match.

### Example (Numeric Demo)
Let
$[ A = \begin{pmatrix}
2 & -1 & 0\\
3 & 4 & 1\\
-2 & 5 & 2
\end{pmatrix},\quad
\vec{x} = \begin{pmatrix}1\\2\\-1\end{pmatrix}. ]$

Row-wise dot products (each entry is a dot product):
$[\begin{aligned}
y_1 &= (2,\,-1,\,0)\cdot(1,\,2,\,-1) = 2(1) + (-1)(2) + 0(-1) = 0,\\
y_2 &= (3,\,4,\,1)\cdot(1,\,2,\,-1) = 3 + 8 - 1 = 10,\\
y_3 &= (-2,\,5,\,2)\cdot(1,\,2,\,-1) = -2 + 10 - 2 = 6.
\end{aligned}]$

Thus
$[ A\vec{x} = \begin{pmatrix}0\\10\\6\end{pmatrix}. ]$

Column-combination view (same result): if
$[ \vec{c}_1 = \begin{pmatrix}2\\3\\-2\end{pmatrix},\; \vec{c}_2 = \begin{pmatrix}-1\\4\\5\end{pmatrix},\; \vec{c}_3 = \begin{pmatrix}0\\1\\2\end{pmatrix}, ]$
then
$[ A\vec{x} = 1\,\vec{c}_1 + 2\,\vec{c}_2 + (-1)\,\vec{c}_3 = \begin{pmatrix}0\\10\\6\end{pmatrix}. ]$

### Notes
- Each output entry is a dot product between a row of $A$ and $\vec{x}$.



