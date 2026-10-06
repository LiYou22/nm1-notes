# Numerical Methods I — Course Notes

LaTeX notes for CSCI-GA 2420 / MATH-GA 2010 (Numerical Methods I), NYU Courant, Fall 2026, taught by Prof. Florian Schaefer. Notes by You Li.

Each chapter covers one lecture; sections marked (SUPPLEMENT) extend that lecture, and background used throughout the course lives in the appendices. Supplements are based on the textbooks: Trefethen & Bau, *Numerical Linear Algebra*; Demmel, *Applied Numerical Linear Algebra*; and Golub & Van Loan, *Matrix Computations*.

## Layout

```
main.tex          title page, notation, bibliography; includes the chapters
nm1notes.sty      page layout, boxed theorem/definition environments, macros
chapters/
  ch1-floating-point.tex    Lecture 1: floating point, conditioning, stability
  ch2-performance.tex       Lecture 2: storage, performance, Gaussian elimination
  ch3-lu.tex                Lecture 3: the LU factorization
  ch4-pivoting.tex          Lecture 4: error analysis of LU, partial pivoting
  ch5-least-squares.tex     Lecture 5: least squares, Gram–Schmidt
  ch6-householder.tex       Lecture 6: products of factors, Householder QR
  ch7-qr.tex                Lecture 7: implicit Q, Givens, existence/uniqueness of QR
  ch8-normal-equations.tex  Lecture 8: optimality conditions, normal equations, Gram matrices
  ch9-cholesky.tex          Lecture 9: Cholesky factorization, Schur complements
  appA-norms.tex            Appendix A: unitary matrices, 2-norm and SVD, Frobenius norm
  appB-floating-point.tex   Appendix B: IEEE formats, machine epsilon, the fp model, backward stability
```

## Build

Requires a TeX Live installation with `latexmk`.

```sh
latexmk -pdf main.tex   # produces main.pdf
latexmk -c              # remove intermediate files
```

To add a lecture, create `chapters/chN-topic.tex` starting with `\chapter{...}` and add `\include{chapters/chN-topic}` to `main.tex`.

## Questions

`questions/` is a separate document collecting my questions about the course, one file per lecture (`questions/lectures/lecNN.tex`). Use the `question` and `answer` environments; write `\unanswered` inside `answer` for questions that are still open. Build it the same way from inside `questions/` (its `.latexmkrc` picks up `../nm1notes.sty`).
