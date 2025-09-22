# Vector Subspaces

## Definition

A **vector subspace** (or simply **subspace**) of a vector space $V$ is a subset $W \subseteq V$ that is itself a vector space under the same operations of addition and scalar multiplication defined on $V$.

## Subspace Test

A subset $W$ of a vector space $V$ is a subspace if and only if:

1. **Non-empty**: $W \neq \emptyset$
2. **Closed under addition**: For all $\mathbf{u}, \mathbf{v} \in W$, we have $\mathbf{u} + \mathbf{v} \in W$
3. **Closed under scalar multiplication**: For all $\mathbf{u} \in W$ and scalar $c$, we have $c\mathbf{u} \in W$

### Alternative Formulation

$W$ is a subspace of $V$ if and only if:
- $W \neq \emptyset$
- For all $\mathbf{u}, \mathbf{v} \in W$ and scalars $a, b$, we have $a\mathbf{u} + b\mathbf{v} \in W$

## Examples of Subspaces

### 1. Trivial Subspaces

- **Zero subspace**: $\{\mathbf{0}\}$ is always a subspace of any vector space $V$
- **The space itself**: $V$ is a subspace of $V$

### 2. Lines Through the Origin

In $\mathbb{R}^2$ or $\mathbb{R}^3$:
$$W = \{t\mathbf{v} : t \in \mathbb{R}\}$$

where $\mathbf{v} \neq \mathbf{0}$ is a fixed vector.

### 3. Planes Through the Origin

In $\mathbb{R}^3$:
$$W = \{s\mathbf{u} + t\mathbf{v} : s, t \in \mathbb{R}\}$$

where $\mathbf{u}$ and $\mathbf{v}$ are linearly independent vectors.

### 4. Solution Space of Homogeneous Systems

The set of solutions to $A\mathbf{x} = \mathbf{0}$ is a subspace of $\mathbb{R}^n$.

### 5. Polynomial Subspaces

- **Degree at most n**: $P_n = \{p(x) : \deg(p) \leq n\}$
- **Even polynomials**: $\{p(x) : p(-x) = p(x)\}$
- **Polynomials with $p(0) = 0$**: $\{p(x) : p(0) = 0\}$

## Span of Vectors

The **span** of vectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_k$ is:
$$\text{span}\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_k\} = \{c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_k\mathbf{v}_k : c_i \in \mathbb{R}\}$$

### Properties of Span

1. $\text{span}\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_k\}$ is always a subspace
2. It is the smallest subspace containing all the vectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_k$

## Important Theorems

### Theorem 1: Dimension of Column Space

For any matrix $A$:
$$\dim(\text{Col}(A)) = \text{rank}(A)$$

### Theorem 2: Rank-Nullity Theorem

For an $m \times n$ matrix $A$:
$$\text{rank}(A) + \text{nullity}(A) = n$$

where $\text{nullity}(A) = \dim(\text{Null}(A))$.

### Theorem 3: Subspace Dimension

If $W$ is a subspace of $V$, then:
$$\dim(W) \leq \dim(V)$$

## Operations on Subspaces

### Intersection of Subspaces

If $W_1$ and $W_2$ are subspaces of $V$, then:
$$W_1 \cap W_2 = \{\mathbf{v} \in V : \mathbf{v} \in W_1 \text{ and } \mathbf{v} \in W_2\}$$

is also a subspace of $V$.

### Sum of Subspaces

$$W_1 + W_2 = \{\mathbf{w}_1 + \mathbf{w}_2 : \mathbf{w}_1 \in W_1, \mathbf{w}_2 \in W_2\}$$

### Direct Sum

If $W_1 \cap W_2 = \{\mathbf{0}\}$, then $W_1 + W_2$ is called a **direct sum**, denoted:
$$W_1 \oplus W_2$$

## Worked Examples

### Example 1: Subspace Test

**Problem**: Show that $W = \{(x, y, z) \in \mathbb{R}^3 : x + y + z = 0\}$ is a subspace of $\mathbb{R}^3$.

**Solution**:
1. **Non-empty**: $(0, 0, 0) \in W$ since $0 + 0 + 0 = 0$ ✓
2. **Closed under addition**: Let $(x_1, y_1, z_1), (x_2, y_2, z_2) \in W$
   - Then $x_1 + y_1 + z_1 = 0$ and $x_2 + y_2 + z_2 = 0$
   - $(x_1 + x_2) + (y_1 + y_2) + (z_1 + z_2) = (x_1 + y_1 + z_1) + (x_2 + y_2 + z_2) = 0 + 0 = 0$ ✓
3. **Closed under scalar multiplication**: Let $(x, y, z) \in W$ and $c \in \mathbb{R}$
   - Then $x + y + z = 0$
   - $c(x + y + z) = c \cdot 0 = 0$, so $(cx, cy, cz) \in W$ ✓

Therefore, $W$ is a subspace of $\mathbb{R}^3$.

### Example 2: Finding a Basis

**Problem**: Find a basis for the subspace $W = \{(x, y, z) \in \mathbb{R}^3 : x + y + z = 0\}$.

**Solution**:
From $x + y + z = 0$, we get $z = -x - y$.
So any vector in $W$ has the form:
$$(x, y, -x - y) = x(1, 0, -1) + y(0, 1, -1)$$

Therefore, $W = \text{span}\{(1, 0, -1), (0, 1, -1)\}$.

Since these vectors are linearly independent, $\{(1, 0, -1), (0, 1, -1)\}$ is a basis for $W$.

### Example 3: Column Space

**Problem**: Find a basis for the column space of $A = \begin{bmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 1 & 3 & 5 \end{bmatrix}$.

**Solution**:
Row reduce $A$:
$$\begin{bmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 1 & 3 & 5 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 0 & 1 & 2 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 0 & -1 \\ 0 & 1 & 2 \\ 0 & 0 & 0 \end{bmatrix}$$

The pivot columns are columns 1 and 2, so a basis for $\text{Col}(A)$ is:
$$\left\{\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} 2 \\ 1 \\ 3 \end{bmatrix}\right\}$$

## Key Takeaways

- Subspaces are closed under linear combinations
- The span of any set of vectors is a subspace
- Column space and null space are fundamental subspaces
- Dimension is well-defined for any subspace
- The rank-nullity theorem connects dimensions of column space and null space
