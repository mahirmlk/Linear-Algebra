### Echelon form and solving systems (with augmented matrices)

- **Goal**: Use elementary row operations to simplify a matrix to an easy-to-read form.
- **Two common targets**:
  - **REF (Row Echelon Form)**: staircase of leading 1s (or leading nonzeros) going down-right; zeros below each pivot.
  - **RREF (Reduced Row Echelon Form)**: REF plus each pivot is 1 and is the only nonzero entry in its column.

### Allowed row operations
- **R1 ↔ R2**: swap two rows
- **k·Ri → Ri**: multiply a row by a nonzero scalar k
- **Ri + k·Rj → Ri**: add a multiple of one row to another

### How to reach REF (Gaussian Elimination)
1. Find the leftmost column with a nonzero entry; swap a nonzero row to the top as needed.
2. Scale that row to make the leading entry a 1 (optional for REF but convenient).
3. Use row additions to make all entries below that leading 1 become 0.
4. Move to the submatrix below-right and repeat until no rows left or all zeros.

### How to reach RREF (Gauss–Jordan)
- After REF, continue to clear the entries above each pivot (make them 0) and scale pivots to 1. The result directly gives solutions.

---

### Example 1: Get REF of a matrix (no system yet)
Given
```text
A = [ 1  2  1
      2  5  4
      1  3  3 ]
```
Steps (to REF):
- R2 → R2 − 2·R1, R3 → R3 − 1·R1
```text
[ 1  2  1
  0  1  2
  0  1  2 ]
```
- R3 → R3 − R2
```text
[ 1  2  1
  0  1  2
  0  0  0 ]   (REF)
```
Pivot positions are at columns 1 and 2. Rank(A) = 2.

---

### Example 2: Solve a system using an augmented matrix (to RREF)
Solve
```text
x + 2y −  z =  1
2x + y + 3z =  9
3x + 3y + 2z = 13
```
Augmented matrix:
```text
[ 1  2 −1 |  1 ]
[ 2  1  3 |  9 ]
[ 3  3  2 | 13 ]
```
Eliminate below the first pivot (row 1):
- R2 → R2 − 2·R1, R3 → R3 − 3·R1
```text
[ 1  2 −1 |  1 ]
[ 0 −3  5 |  7 ]
[ 0 −3  5 | 10 ]
```
Eliminate below the second pivot (row 2):
- R3 → R3 − R2
```text
[ 1  2 −1 |  1 ]
[ 0 −3  5 |  7 ]
[ 0  0  0 |  3 ]
```
The last row says 0 = 3, which is impossible. Therefore, the system is **inconsistent** (no solution).

To also see a consistent example, change the right-hand side of the third equation to 12 (so the augmented matrix’s last entry is 12 instead of 13):
```text
[ 1  2 −1 |  1 ]
[ 2  1  3 |  9 ]
[ 3  3  2 | 12 ]
```
Repeat elimination:
- R2 → R2 − 2·R1, R3 → R3 − 3·R1
```text
[ 1  2 −1 |  1 ]
[ 0 −3  5 |  7 ]
[ 0 −3  5 |  9 ]
```
- R3 → R3 − R2
```text
[ 1  2 −1 |  1 ]
[ 0 −3  5 |  7 ]
[ 0  0  0 |  2 ]
```
Again 0 = 2 (inconsistent). Let’s use a different consistent system:
```text
x +  y +  z =  6
2x + 3y + 7z = 20
x + 2y + 4z = 11
```
Augmented matrix and elimination to RREF:
```text
[ 1  1  1 |  6 ]
[ 2  3  7 | 20 ] → R2 − 2·R1 → [ 0  1  5 |  8 ]
[ 1  2  4 | 11 ] → R3 − 1·R1 → [ 0  1  3 |  5 ]

[ 1  1  1 |  6 ]
[ 0  1  5 |  8 ]
[ 0  1  3 |  5 ] → R3 − R2 → [ 0  0 −2 | −3 ]

Scale pivot in row 3: R3 → (−1/2)·R3 → [ 0  0  1 |  3/2 ]
Clear above the z-pivot:
- R2 → R2 − 5·R3 → [ 0  1  0 |  8 − 5·(3/2) ] = [ 0  1  0 |  1/2 ]
- R1 → R1 − 1·R3 → [ 1  1  0 |  6 − 3/2 ] = [ 1  1  0 |  9/2 ]
Clear above the y-pivot:
- R1 → R1 − 1·R2 → [ 1  0  0 |  9/2 − 1/2 ] = [ 1  0  0 |  4 ]
```
RREF is
```text
[ 1  0  0 | 4 ]
[ 0  1  0 | 1/2 ]
[ 0  0  1 | 3/2 ]
```
Thus the unique solution is
- **x = 4**, **y = 1/2**, **z = 3/2**.

---

### Quick checklist
- **REF**: zeros below each pivot; pivots move strictly right as you go down.
- **RREF**: REF plus each pivot is 1 and the only nonzero in its column.
- **Solutions**: read directly from RREF of the augmented matrix; watch for rows like [0 0 … 0 | c] with c ≠ 0 (inconsistent) or free variables (infinitely many solutions).


