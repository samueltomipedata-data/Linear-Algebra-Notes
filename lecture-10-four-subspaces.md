# Lecture 10: The Four Fundamental Subspaces

Every matrix A (size m × n, rank r) has exactly four subspaces attached
to it. Understanding these four — where they live, their dimensions,
and how to find a basis for each — ties together everything from
elimination through solving Ax = b.

## The Four Subspaces

| Subspace | Notation | Lives in | Dimension |
|---|---|---|---|
| Column Space | C(A) | Rᵐ | r |
| Row Space | C(Aᵀ) | Rⁿ | r |
| Null Space | N(A) | Rⁿ | n − r |
| Left Null Space | N(Aᵀ) | Rᵐ | m − r |

**Key pairing:** row space and null space both live in Rⁿ (they turn out
to be perpendicular complements of each other). Column space and left
null space both live in Rᵐ.

## Where Each Basis Comes From

- **Row space basis** = the nonzero rows of R (the reduced echelon form)
- **Null space basis** = the special solutions — one per free variable,
  found by setting each free variable to 1 (others to 0) and solving
  for the pivot variables
- **Column space basis** = the **pivot columns of the original A**
  (not R — this is a common mix-up; R's pivot columns tell you *which*
  columns of A to pick, but you take them from A itself)
- **Left null space basis** = solve Aᵀy = 0, same method as finding N(A)
  but applied to Aᵀ

## Why Row Space and Column Space Have the Same Dimension

This is one of the most surprising facts in linear algebra: even for a
non-square matrix, **dim(row space) = dim(column space) = rank(A)**.
Rows and columns "agree" on this number even though they live in
completely different spaces (Rⁿ vs Rᵐ).

## Worked Example:
A = | 1  2  3  1 |
| 1  1  2  1 |
| 1  2  3  1 |

Row reduce → R = 
| 1  2  3  1 |
| 0 -1 -1  0 |
| 0  0  0  0 |

- Rank r = 2 (two nonzero rows / two pivots)
- Row space: basis is the first 2 rows of R → dimension 2
- Column space: basis is columns 1 and 2 of the *original* A → dimension 2
- Null space: 4 − 2 = 2 free variables → dimension 2
- Left null space: 3 − 2 = 1 → dimension 1

Note: C(R) ≠ C(A) in general — row reduction changes the column space —
but the row space stays the same throughout elimination.

## The Big Picture

Once you know a matrix's shape (m × n) and its rank (r), you immediately
know the dimension of all four fundamental subspaces:

- C(A): dimension r, in Rᵐ
- N(A): dimension n − r, in Rⁿ
- C(Aᵀ): dimension r, in Rⁿ
- N(Aᵀ): dimension m − r, in Rᵐ

This single relationship — **n = r + (n − r)** — is the thread that
connects rank, solvability of Ax = b, uniqueness of solutions, and the
size of every fundamental subspace.
