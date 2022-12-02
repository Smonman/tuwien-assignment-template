# tuwien-assignment-template
An inofficial Latex template for TU Vienna assignments.

This Latex template aims to streamline the writing of assignments written digitally.

## Why should I use this template?

## How do I use this template?

## What can this template do?

### Math

The packages [`amsmath`](https://ctan.org/pkg/amsmath), `amssymb`, [`mathtools`](https://ctan.org/pkg/mathtools) and [`amsthm`](https://ctan.org/pkg/amsthm) are already supplied via the template. Writing proofs and theorems can be done easily via the environments provided by the `amsthm` package. Take a look at [this guide](https://de.overleaf.com/learn/latex/Theorems_and_proofs) for more details.

Moreover some math-related commands are changed or added:

- `\abs` and `\norm` now scale with the content
- `\mset{}` creates a simple set, with scaling braces and spacing
- `\msetempty` creates an empty set
- `\mtupel{}` creates a simple tupel, with angled brackets and spacing
- `\mtupelempty` creates an empty tupel
- `conditions` is an environment to list mathematical conditions or explanations

### Language

The package [`babel`](https://ctan.org/pkg/babel) is used for language support. With the standard being Englisch. Additionally the package [`csqotes`](https://ctan.org/pkg/csquotes) is imported, for correct qotes based on the primary language selected via `babel`.


## Changelog

### 0.1.0 first version
