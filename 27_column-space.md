## Column Space (Col(A))

### Definition
- **Column space** of an m×n matrix $A$ is the set of all linear combinations of its columns. It is a subspace of $\mathbb{R}^m$.
- Notation: $Col(A) = \operatorname{span}\{a_1, a_2, \dots, a_n\}$ where $a_j$ is the j-th column of $A$.

### Key facts
- **Subspace**: $Col(A) \subseteq \mathbb{R}^m$.
- **Span of columns**: Every vector in $Col(A)$ is $Ax$ for some $x$.
- **Basis via pivots**: The columns of $A$ corresponding to pivot columns (from the RREF of $A$) form a basis for $Col(A)$.
- **Dimension**: $\dim(Col(A)) = \operatorname{rank}(A)$.
- **Solvability**: The system $Ax = b$ has a solution iff $b \in Col(A)$.

---

### some easy to understand examples

- Example A (single column in $\mathbb{R}^2$):
  $$
  A = \begin{bmatrix}1\\2\end{bmatrix} = \big[\,a_1\,\big],\quad a_1 = \begin{bmatrix}1\\2\end{bmatrix}.
  $$
  $Col(A) = \operatorname{span}\{a_1\} = \{ t\,(1,2)^T : t\in\mathbb{R} \}$, a line through the origin.

- Example B (identity matrix gives the whole space):
  $$
  A = I_2 = \begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix},\quad a_1 = e_1,\ a_2 = e_2.
  $$
  $Col(A) = \operatorname{span}\{e_1,e_2\} = \mathbb{R}^2$. Basis: $\{e_1,e_2\}$. Dimension: $2$.

- Example C (duplicate columns):
  $$
  A = \begin{bmatrix}1 & 1 \\ 1 & 1\end{bmatrix},\quad a_2 = a_1 = \begin{bmatrix}1\\1\end{bmatrix}.
  $$
  $Col(A) = \operatorname{span}\{a_1\} = \{ t\,(1,1)^T : t\in\mathbb{R} \}$. Basis: $\{(1,1)^T\}$. Dimension: $1$.

- Example D (all-zero matrix):
  $$
  A = \begin{bmatrix}0 & 0 \\ 0 & 0\end{bmatrix}.
  $$
  $Col(A) = \{\mathbf{0}\}$ only. Basis: none (the zero vector cannot be in a basis). Dimension: $0$.

  ---
  ---

### Example 1: 2×2 with dependent columns
Let
$$
A = \begin{bmatrix} 1 & 2 \\
0 & 0 \end{bmatrix},\quad a_1 = \begin{bmatrix}1 \\
0\end{bmatrix},\ a_2 = \begin{bmatrix}2 \\
0\end{bmatrix} = 2 a_1.
$$
- $Col(A) = \operatorname{span}\{a_1\} = \{ (t, 0)^T : t \in \mathbb{R} \}$ (the x-axis in $\mathbb{R}^2$).
- Basis: $\{ (1,0)^T \}$. Dimension: $1$.
- Membership: $b = (3,0)^T \in Col(A)$ (take $x = (3,0)^T$). But $b = (1,1)^T \notin Col(A)$ because all vectors in $Col(A)$ have second entry $0$.

---

### Example 2: 3×2 with independent columns (a plane in $\mathbb{R}^3$)
Let
$$
A = \begin{bmatrix}
1 & 0 \\
2 & 1 \\
0 & 1
\end{bmatrix},\quad a_1 = \begin{bmatrix}1\\2\\0\end{bmatrix},\ a_2 = \begin{bmatrix}0\\1\\1\end{bmatrix}.
$$
- $a_1$ and $a_2$ are independent, so $Col(A) = \operatorname{span}\{a_1, a_2\}$ is a 2D plane.
- Basis: $\{ a_1, a_2 \}$. Dimension: $2$.
- Membership checks:
  - $b = (1,3,1)^T = 1\cdot a_1 + 1\cdot a_2 \in Col(A)$.
  - $b' = (0,1,0)^T$ is not in $Col(A)$: first coordinate forces $\alpha = 0$, then second gives $\beta = 1$, but third becomes $1 \neq 0$.

---

### Example 3: Finding a basis using pivot columns
Given
$$
A = \begin{bmatrix}
1 & 2 & 3 \\
0 & 1 & 1
\end{bmatrix}.
$$
Row-reduce to RREF:
$$
\operatorname{rref}(A) = \begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 1
\end{bmatrix}.
$$
- Pivot columns in the RREF are columns 1 and 2, so the corresponding **original** columns of $A$ ($\begin{bmatrix}1\\0\end{bmatrix}$ and $\begin{bmatrix}2\\1\end{bmatrix}$) form a basis for $Col(A)$.
- Therefore,
$$
Col(A) = \operatorname{span}\left\{ \begin{bmatrix}1\\0\end{bmatrix}, \begin{bmatrix}2\\1\end{bmatrix} \right\},\quad \dim(Col(A)) = 2 = \operatorname{rank}(A).
$$
- Quick membership: $b = (5,2)^T$ is in $Col(A)$ since $\begin{bmatrix}1 & 2\\0 & 1\end{bmatrix}\begin{bmatrix}1 \\ 2\end{bmatrix} = \begin{bmatrix}5 \\ 2\end{bmatrix}$.


---

### How to compute $Col(A)$ in practice
1. Row-reduce `A` to RREF.
2. Identify pivot columns in the RREF.
3. Take the corresponding original columns of `A`; these form a basis for $Col(A)$.
4. The number of basis vectors is $\operatorname{rank}(A) = \dim(Col(A))$.
