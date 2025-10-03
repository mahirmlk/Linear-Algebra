### Null space:

- **Definition (inline)**: For a matrix $ A \in \mathbb{R}^{m\times n} $, the null space (kernel) is
  $\,\mathcal{N}(A) = \{\, x \in \mathbb{R}^n : A x = 0 \,\}$.

- **Definition (display)**:
$$
\mathcal{N}(A) := \{\, x \in \mathbb{R}^n \mid A x = \mathbf{0} \in \mathbb{R}^m \,\}.
$$

### Subspace proof via matrix multiplication linearity
We show $\mathcal{N}(A)$ is a subspace of $\mathbb{R}^n$:
- Nonempty: $A\mathbf{0} = \mathbf{0}$, hence $\mathbf{0} \in \mathcal{N}(A)$.
- Closed under addition: if $x,y \in \mathcal{N}(A)$, then $A(x+y) = Ax + Ay = \mathbf{0}+\mathbf{0} = \mathbf{0}$, so $x+y \in \mathcal{N}(A)$.
- Closed under scalar multiplication: if $x \in \mathcal{N}(A)$ and $\alpha \in \mathbb{R}$, then $A(\alpha x) = \alpha (Ax) = \alpha\, \mathbf{0} = \mathbf{0}$, so $\alpha x \in \mathcal{N}(A)$.

Thus $\mathcal{N}(A)$ is a vector subspace of $\mathbb{R}^n$.

### Example 1: Nontrivial null space
Let
$$
A = \begin{bmatrix}
1 & 2 & -1 \\
2 & 4 & -2
\end{bmatrix} \in \mathbb{R}^{2\times 3}.
$$
Solve $Ax=0$. Row-reduce (left-multiplying by elementary matrices does not change the solution set of $Ax=0$):
$$
\begin{bmatrix}
1 & 2 & -1 \\
2 & 4 & -2
\end{bmatrix}
\xrightarrow{\ R_2 \leftarrow R_2 - 2R_1\ }
\begin{bmatrix}
1 & 2 & -1 \\
0 & 0 & 0
\end{bmatrix}.
$$
Let $x = (x_1,x_2,x_3)^T$. The pivot equation is
$$
 x_1 + 2x_2 - x_3 = 0 \ \Rightarrow\ x_1 = -2x_2 + x_3.
$$
Free variables: $x_2 = s$, $x_3 = t$. Then
$$
 x = \begin{bmatrix}-2s + t \\ s \\ t\end{bmatrix} = s\,\begin{bmatrix}-2\\1\\0\end{bmatrix} + t\,\begin{bmatrix}1\\0\\1\end{bmatrix}.
$$
Therefore a basis for $\mathcal{N}(A)$ is $\{\,(-2,1,0)^T,\ (1,0,1)^T\}$ and $\operatorname{nullity}(A)=2$.

### Example 2: Trivial null space
Let
$$
B = \begin{bmatrix}
1 & 0 \\
0 & 2
\end{bmatrix} \in \mathbb{R}^{2\times 2}.
$$
Solve $Bx=0$. The equations are $x_1=0$, $2x_2=0\Rightarrow x_2=0$. Hence $x=\mathbf{0}$ is the only solution, so $\mathcal{N}(B)=\{\mathbf{0}\}$ and $\operatorname{nullity}(B)=0$.

### Core properties
- Solution set of the homogeneous system:
  $$ \mathcal{N}(A) = \{ x \in \mathbb{R}^n : A x = 0 \}. $$
- Invariance under elementary row operations on the left: for any invertible $E$,
  $$ EAx = 0 \iff Ax = 0, $$
  so row-reducing $A$ does not change $\mathcal{N}(A)$.
- Connection to linear independence: columns of $A$ are linearly independent $\iff$ $\mathcal{N}(A) = \{\mathbf{0}\}$.
- Rank–nullity theorem (for $A \in \mathbb{R}^{m\times n}$):
  $$
  \operatorname{rank}(A) + \operatorname{nullity}(A) = n.
  $$
- Computing a basis: Put $A$ into RREF. Label free variables $t_1,\dots,t_k$; express pivot variables in terms of $t_j$. The coefficient vectors of each $t_j$ give a basis of $\mathcal{N}(A)$.

### Example 3: Calculating a null space via RREF 

Consider
$$
A = \begin{bmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
1 & 1 & 1
\end{bmatrix},\quad \text{solve } Ax = 0,
\quad x = \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}.
$$

Form the augmented matrix for the homogeneous system and row-reduce:
$$
\left[\begin{array}{ccc|c}
1 & 2 & 3 & 0 \\
2 & 4 & 6 & 0 \\
1 & 1 & 1 & 0
\end{array}\right]
\xrightarrow{\ R_2 \leftarrow R_2 - 2R_1\ }
\left[\begin{array}{ccc|c}
1 & 2 & 3 & 0 \\
0 & 0 & 0 & 0 \\
1 & 1 & 1 & 0
\end{array}\right]
\xrightarrow{\ R_3 \leftarrow R_3 - R_1\ }
\left[\begin{array}{ccc|c}
1 & 2 & 3 & 0 \\
0 & 0 & 0 & 0 \\
0 & -1 & -2 & 0
\end{array}\right].
$$

Make the pivot in row 3 positive and clear above it:
$$
R_3 \leftarrow -R_3\ :\ \left[\begin{array}{ccc|c}
1 & 2 & 3 & 0 \\
0 & 0 & 0 & 0 \\
0 & 1 & 2 & 0
\end{array}\right]
\xrightarrow{\ R_1 \leftarrow R_1 - 2R_3\ }
\left[\begin{array}{ccc|c}
1 & 0 & -1 & 0 \\
0 & 0 & 0 & 0 \\
0 & 1 & 2 & 0
\end{array}\right] \equiv \text{RREF}.
$$

Read off the equations from RREF:
$$
\begin{aligned}
x_1 - x_3 &= 0 \\[-2pt]
x_2 + 2x_3 &= 0
\end{aligned}
\quad\Rightarrow\quad x_1 = x_3,\ \ x_2 = -2x_3.
$$

Let the free variable be $x_3 = t$. Then
$$
x = \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}
= \begin{bmatrix}t\\-2t\\t\end{bmatrix}
= t\,\begin{bmatrix}1\\-2\\1\end{bmatrix}.
$$

Therefore, a basis for $\mathcal{N}(A)$ is $\{\,(1,-2,1)^T\,\}$ and $\operatorname{nullity}(A)=1$.


