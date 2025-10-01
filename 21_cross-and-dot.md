# Vector Cross Product: 

## Introduction

The **cross product** (also called **vector product**) is a fundamental operation in linear algebra that takes two vectors and returns a third vector that is perpendicular to both input vectors. Unlike the dot product which returns a scalar, the cross product returns a vector.

## Definition

For two vectors $\vec{a} = \begin{pmatrix} a_1 \\ a_2 \\ a_3 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} b_1 \\ b_2 \\ b_3 \end{pmatrix}$, the cross product is defined as:

$$\vec{a} \times \vec{b} = \begin{pmatrix} a_2b_3 - a_3b_2 \\ a_3b_1 - a_1b_3 \\ a_1b_2 - a_2b_1 \end{pmatrix}$$

### Determinant Method

The cross product can also be calculated using the determinant of a 3×3 matrix:

$$\vec{a} \times \vec{b} = \begin{vmatrix} \hat{i} & \hat{j} & \hat{k} \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{vmatrix}$$

Expanding this determinant:
$$\vec{a} \times \vec{b} = \hat{i}(a_2b_3 - a_3b_2) - \hat{j}(a_1b_3 - a_3b_1) + \hat{k}(a_1b_2 - a_2b_1)$$

## Examples

### Example 1: Basic 3D Vectors

Let $\vec{a} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix}$

**Solution:**
$$\vec{a} \times \vec{b} = \begin{pmatrix} (2)(6) - (3)(5) \\ (3)(4) - (1)(6) \\ (1)(5) - (2)(4) \end{pmatrix} = \begin{pmatrix} 12 - 15 \\ 12 - 6 \\ 5 - 8 \end{pmatrix} = \begin{pmatrix} -3 \\ 6 \\ -3 \end{pmatrix}$$

### Example 2: Simple Unit Vectors

Let $\vec{i} = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ and $\vec{j} = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$

**Solution:**
$$\vec{i} \times \vec{j} = \begin{pmatrix} (0)(0) - (0)(1) \\ (0)(0) - (1)(0) \\ (1)(1) - (0)(0) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} = \vec{k}$$

### Example 3: Parallel Vectors

Let $\vec{u} = \begin{pmatrix} 2 \\ 4 \\ 6 \end{pmatrix}$ and $\vec{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ (Note: $\vec{u} = 2\vec{v}$)

**Solution:**
$$\vec{u} \times \vec{v} = \begin{pmatrix} (4)(3) - (6)(2) \\ (6)(1) - (2)(3) \\ (2)(2) - (4)(1) \end{pmatrix} = \begin{pmatrix} 12 - 12 \\ 6 - 6 \\ 4 - 4 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} = \vec{0}$$

*Note: When vectors are parallel, their cross product is the zero vector.*

## Key Properties

### 1. Anti-Commutative Property
$$\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$$

**Example:**
$$\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} \times \begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix} = \begin{pmatrix} -3 \\ 6 \\ -3 \end{pmatrix}$$
$$\begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix} \times \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} = \begin{pmatrix} 3 \\ -6 \\ 3 \end{pmatrix} = -\begin{pmatrix} -3 \\ 6 \\ -3 \end{pmatrix}$$

### 2. Distributive Property
$$\vec{a} \times (\vec{b} + \vec{c}) = \vec{a} \times \vec{b} + \vec{a} \times \vec{c}$$

### 3. Scalar Multiplication
$$(k\vec{a}) \times \vec{b} = k(\vec{a} \times \vec{b}) = \vec{a} \times (k\vec{b})$$

**Example:**
Let $\vec{a} = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$, $\vec{b} = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$, and $k = 3$

$$(3\vec{a}) \times \vec{b} = \begin{pmatrix} 3 \\ 0 \\ 0 \end{pmatrix} \times \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 3 \end{pmatrix}$$
$$3(\vec{a} \times \vec{b}) = 3\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 3 \end{pmatrix}$$

### 4. Cross Product with Zero Vector
$$\vec{a} \times \vec{0} = \vec{0}$$

### 5. Cross Product of a Vector with Itself
$$\vec{a} \times \vec{a} = \vec{0}$$

### 6. Cross Product with Parallel Vectors
If $\vec{a}$ and $\vec{b}$ are parallel, then $\vec{a} \times \vec{b} = \vec{0}$

## Geometric Interpretation

### Magnitude
The magnitude of the cross product is:
$$|\vec{a} \times \vec{b}| = |\vec{a}||\vec{b}|\sin\theta$$

Where $\theta$ is the angle between the vectors.

### Direction
The cross product $\vec{a} \times \vec{b}$ is perpendicular to both $\vec{a}$ and $\vec{b}$, and its direction follows the **right-hand rule**:
1. Point your right index finger in the direction of $\vec{a}$
2. Curl your fingers toward $\vec{b}$
3. Your thumb points in the direction of $\vec{a} \times \vec{b}$

### Area Interpretation
The magnitude of the cross product equals the area of the parallelogram formed by the two vectors:
$$\text{Area} = |\vec{a} \times \vec{b}|$$

## Special Cases

### 1. Perpendicular Vectors
When vectors are perpendicular: $|\vec{a} \times \vec{b}| = |\vec{a}||\vec{b}|$ (sin 90° = 1)

### 2. Parallel Vectors
When vectors are parallel: $\vec{a} \times \vec{b} = \vec{0}$ (sin 0° = sin 180° = 0)

### 3. Unit Vectors
For unit vectors: $|\vec{a} \times \vec{b}| = \sin\theta$

## Practical Applications

### 1. Torque in Physics
Torque = Position × Force
$$\vec{\tau} = \vec{r} \times \vec{F}$$

### 2. Angular Momentum
Angular momentum = Position × Momentum
$$\vec{L} = \vec{r} \times \vec{p}$$

### 3. Finding Normal Vectors
The cross product of two vectors gives a normal vector to the plane containing both vectors.

### 4. Volume of Parallelepiped
The scalar triple product $|\vec{a} \cdot (\vec{b} \times \vec{c})|$ gives the volume of the parallelepiped formed by three vectors.


**Answer:** 
$$\vec{a} \times \vec{b} = \begin{pmatrix} (-1)(-2) - (3)(4) \\ (3)(1) - (2)(-2) \\ (2)(4) - (-1)(1) \end{pmatrix} = \begin{pmatrix} 2 - 12 \\ 3 + 4 \\ 8 + 1 \end{pmatrix} = \begin{pmatrix} -10 \\ 7 \\ 9 \end{pmatrix}$$


---

# Comparison: Dot Product vs Cross Product

## Fundamental Differences

| Aspect | Dot Product | Cross Product |
|--------|-------------|---------------|
| **Input** | Two vectors | Two vectors |
| **Output** | Scalar (number) | Vector |
| **Notation** | $\vec{a} \cdot \vec{b}$ | $\vec{a} \times \vec{b}$ |
| **Dimension** | Works in any dimension | Only works in 3D (and 7D) |

## Mathematical Formulas

### Dot Product
$$\vec{a} \cdot \vec{b} = a_1b_1 + a_2b_2 + a_3b_3 = |\vec{a}||\vec{b}|\cos\theta$$

### Cross Product
$$\vec{a} \times \vec{b} = \begin{pmatrix} a_2b_3 - a_3b_2 \\ a_3b_1 - a_1b_3 \\ a_1b_2 - a_2b_1 \end{pmatrix}$$
$$|\vec{a} \times \vec{b}| = |\vec{a}||\vec{b}|\sin\theta$$

## Geometric Interpretations

### Dot Product
- **Measures**: How much one vector "points in the same direction" as another
- **Zero when**: Vectors are perpendicular
- **Maximum when**: Vectors are parallel (same direction)
- **Minimum when**: Vectors are parallel (opposite direction)

### Cross Product
- **Measures**: How much one vector "rotates around" another
- **Zero when**: Vectors are parallel
- **Maximum when**: Vectors are perpendicular
- **Direction**: Perpendicular to both input vectors

## Algebraic Properties

### Commutativity
- **Dot Product**: $\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$  **Commutative**
- **Cross Product**: $\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$  **Anti-commutative**

### Distributivity
- **Both**: $\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$ 
- **Both**: $\vec{a} \times (\vec{b} + \vec{c}) = \vec{a} \times \vec{b} + \vec{a} \times \vec{c}$ 

## Practical Applications

### Dot Product Applications
- **Physics**: Work = Force · Displacement
- **Computer Graphics**: Lighting calculations, projections
- **Machine Learning**: Similarity measures, neural networks
- **Geometry**: Finding angles, checking orthogonality

### Cross Product Applications
- **Physics**: Torque, angular momentum, magnetic fields
- **Computer Graphics**: Normal vectors, surface orientation
- **Engineering**: Moment calculations, structural analysis
- **Geometry**: Finding perpendicular vectors, area calculations

## Side-by-Side Example

Let $\vec{a} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix}$

### Dot Product Calculation
$$\vec{a} \cdot \vec{b} = (1)(4) + (2)(5) + (3)(6) = 4 + 10 + 18 = 32$$

### Cross Product Calculation
$$\vec{a} \times \vec{b} = \begin{pmatrix} (2)(6) - (3)(5) \\ (3)(4) - (1)(6) \\ (1)(5) - (2)(4) \end{pmatrix} = \begin{pmatrix} -3 \\ 6 \\ -3 \end{pmatrix}$$

## When to Use Which?

### Use Dot Product When:
- Finding angles between vectors
- Calculating projections
- Measuring similarity/direction alignment
- Working in any dimension
- Need a scalar result

### Use Cross Product When:
- Finding perpendicular vectors
- Calculating areas or volumes
- Working with torque or rotation
- Need a vector result
- Working in 3D space

## Relationship Between Them

The dot and cross products are related through the **scalar triple product**:
$$\vec{a} \cdot (\vec{b} \times \vec{c}) = \vec{b} \cdot (\vec{c} \times \vec{a}) = \vec{c} \cdot (\vec{a} \times \vec{b})$$

This gives the volume of the parallelepiped formed by the three vectors.

## Summary

Both dot and cross products are essential tools in linear algebra:

- **Dot Product**: Measures alignment and similarity, works in any dimension, returns scalars
- **Cross Product**: Measures rotation and perpendicularity, works in 3D, returns vectors


