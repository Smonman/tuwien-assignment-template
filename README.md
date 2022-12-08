# tuwien-assignment-template

An inofficial Latex template for TU Vienna assignments. Take a look at the [example](https://github.com/Smonman/tuwien-assignment-template/blob/main/example.pdf).

_This Latex template aims to streamline the writing of digital assignments._

## Why should I use this template?

Writing assignments isn't necessarily a joyful activity. Out of a need to reduce workload this template was written. It's purpose is not to be an efficient lightweight template but rather a fully loaded, plug-and-play, out of the box template. It provides additional commands to help specificly with assignments. The idea was that one can start working using this template, without worring about packages to import or settings to change.

## How do I use this template?

Download the latest version of this template [here](https://github.com/Smonman/tuwien-assignment-template/releases). When using [Overleaf](https://www.overleaf.com/project) press "New Project" > "Upload Project" and select the downloaded ZIP archive.

## What can this template do?

This template comes with a sleek design that is kept closely to the originial Latex article style. It also provides environments for exercises and solutions. Which are conveniently numbered.

### Exercises and Solutions

`exercise` is an environment for the exercises, including the solutions. Exercises are numbered within a `section`. The idea is, that each section represents a singe exercise sheet. Inside of this `exercise` environment can multiple `solution` environments be declared. These are numbered within the parent exercise environment.

There are also minute possibilities to customise these environments. Each `exercise` environment has the following keys:

- `title` the title of the exercise (default "Exercise")
- `solution/title` the title for the solution declared within the exercise (default "Solution")

#### Customization

If a specific solution counter should be set to a specific value, this can be done via the

```tex
\setcounter{solutioncounter}{x}
```

macro, where `x` is the new starting number for the counter.
> **Note**: that the following solutions will also be affected.

If the numbering style of the solutions within an `exercise` environment should be changed, this currently cannot be done via keys, but has to be done _manually_ via the command:

```tex
\renewcommand{\thesolutioncounter}{(\roman{solutioncounter})}
```

at the top inside of the corresponding `exercise` environment. In this case, the enumeration will be lowercase roman numerals in braces.

### Math

The packages [`amsmath`](https://ctan.org/pkg/amsmath), `amssymb`, [`mathtools`](https://ctan.org/pkg/mathtools) and [`amsthm`](https://ctan.org/pkg/amsthm) are already supplied via the template. Writing proofs and theorems can be done easily via the environments provided by the `amsthm` package. Take a look at [this guide](https://de.overleaf.com/learn/latex/Theorems_and_proofs) for more details.

Moreover some math-related commands are changed or added:

- `\abs` and `\norm` now scale with the content
- `\mset{}` creates a simple set, with scaling braces and spacing
- `\msetempty` creates an empty set
- `\mtupel{}` creates a simple tupel, with angled brackets and spacing
- `\mtupelempty` creates an empty tupel
- `conditions` is an environment to list mathematical conditions or explanations
- `\ltrue` is an alias for verum
- `\lfalse` is an alias for falsum

For more details regarding Latex in general take a look at this [cheatsheet](https://de.overleaf.com/latex/templates/a-quick-guide-to-latex/fghqpfgnxggz).

### Language

The package [`babel`](https://ctan.org/pkg/babel) is used for language support. With the standard being Englisch. Additionally the package [`csqotes`](https://ctan.org/pkg/csquotes) is imported, for correct qotes based on the primary language selected via `babel`.

### Code

The package [`listings`](https://ctan.org/pkg/listings) is imported for displaying code. Also a style for code output and pseudocode are provided. The standard path for script files is set to `./scripts/`. This can be changed with the

```tex
\lstinputpath{{<path>}}
```

command.

### Graphics

The standard `graphicspath` is set to `./img/`. This can be changed with the

```tex
\graphicspath{{<path>}}
```

command.

## Changelog

### 0.1.1

- add listings file path
- listings now show linebreaks resulted from long lines

### 0.1.0 first version
