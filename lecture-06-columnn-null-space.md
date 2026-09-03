# Lecture 6: Column Space and Null Space

## Column Space C(A)

For a matrix A, the **column space** is the set of all linear combinations
of A's columns — every vector you can reach by scaling and adding them
together.

Example: 
A = | 1  3 |
| 2  3 |
| 4  1 |

A has 2 columns, each living in R³ (3 entries per column). Combining
these two columns in every possible weighted way sweeps out a **plane**
through the origin in R³ — that plane is C(A).

**Key idea:** since A only has 2 columns but lives in R³, the column space
is a flat 2-dimensional slice of R³, not all of R³. This means most
vectors in R³ are *not* reachable as Ax — only the ones lying exactly on
that plane.

This connects directly to solving Ax = b: **Ax = b has a solution only
when b lies in C(A)**. If b isn't on the plane (or line, or whatever
shape C(A) takes), there's no solution.

## Null Space N(A)

The **null space** is the set of all solution to:
Ax = 0.

Unlike the column space (which lives in the same space as A's rows —
i.e., Rᵐ, where m = number of rows), the null space lives in **Rⁿ**,
where n = number of columns — because x has as many entries as A has
columns.

### Example:
A = | 1  1  2 |
| 2  1  3 |
| 3  1  4 |
| 4  1  5 |

Solving Ax = 0 for x = (x₁, x₂, x₃):

The solutions form a **line through the origin in R³**, spanned by the
vector (1, 1, -1).

## Why the Null Space Is Always a Subspace

Every subspace must contain the zero vector, and pass the "closed under
addition and scalar multiplication" test.

- Ax = 0 is always satisfied by x = 0, so the zero vector is always in N(A).
- If Av = 0 and Aw = 0, then A(v + w) = Av + Aw = 0 + 0 = 0 — so the sum
  stays in the null space too.
- If Av = 0, then A(cv) = c(Av) = c(0) = 0 for any scalar c.

This is why N(A) is guaranteed to be a subspace, no matter what A is.

## Column Space vs Null Space — Quick Comparison

| | Column Space C(A) | Null Space N(A) |
|---|---|---|
| Lives in | Rᵐ (rows) | Rⁿ (columns) |
| Contains | All possible Ax outputs | All x where Ax = 0 |
| Tells you | Which b's are reachable | Which x's collapse to zero |

## Key Takeaway

The column space and null space are two different lenses on the same
matrix: one describes the *outputs* A can produce, the other describes
the *inputs* A destroys (maps to zero). Both are essential for
understanding whether Ax = b has a solution, and how many solutions
exist.
