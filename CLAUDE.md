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
- `img/` - Directory containing generated figures and plots (PDF, EPS, TEX formats)
- `html/` - HTML export of the paper
- `research/` - Mathematica notebooks (.nb) and related research materials
- `archive/` - Previous versions of the paper
- `paper.pdf` - Compiled output

## Working with LaTeX

### Building the Paper

Compile the paper using:
```bash
pdflatex paper.tex
bibtex paper
pdflatex paper.tex
pdflatex paper.tex
```

Or use latexmk for automatic dependency handling:
```bash
latexmk -pdf paper.tex
```

### Key LaTeX Packages Used

- `algorithm2e` - For algorithm pseudocode (Algorithms 1-3)
- `amsmath`, `amsthm`, `amssymb` - Mathematical notation and theorem environments
- `natbib` - Bibliography management with `\cite{}`
- `hyperref` - PDF hyperlinks and metadata

### Custom Macros and Environments

The paper defines several custom commands:
- `\Fun{name}` - Function notation
- `\PH`, `\ph` - Perfect hash data type and constructor
- `\Expect{X}` - Expectation operator
- `\BL` - Bit length function
- `\cat` - Concatenation operator (#)
- Theorem environments: `theorem`, `corollary`, `definition`, `postulate`, `conjecture`, `example`, `remark`

## Mathematical Content

The paper presents:
1. **Section 2**: Perfect hash function fundamentals
2. **Section 3**: Cryptographic perfect hash functions using random oracles (Algorithm 1)
3. **Section 4**: Two-level practical perfect hash functions (Algorithm 2)
4. **Section 5**: Algebra of function composition
5. **Appendix**: Probability mass of random bit length (Algorithm 3)

Key theoretical results:
- Expected space complexity: 1.44 bits/element for minimal perfect hash (load factor r=1)
- General formula: log₂(e) - (1/r - 1)log₂(1/(1-r)) bits/element

## Research Materials

The `research/` directory contains Mathematica notebooks (.nb files) for:
- Mathematical derivations and proofs
- Plot generation (SVG, EPS formats)
- Performance analysis

Generated plots are exported to `img/` for inclusion in the paper.
