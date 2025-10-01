# Vector Dot Product:

## Introduction

The **dot product** (also called **scalar product** or **inner product**) is a fundamental operation in linear algebra that takes two vectors and returns a scalar (single number). It's one of the most important operations for understanding vector relationships, angles, and projections.

## Definition

For two vectors $\vec{a} = \begin{pmatrix} a_1 \\ a_2 \\ a_3 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} b_1 \\ b_2 \\ b_3 \end{pmatrix}$, the dot product is defined as:

$$\vec{a} \cdot \vec{b} = a_1b_1 + a_2b_2 + a_3b_3$$

### General Formula

For n-dimensional vectors:
$$\vec{a} \cdot \vec{b} = \sum_{i=1}^{n} a_i b_i$$

## Examples

### Example 1: Simple 2D Vectors

Let $\vec{a} = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$ and $\vec{b} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$

**Solution:**
$$\vec{a} \cdot \vec{b} = (3)(2) + (4)(1) = 6 + 4 = 10$$

### Example 2: 3D Vectors

Let $\vec{u} = \begin{pmatrix} 1 \\ -2 \\ 3 \end{pmatrix}$ and $\vec{v} = \begin{pmatrix} 4 \\ 0 \\ -1 \end{pmatrix}$

**Solution:**
$$\vec{u} \cdot \vec{v} = (1)(4) + (-2)(0) + (3)(-1) = 4 + 0 - 3 = 1$$

### Example 3: Zero Dot Product

Let $\vec{p} = \begin{pmatrix} 2 \\ 3 \end{pmatrix}$ and $\vec{q} = \begin{pmatrix} -3 \\ 2 \end{pmatrix}$

**Solution:**
$$\vec{p} \cdot \vec{q} = (2)(-3) + (3)(2) = -6 + 6 = 0$$

*Note: When the dot product is zero, the vectors are perpendicular (orthogonal).*

## Key Properties

### 1. Commutative Property
$$\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$$

**Example:**
$$\begin{pmatrix} 2 \\ 3 \end{pmatrix} \cdot \begin{pmatrix} 1 \\ 4 \end{pmatrix} = (2)(1) + (3)(4) = 14$$
$$\begin{pmatrix} 1 \\ 4 \end{pmatrix} \cdot \begin{pmatrix} 2 \\ 3 \end{pmatrix} = (1)(2) + (4)(3) = 14$$

### 2. Distributive Property
$$\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$$

### 3. Scalar Multiplication
$$(k\vec{a}) \cdot \vec{b} = k(\vec{a} \cdot \vec{b}) = \vec{a} \cdot (k\vec{b})$$

**Example:**
Let $\vec{a} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$, $\vec{b} = \begin{pmatrix} 3 \\ 1 \end{pmatrix}$, and $k = 2$

$$(2\vec{a}) \cdot \vec{b} = \begin{pmatrix} 2 \\ 4 \end{pmatrix} \cdot \begin{pmatrix} 3 \\ 1 \end{pmatrix} = 6 + 4 = 10$$
$$2(\vec{a} \cdot \vec{b}) = 2[(1)(3) + (2)(1)] = 2(5) = 10$$

### 4. Dot Product with Zero Vector
$$\vec{a} \cdot \vec{0} = 0$$

### 5. Dot Product of a Vector with Itself
$$\vec{a} \cdot \vec{a} = |\vec{a}|^2$$

**Example:**
$$\begin{pmatrix} 3 \\ 4 \end{pmatrix} \cdot \begin{pmatrix} 3 \\ 4 \end{pmatrix} = 3^2 + 4^2 = 9 + 16 = 25 = 5^2$$

## Geometric Interpretation

The dot product has a beautiful geometric meaning:

$$\vec{a} \cdot \vec{b} = |\vec{a}||\vec{b}|\cos\theta$$

Where:
- $|\vec{a}|$ and $|\vec{b}|$ are the magnitudes (lengths) of the vectors
- $\theta$ is the angle between the vectors

### Finding the Angle Between Vectors

From the geometric formula, we can find the angle:
$$\cos\theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}||\vec{b}|}$$

**Example:**
Find the angle between $\vec{u} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ and $\vec{v} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$

**Solution:**
1. Calculate dot product: $\vec{u} \cdot \vec{v} = (1)(1) + (1)(0) = 1$
2. Calculate magnitudes: $|\vec{u}| = \sqrt{1^2 + 1^2} = \sqrt{2}$, $|\vec{v}| = \sqrt{1^2 + 0^2} = 1$
3. Find angle: $\cos\theta = \frac{1}{\sqrt{2} \cdot 1} = \frac{1}{\sqrt{2}} = \frac{\sqrt{2}}{2}$
4. Therefore: $\theta = 45°$

## Special Cases

### 1. Parallel Vectors
When vectors are parallel (same or opposite direction):
- Same direction: $\vec{a} \cdot \vec{b} = |\vec{a}||\vec{b}|$ (cos 0° = 1)
- Opposite direction: $\vec{a} \cdot \vec{b} = -|\vec{a}||\vec{b}|$ (cos 180° = -1)

### 2. Perpendicular Vectors
When vectors are perpendicular: $\vec{a} \cdot \vec{b} = 0$ (cos 90° = 0)

### 3. Unit Vectors
For unit vectors (magnitude = 1): $\vec{a} \cdot \vec{b} = \cos\theta$

## Practical Applications

### 1. Work in Physics
Work = Force · Displacement
$$W = \vec{F} \cdot \vec{d}$$

### 2. Projection of One Vector onto Another
The projection of $\vec{a}$ onto $\vec{b}$ is:
$$\text{proj}_{\vec{b}}\vec{a} = \frac{\vec{a} \cdot \vec{b}}{|\vec{b}|^2}\vec{b}$$

### 3. Checking Orthogonality
Two vectors are perpendicular if and only if their dot product is zero.


- $|\vec{u}| = 5$, $|\vec{v}| = \sqrt{2}$
- $\cos\theta = \frac{7}{5\sqrt{2}} = \frac{7\sqrt{2}}{10}$
- $\theta \approx 8.13°$


## Summary

The dot product is a powerful tool that:
- Combines two vectors to produce a scalar
- Reveals geometric relationships (angles, orthogonality)
- Has many practical applications in physics and engineering
- Follows intuitive algebraic properties
- Provides a foundation for more advanced linear algebra concepts

