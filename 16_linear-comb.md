# Linear Combination

A vector $\mathbf{v}$ is a linear combination of vectors $\mathbf{u}_1,\mathbf{u}_2,\dots,\mathbf{u}_k$ if there exist scalars $c_1, c_2, \dots, c_k$ such that

$$
\mathbf{v} = c_1\mathbf{u}_1 + c_2\mathbf{u}_2 + \cdots + c_k\mathbf{u}_k.
$$

- **Span**: The set of all linear combinations of $\{\mathbf{u}_1,\dots,\mathbf{u}_k\}$ is the span, written $\operatorname{span}\{\mathbf{u}_1,\dots,\mathbf{u}_k\}$.
- **Goal**: Given $\mathbf{v}$ and $\mathbf{u}_i$, decide if $\mathbf{v}\in\operatorname{span}\{\mathbf{u}_1,\dots,\mathbf{u}_k\}$ by solving for $c_i$.

### Example in $\mathbb{R}^2$
Let
$$
\mathbf{u}_1 = \begin{bmatrix}1\\2\end{bmatrix},\quad
\mathbf{u}_2 = \begin{bmatrix}3\\-1\end{bmatrix},\quad
\mathbf{v}   = \begin{bmatrix}5\\0\end{bmatrix}.
$$
We seek $c_1,c_2$ such that $c_1\mathbf{u}_1 + c_2\mathbf{u}_2 = \mathbf{v}$:
$$
\begin{cases}
1\cdot c_1 + 3\cdot c_2 = 5,\\
2\cdot c_1 - 1\cdot c_2 = 0.
\end{cases}
$$
Solve:
$$
\begin{aligned}
2c_1 - c_2 &= 0 \;\Rightarrow\; c_2 = 2c_1,\\
c_1 + 3(2c_1) &= 5 \;\Rightarrow\; 7c_1 = 5 \;\Rightarrow\; c_1 = \tfrac{5}{7},\\
c_2 &= 2\cdot\tfrac{5}{7} = \tfrac{10}{7}.
\end{aligned}
$$
Therefore $\mathbf{v}$ is a linear combination: $\mathbf{v} = \tfrac{5}{7}\,\mathbf{u}_1 + \tfrac{10}{7}\,\mathbf{u}_2$.

### Matrix form
Stack $\mathbf{u}_i$ as columns of $A$. Then $\mathbf{v}$ is a linear combination iff the system
$$
A\mathbf{c} = \mathbf{v}
$$
has a solution $\mathbf{c}$. This can be checked with row-reduction (Gauss–Jordan).

### Quick properties
- **Zero vector**: $\mathbf{0}$ is a linear combination with all coefficients zero.
- **Uniqueness**: If columns of $A$ are linearly independent, the coefficients are unique.
- **Redundancy**: If columns are dependent, multiple $\mathbf{c}$ may produce the same $\mathbf{v}$.


