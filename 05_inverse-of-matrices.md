

# Matrix Inverses

### 2×2 Matrix Inve**Given:** $A = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$

**Step 1: Calculate the Determinant**

$$
\det(A) = (3)(4) - (1)(2) = 12 - 2 = 10
$$

Since $\det(A) = 10 \neq 0$, the matrix is **invertible**.la

For a 2×2 matrix $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ with $\det(A) \neq 0$:

$$
A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{ad-bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

### 3×3 Matrix Inverse Using Adjugate

For a 3×3 matrix $A$, the **inverse** is calculated using the adjugate matrix:

$$
A^{-1} = \frac{1}{\det(A)} \cdot \text{adj}(A)
$$

For $A = \begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix}$:

$$
A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} 
ei-fh & -(bi-ch) & bf-ce \\
-(di-fg) & ai-cg & -(af-cd) \\
dh-eg & -(ah-bg) & ae-bd
\end{pmatrix}
$$

### Matrix Inverse Properties

**Key Properties:**

1. **Double Inverse:** $(A^{-1})^{-1} = A$
2. **Product Inverse:** $(AB)^{-1} = B^{-1}A^{-1}$ (order reverses)
3. **Transpose Inverse:** $(A^T)^{-1} = (A^{-1})^T$
4. **Identity Property:** $A \cdot A^{-1} = A^{-1} \cdot A = I$
5. **Determinant Inverse:** $\det(A^{-1}) = \frac{1}{\det(A)}$

## Complete Worked Example

### Finding the Inverse of a 2×2 Matrix

**Given:** $A = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$

**Step 1: Calculate the Determinant**

$$
\det(A) = (3)(4) - (1)(2) = 12 - 2 = 10
$$

Since $\det(A) = 10 \neq 0$, the matrix is **invertible**.

**Step 2: Apply the Inverse Formula**

$$
A^{-1} = \frac{1}{10} \begin{pmatrix} 4 & -1 \\ -2 & 3 \end{pmatrix} = \begin{pmatrix} 0.4 & -0.1 \\ -0.2 & 0.3 \end{pmatrix}
$$

**Step 3: Verification**

Check that $A \cdot A^{-1} = I$:

$$
A \cdot A^{-1} = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} \begin{pmatrix} 0.4 & -0.1 \\ -0.2 & 0.3 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

**Verification successful!**

## Applications and Notes

### When Does an Inverse Exist?

A matrix \(A\) has an inverse **if and only if** \(\det(A) \neq 0\). Such matrices are called:
- **Invertible** or **Non-singular**
- **Full rank**

### Computational Methods

For larger matrices (\(n \geq 4\)), practical computation uses:
- **Gaussian elimination** with partial pivoting
- **LU decomposition**
- **Cramer's rule** (theoretical, computationally expensive)

### Common Applications

- Solving linear systems: \(Ax = b \Rightarrow x = A^{-1}b\)
- Computer graphics transformations
- Statistics and data analysis
- Engineering and physics problems
