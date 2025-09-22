### Basis and Dimension

Definitions (vector space `V` over a field `F`):
- **Span** of vectors `v1, …, vk`: all linear combinations `a1 v1 + ··· + ak vk` with `ai ∈ F`.
- **Linear independence**: `v1, …, vk` are independent if the only solution of `a1 v1 + ··· + ak vk = 0` is `a1 = ··· = ak = 0`.
- **Basis**: a set of vectors that is both spanning and linearly independent.
- **Dimension**: the number of vectors in any basis of `V` (all bases have the same size).

Core facts (finite-dimensional `V`):
- If `dim(V)=n` and you have `n` independent vectors in `V`, they automatically form a basis (so they span).
- If `dim(V)=n` and you have `n` spanning vectors, they are automatically independent.
- Any independent set can be extended to a basis; any spanning set can be reduced to a basis.
- The zero vector cannot belong to a basis.

Coordinates and change of basis:
- Given a basis `B = (b1, …, bn)`, every `v ∈ V` is uniquely written `v = c1 b1 + ··· + cn bn`.
- The coefficients `(c1, …, cn)` are the coordinates of `v` in basis `B`.
- Changing coordinates between two bases uses an invertible change‑of‑basis matrix.

How to check a set is a basis (practical):
- Put candidate vectors as columns of a matrix and row‑reduce (RREF):
  - In an `n`‑dimensional space, if there are `n` pivot columns, the set is a basis.
  - Pivot columns identify a maximal independent subset; they also form a basis of the span.

Separate examples
1) `R^2`:
   - Standard basis: `{(1,0), (0,1)}`; `dim(R^2)=2`.
   - Another basis: `{(1,1), (1,-1)}` (matrix has nonzero determinant `-2`).

2) `R^3`:
   - Standard basis: `{(1,0,0), (0,1,0), (0,0,1)}`; `dim(R^3)=3`.
   - Another basis: `{(1,1,0), (0,1,1), (1,0,1)}` (independent and spans `R^3`).

3) `P_2` (polynomials of degree ≤ 2):
   - Basis: `{1, x, x^2}`; `dim(P_2)=3`.
   - Any `ax^2 + bx + c` has unique coordinates `(c, b, a)` in this basis.

4) `M_{2×2}(R)` (all 2×2 real matrices):
   - Basis: {E11, E12, E21, E22} where `Eij` has 1 at `(i,j)` and 0 elsewhere.
   - `dim = 4`. Any 2×2 matrix is a unique linear combo of these four.

5) A 1D subspace (a line through the origin in `R^2`):
   - U = span{(1,2)}; basis {(1,2)}; dim(U)=1.



