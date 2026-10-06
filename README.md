# Numerical Methods I Notes

My LaTeX notes for CSCI-GA 2420 / MATH-GA 2010 (Numerical Methods I) at NYU Courant, Fall 2026, taught by Prof. Florian Schaefer.

Each chapter is one lecture. Things that come up again and again (norms, the SVD, floating point) are collected in the appendices so I don't have to repeat them. Sections marked (SUPPLEMENT) go past what was said in class; for those I mostly used Trefethen & Bau, Demmel, and Golub & Van Loan.

## Files

```
main.tex          title page, notation, bibliography
nm1notes.sty      layout, the theorem/definition boxes, macros
chapters/
  ch1-floating-point.tex    L1: floating point, conditioning, stability
  ch2-performance.tex       L2: storage, performance, Gaussian elimination
  ch3-lu.tex                L3: LU factorization
  ch4-pivoting.tex          L4: error analysis of LU, partial pivoting
  ch5-least-squares.tex     L5: least squares, Gram–Schmidt
  ch6-householder.tex       L6: Householder QR
  ch7-qr.tex                L7: implicit Q, Givens rotations, existence and uniqueness of QR
  ch8-normal-equations.tex  L8: normal equations, Gram matrices
  ch9-cholesky.tex          L9: Cholesky, Schur complements
  appA-norms.tex            Appendix A: unitary matrices, 2-norm and SVD, Frobenius norm
  appB-floating-point.tex   Appendix B: IEEE formats, machine epsilon, backward stability
```

## Building

You need TeX Live with `latexmk`.

```sh
latexmk -pdf main.tex   # builds main.pdf
latexmk -c              # cleans up the aux files
```

For a new lecture, add `chapters/chN-topic.tex` (starting with `\chapter{...}`) and an `\include` line in `main.tex`.

## Questions

`questions/` is a separate little document where I keep questions I have about the course, one file per lecture (`questions/lectures/lecNN.tex`). Each one goes in a `question` environment with an `answer` after it; if I haven't figured it out yet, the answer is just `\unanswered`. Build it the same way from inside `questions/`; its `.latexmkrc` points at `../nm1notes.sty`.
