## Row Space (Row(A)) and Bases of Row/Column Spaces

### Definition
- The **row space** of an m×n matrix $A$ is the set of all linear combinations of its rows. It is a subspace of $\mathbb{R}^n$.
- Notation: $Row(A) = \operatorname{span}\{r_1, r_2, \dots, r_m\}$ where $r_i^T$ is the $i$-th row of $A$.

### Key facts
- $Row(A) \subseteq \mathbb{R}^n$, $Col(A) \subseteq \mathbb{R}^m$.
- $\dim(Row(A)) = \dim(Col(A)) = \operatorname{rank}(A)$.
- Row operations do NOT change the row space. Therefore, the nonzero rows of $\operatorname{rref}(A)$ form a basis for $Row(A)$.
- Pivot columns of $A$ (from $\operatorname{rref}(A)$) pick a basis of $Col(A)$ using the original columns of $A$.
- $Row(A) = Col(A^T)$ and $Col(A) = Row(A^T)$.

---

### Some easy to understand row-space examples

- Example 1 (single row in $\mathbb{R}^3$):
  $$
  A = \begin{bmatrix}1 & 2 & 3\end{bmatrix}.
  $$
  $Row(A) = \operatorname{span}\{(1,2,3)\}$, a line in $\mathbb{R}^3$. Basis: $\{(1,2,3)\}$. Dimension: $1$.

- Example 2 (identity rows span the whole space):
  $$
  A = I_2 = \begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix}.
  $$
  Rows are $e_1, e_2$. $Row(A) = \operatorname{span}\{e_1,e_2\} = \mathbb{R}^2$. Basis: $\{e_1,e_2\}$. Dimension: $2$.

- Example 3 (dependent rows):
  $$
  A = \begin{bmatrix}1 & 1 \\ 2 & 2\end{bmatrix}.
  $$
  Second row $= 2\times$ first row. $Row(A) = \operatorname{span}\{(1,1)\}$. Basis: $\{(1,1)\}$. Dimension: $1$.

- Example 4 (zero matrix):
  $$
  A = \begin{bmatrix}0 & 0 \\ 0 & 0\end{bmatrix}.
  $$
  $Row(A) = \{\mathbf{0}\}$. Dimension: $0$.

---

### How to find a basis of the row space (step-by-step)

1) Put $A$ into RREF. 2) Take the nonzero rows of the RREF. These rows form a basis for $Row(A)$.

- Example (row-space basis via RREF):
  $$
  A = \begin{bmatrix}
  1 & 2 & 3 \\
  2 & 4 & 6 \\
  1 & 1 & 0
  \end{bmatrix}
  \xrightarrow{\;\operatorname{rref}\;}
  R = \begin{bmatrix}
  1 & 0 & -3 \\
  0 & 1 & 3 \\
  0 & 0 & 0
  \end{bmatrix}.
  $$
  - Nonzero rows of $R$ are $(1,0,-3)$ and $(0,1,3)$.
  - Basis of $Row(A)$: $\{(1,0,-3),\ (0,1,3)\}$. Dimension $=2$.

---

### How to find a basis of the column space (step-by-step)

1) Put $A$ into RREF and find pivot columns. 2) Take the corresponding ORIGINAL columns of $A$. These form a basis for $Col(A)$.

- Example (column-space basis via pivot columns):
  $$
  A = \begin{bmatrix}
  1 & 2 & 3 \\
  0 & 1 & 1 \\
  1 & 3 & 4
  \end{bmatrix}
  \xrightarrow{\;\operatorname{rref}\;}
  R = \begin{bmatrix}
  1 & 0 & 1 \\
  0 & 1 & 1 \\
  0 & 0 & 0
  \end{bmatrix}.
  $$
  - Pivot columns of $R$ are 1 and 2 $\Rightarrow$ use original columns 1 and 2 of $A$.
  - Basis of $Col(A)$: $\left\{\begin{bmatrix}1\\0\\1\end{bmatrix},\ \begin{bmatrix}2\\1\\3\end{bmatrix}\right\}$. Dimension $=2$.

---

### Combined demo: row vs column spaces and rank

Let
$$
A = \begin{bmatrix}
1 & 2 & 0 \\
0 & 1 & 1 \\
1 & 3 & 1
\end{bmatrix}
\xrightarrow{\;\operatorname{rref}\;}
R = \begin{bmatrix}
1 & 0 & -2 \\
0 & 1 & 1 \\
0 & 0 & 0
\end{bmatrix}.
$$
- Row-space basis: nonzero rows of $R$ $\Rightarrow$ $\{(1,0,-2),(0,1,1)\}$.
- Column-space basis: pivot columns (1,2) $\Rightarrow$ original columns $\left\{\begin{bmatrix}1\\0\\1\end{bmatrix},\ \begin{bmatrix}2\\1\\3\end{bmatrix}\right\}$.
- Rank $=2 = \dim(Row(A)) = \dim(Col(A))$.

---

### Quick membership checks
- $b \in Col(A)$ iff the system $Ax=b$ is consistent.
- $w \in Row(A)$ iff $w$ is a linear combination of the rows; equivalently, $w$ is in the span of the nonzero rows of $\operatorname{rref}(A)$.
