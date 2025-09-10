# Matrices: Introduction and Notation

## What is a Matrix?

A **matrix** is a rectangular array of numbers, symbols, or expressions arranged in rows and columns. Matrices are fundamental structures in linear algebra and serve as powerful tools for representing and solving systems of linear equations, transformations, and data organization.

## General Matrix Representation

A general matrix $A$ with $m$ rows and $n$ columns is written as:

$$A = \begin{pmatrix}
a_{11} & a_{12} & a_{13} & \cdots & a_{1n} \\
a_{21} & a_{22} & a_{23} & \cdots & a_{2n} \\
a_{31} & a_{32} & a_{33} & \cdots & a_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & a_{m3} & \cdots & a_{mn}
\end{pmatrix}$$

## Matrix Notation Conventions

### Element Notation
- Each element is denoted as $a_{ij}$, where:
  - $i$ represents the **row number** (1 to $m$)
  - $j$ represents the **column number** (1 to $n$)
- The element $a_{ij}$ is located at the intersection of the $i$-th row and $j$-th column

### Alternative Notations
Matrices can be represented in several ways:

1. **Parentheses notation**: $A = \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}$

2. **Bracket notation**: $A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}$

3. **Double bars**: $A = \begin{Vmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{Vmatrix}$

4. **Compact notation**: $A = [a_{ij}]_{m \times n}$ or $A = (a_{ij})$

## Matrix Terminology

### Order or Dimension
The **order** (or **dimension**) of a matrix describes its size:
- A matrix with $m$ rows and $n$ columns has order $m \times n$ (read as "$m$ by $n$")
- The order is always written as **rows × columns**

**Examples:**
- $\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}$ has order $2 \times 3$
- $\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ has order $3 \times 1$

### Square Matrix
A matrix where the number of rows equals the number of columns ($m = n$):

$$A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix} \quad \text{(3×3 square matrix)}$$

### Row Vector
A matrix with only one row (order $1 \times n$):

$$\mathbf{r} = \begin{pmatrix} r_1 & r_2 & r_3 & \cdots & r_n \end{pmatrix}$$

**Example:** $\mathbf{r} = \begin{pmatrix} 2 & -1 & 4 & 7 \end{pmatrix}$ (order $1 \times 4$)

### Column Vector
A matrix with only one column (order $m \times 1$):

$$\mathbf{c} = \begin{pmatrix} c_1 \\ c_2 \\ c_3 \\ \vdots \\ c_m \end{pmatrix}$$

**Example:** $\mathbf{c} = \begin{pmatrix} 3 \\ -2 \\ 5 \end{pmatrix}$ (order $3 \times 1$)

## Matrix Elements and Indexing

### Main Diagonal
For a square matrix, the **main diagonal** (or **principal diagonal**) consists of elements $a_{ii}$ where the row and column indices are equal:

$$A = \begin{pmatrix}
\mathbf{a_{11}} & a_{12} & a_{13} \\
a_{21} & \mathbf{a_{22}} & a_{23} \\
a_{31} & a_{32} & \mathbf{a_{33}}
\end{pmatrix}$$

### Upper and Lower Triangular Parts
- **Upper triangular part**: Elements $a_{ij}$ where $i < j$ (above the main diagonal)
- **Lower triangular part**: Elements $a_{ij}$ where $i > j$ (below the main diagonal)

### Matrix Equality
Two matrices $A$ and $B$ are equal if:
1. They have the same order ($m \times n$)
2. Corresponding elements are equal: $a_{ij} = b_{ij}$ for all $i, j$

$$A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} = B = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}$$

## Common Matrix Naming Conventions

### Capital Letters
Matrices are typically denoted by capital letters: $A$, $B$, $C$, $M$, $X$, etc.

### Subscripts for Identification
Multiple matrices can be distinguished using subscripts:
- $A_1, A_2, A_3$ for a sequence of matrices
- $A_{input}, A_{output}$ for descriptive naming

### Bold Notation for Vectors
Vectors (row or column matrices) are often written in bold:
- $\mathbf{v}$ for a column vector
- $\mathbf{u}^T$ for a row vector (transpose of column vector)

## Practical Examples

### Example 1: Student Grade Matrix
A $3 \times 4$ matrix representing grades of 3 students in 4 subjects:

$$\text{Grades} = \begin{pmatrix}
85 & 92 & 78 & 88 \\
90 & 85 & 95 & 82 \\
75 & 88 & 90 & 94
\end{pmatrix}$$

Where:
- Rows represent students (Student 1, Student 2, Student 3)
- Columns represent subjects (Math, Science, English, History)
- Element $g_{23} = 95$ means Student 2 scored 95 in English

### Example 2: Coordinate Transformation
A $2 \times 2$ matrix for rotating points in 2D space:

$$R_\theta = \begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix}$$

### Example 3: System of Linear Equations
The system:
$$\begin{align}
2x + 3y &= 7 \\
4x - y &= 1
\end{align}$$

Can be represented as: $A\mathbf{x} = \mathbf{b}$ where:

$$A = \begin{pmatrix} 2 & 3 \\ 4 & -1 \end{pmatrix}, \quad \mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}, \quad \mathbf{b} = \begin{pmatrix} 7 \\ 1 \end{pmatrix}$$

