# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a LaTeX academic paper titled "Cryptographic perfect hash functions: A theoretical analysis on space efficiency and algebraic composition" by Alexander Towell.

The paper analyzes theoretical cryptographic perfect hash functions with three key properties:
1. They are cryptographic hash functions
2. Their in-place encoding obtains the theoretical lower-bound for expected space complexity
3. Their in-place encoding is a random bit string with maximum entropy

## Repository Structure

- `paper.tex` - Main LaTeX source file
- `references.bib` - BibTeX bibliography file
- `img/` - Figures and plots (PDF, EPS, TEX formats) included in the paper
- `research/` - Mathematica notebooks (.nb) for derivations and plot generation

## Building the Paper

```bash
# Full build with bibliography
pdflatex paper.tex && bibtex paper && pdflatex paper.tex && pdflatex paper.tex

# Or use latexmk for automatic dependency handling
latexmk -pdf paper.tex

# Clean build artifacts
latexmk -c paper.tex
```

## Custom LaTeX Macros

Key macros defined in `paper.tex`:
- `\Fun{name}` - Function notation
- `\PH`, `\ph` - Perfect hash data type and constructor
- `\Expect{X}` - Expectation operator E[X]
- `\BL` - Bit length function
- `\cat` - Concatenation operator (#)
- `\PS{X}` - Power set notation
- `\geodist` - Geometric distribution
- `\MinHash`, `\MaxHash` - Hash bound functions

Algorithm keywords: `\Break`, `\True`, `\False`

Theorem environments: `theorem`, `corollary`, `definition`, `postulate`, `conjecture`, `example`, `remark`

## Research Materials

Mathematica notebooks in `research/`:
- `paper_pf.nb` - Main paper derivations
- `perfhash.nb` - Perfect hash analysis
- `cryptoph_with_fn.nb` - Cryptographic properties with function composition
- `logq.nb`, `math1.nb` - Supporting mathematical computations

Plots are exported to `img/` as PDF/EPS/TEX for LaTeX inclusion.
