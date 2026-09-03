# Lecture 21: Eigenvalues and Eigenvectors

## The Core Idea

For a square matrix A, an **eigenvector** x is a special vector that
doesn't change direction when multiplied by A — it only gets scaled: Ax = λx

Here, **λ (lambda)** is the **eigenvalue** — the scaling factor. Most
vectors get rotated *and* scaled when multiplied by A, but eigenvectors
only get stretched or shrunk along their own direction.

## Finding Eigenvalues

Rearranging Ax = λx: Ax − λx = 0
(A − λI)x = 0

For this to have a nonzero solution x, **(A − λI) must be singular** —
meaning its determinant must be zero: det(A − λI) = 0

This equation is called the **characteristic equation**. Solving it
gives the eigenvalues.

### Worked Example:
A = | 3  1 |
| 0  2 |
A − λI = | 3−λ    1   |
|  0    2−λ  |

Solving: λ = 3 or λ = 2 — two eigenvalues.

## Finding Eigenvectors

Once you have an eigenvalue λ, plug it back into (A − λI)x = 0 and solve
for x — this is just finding the null space of (A − λI).

For λ = 3: (A − 2I) = | 1  1 |
| 0  0 |

Solving gives x = (1, -1) — the eigenvector for λ = 2.

## Key Facts Worth Remembering

- **Sum of eigenvalues = trace of A** (sum of diagonal entries) — quick
  sanity check: 3 + 2 = 5, and trace(A) = 3 + 2 = 5 ✓
- **Product of eigenvalues = determinant of A** — check: 3 × 2 = 6, and
  det(A) = (3)(2) − (1)(0) = 6 ✓
- An **n × n matrix has exactly n eigenvalues** (counting repeats,
  allowing complex numbers)
- If A is **triangular** (upper or lower), the eigenvalues are simply
  the diagonal entries — no computation needed

## Why Eigenvalues Matter

Eigenvalues describe how a matrix behaves when applied repeatedly (Aⁿ),
which is central to understanding stability in systems, powers of
matrices, differential equations, and — directly relevant to ML — why
PCA (principal component analysis) works: PCA finds the eigenvectors of
a covariance matrix to identify the directions of greatest variance in
data.
