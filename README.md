# Numerical Methods I — Course Notes

English LaTeX notes for CSCI-GA 2420 / MATH-GA 2010 (Numerical Methods I), NYU Courant, Fall 2026, taught by Prof. Florian Schaefer. Notes by You Li.

Each chapter covers one lecture. Sections marked (SUPPLEMENT) draw on the textbooks: Trefethen & Bau, *Numerical Linear Algebra*; Demmel, *Applied Numerical Linear Algebra*; and Golub & Van Loan, *Matrix Computations*.

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
```

## Build

Requires a TeX Live installation with `latexmk`.

```sh
latexmk -pdf main.tex   # produces main.pdf
latexmk -c              # remove intermediate files
```

To add a lecture, create `chapters/chN-topic.tex` starting with `\chapter{...}` and add `\include{chapters/chN-topic}` to `main.tex`.
