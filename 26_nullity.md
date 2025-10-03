### Nullity: dimension of the null space

- **Definition**: For $A \in \mathbb{R}^{m\times n}$, the nullity of $A$ is the dimension of its null space $\mathcal{N}(A)$:
  $$
  \operatorname{nullity}(A) := \dim\mathcal{N}(A).
  $$


### solve $Ax=0$, extract basis, read nullity
 We simply solve $Ax=0$, write the general solution with parameters, then read a basis for $\mathcal{N}(A)$. The number of basis vectors equals the nullity.

#### Example A: One free variable $\Rightarrow$ nullity $=1$
Let
$$
A = \begin{bmatrix}
1 & 2 & -1 \\
0 & 1 & 3 \\
0 & 0 & 0
\end{bmatrix},\quad x = \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix},\quad Ax=0.
$$
Read equations from the upper-triangular form:
$$
\begin{aligned}
\text{Row 3:}\ & 0=0\ \text{(no info)}\\
\text{Row 2:}\ & x_2 + 3x_3 = 0 \Rightarrow x_2 = -3x_3 \\
\text{Row 1:}\ & x_1 + 2x_2 - x_3 = 0 \Rightarrow x_1 = -2x_2 + x_3.
\end{aligned}
$$
Let the free variable be $x_3 = t$. Then
$$
\begin{aligned}
x_2 &= -3t,\\
x_1 &= -2(-3t) + t = 6t + t = 7t,\\
x &= \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} = \begin{bmatrix}7t\\-3t\\t\end{bmatrix} = t\,\begin{bmatrix}7\\-3\\1\end{bmatrix}.
\end{aligned}
$$
Basis: $\{\,(7,-3,1)^T\,\}$. There is 1 basis vector, so nullity $=1$.

#### Example B: Two free variables $\Rightarrow$ nullity $=2$
Consider
$$
B = \begin{bmatrix}
1 & 1 & 2 & 0 \\
0 & 1 & 3 & 1 \\
0 & 0 & 0 & 0
\end{bmatrix},\quad y = \begin{bmatrix}y_1\\y_2\\y_3\\y_4\end{bmatrix},\quad By=0.
$$
Equations:
$$
\begin{aligned}
\text{Row 2:}\ & y_2 + 3y_3 + y_4 = 0 \Rightarrow y_2 = -3y_3 - y_4,\\
\text{Row 1:}\ & y_1 + y_2 + 2y_3 = 0 \Rightarrow y_1 = -y_2 - 2y_3.
\end{aligned}
$$
Choose free variables $y_3 = s$, $y_4 = t$. Then
$$
\begin{aligned}
y_2 &= -3s - t,\\
y_1 &= -(-3s - t) - 2s = 3s + t - 2s = s + t.
\end{aligned}
$$
Assemble the solution:
$$
y = \begin{bmatrix}y_1\\y_2\\y_3\\y_4\end{bmatrix}
= \begin{bmatrix}s+t\\-3s - t\\s\\t\end{bmatrix}
= s\,\begin{bmatrix}1\\-3\\1\\0\end{bmatrix} \; + \; t\,\begin{bmatrix}1\\-1\\0\\1\end{bmatrix}.
$$
Basis: $\{\,(1,-3,1,0)^T,\ (1,-1,0,1)^T\,\}$. There are 2 basis vectors, so nullity $=2$.

#### Example C: No free variables $\Rightarrow$ nullity $=0$
Let
$$
C = \begin{bmatrix}
2 & 0 \\
0 & -5
\end{bmatrix},\quad z = \begin{bmatrix}z_1\\z_2\end{bmatrix},\quad Cz=0.
$$
Equations: $2z_1=0 \Rightarrow z_1=0$, $-5z_2=0 \Rightarrow z_2=0$. Then $z=\mathbf{0}$ only, so the basis is the empty set and nullity $=0$.



### Relation to linear independence and the null space
- Columns of $A$ are linearly independent $\iff \mathcal{N}(A) = \{\mathbf{0}\} \iff \operatorname{nullity}(A)=0$.
- If $\operatorname{nullity}(A) > 0$, then there exist nontrivial solutions to $Ax=0$, so the columns are linearly dependent.
- Rank–nullity connects all three:
  $$
  \operatorname{rank}(A) + \dim\mathcal{N}(A) = n
  $$
  where $n$ is the number of columns.

### Quick checklist
- Compute RREF, count pivots $r$.
- Nullity $= n-r$ (number of free variables).
- Nullity $=0$ means independent columns; $>0$ means dependence.

