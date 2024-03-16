# tuwien-assignment-template

An inofficial Latex template for TU Vienna assignments. Take a look at the [example](https://github.com/Smonman/tuwien-assignment-template/blob/main/example.pdf).

_This Latex template aims to streamline the writing of digital assignments._

## Why should I use this template?

Writing assignments isn't necessarily a joyful activity. Out of a need to reduce workload this template was written. Its purpose is not to be an efficient lightweight template but rather a fully loaded, plug-and-play, out of the box template. It provides additional commands to help specificly with assignments. The idea was that one can start working using this template, without worring about packages to import or settings to change.

## How do I use this template?

Download the latest version of this template [here](https://github.com/Smonman/tuwien-assignment-template/releases). When using [Overleaf](https://www.overleaf.com/project) press "New Project" > "Upload Project" and select the downloaded ZIP archive.

## What can this template do?

This template comes with a sleek design that is kept closely to the originial Latex article style. It also provides environments for exercises and solutions. Which are conveniently numbered.

This template loads a bunch of other packages:

- `geometry`
- `inputenc`
- `fontenc`
- `babel`
- `csquotes`
- `iflang`
- `ifthen`
- `parskip`
- `titling`
- `fancyhdr`
- `amsmath`
- `amssymb`
- `mathtools`
- `amsthm`
- `siunix`
- `microtype`
- `enumitem`
- `graphicx`
- `array`
- `xcolor`
- `fp`
- `booktabs`
- `tabularx`
- `xltabular`
- `nicematrix`
- `multirow`
- `makecell`
- `listings`
- `pgfkeys`
- `tikz`
- `varwidth`
- `float`
- `hyperref`

### Exercises and Solutions

`exercise` is an environment for the exercises, including the solutions. Exercises are numbered within a `section`. The idea is, that each section represents a singe exercise sheet. Inside of this `exercise` environment can multiple `solution` environments be declared. These are numbered within the parent exercise environment.

If you don't want to number the exercises according to the section, just use this macro:

```tex
\counterwithout{exercisecounter}{section}
```

There are also minute possibilities to customise these environments. Each `exercise` environment has the following keys:

- `title` the title of the exercise (default "Exercise")
- `subtitle` the subtitle of the exercise (default empty)
- `points` the points of the exercise
- `points/show` a boolean flag to indicate whether to show the points (default false)
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

| command | has starred version | description |
| --- | --- | --- |
| `\ceil{}` | yes | |
| `\floor{}` | yes | |
| `\abs{}` | yes | |
| `\norm{}` | yes | |
| `\mset{}` | yes | creates a simple set |
| `\msetmid{}{}` | yes | creates a simple set with a mid symbol |
| `\mtupel{}` | yes | creates a simple tupel |
| `\appliesto` | no | creates a comma with spacing |
| `\definedas` | no | creates a colon with an equal sign |
| `\ltrue` | no | alias for verum |
| `\lfalse` | no | alias for falsum |

| environment | description |
| --- | --- |
| `conditions` | is an environment to list mathematical conditions or explanations |

For more details regarding Latex in general take a look at this [cheatsheet](https://de.overleaf.com/latex/templates/a-quick-guide-to-latex/fghqpfgnxggz).

### Language

The package [`babel`](https://ctan.org/pkg/babel) is used for language support. With the standard being Englisch. Additionally the package [`csquotes`](https://ctan.org/pkg/csquotes) is imported, for correct quotes based on the primary language selected via `babel`.

You can change the language associated with the document by changing this line right after the begin of the document:

```tex
\selectlanguage{english}
```

The possible arguments for this are `english` and `naustrian`.

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

### Header

The author, matrikelnumber and date can be ommited by setting them blank before the `\maketitle` command:

```tex
\author{}
\matrikelnr{}
\date{}

...

\maketitle
```

## Changelog

### 0.5.1

- adjust spacing in `\msetmid`
- `\msetmid*` scales mid

### 0.5.0

- refactor commands:
  - `abs`
  - `norm`
  - `mset`
  - `msetmid`
  - `mtupel`
  - These commands now provide a consistent syntax for the starred versions. The starred versions scale vertically.
  - `mtupel` is now nestable
  - `definedas` now looks better
- add commands:
  - `ceil`
  - `floor`
- rename commands:
  - `mappliesto` to `appliesto`
  - `mdefinedas` to `definedas`
- remove commands:
  - `\msetmidsa`
- add latex indent config file to provide proper formatting of the `conditions` environment. To use this local config, make sure to use the `-l` switch. Read more [here](https://latexindentpl.readthedocs.io/en/latest/sec-indent-config-and-settings.html#localsettings-yaml-and-friends).
- add `siunix` package

### 0.4.0

- fix `conditions` being to wide
- add optional argument to `conditions` as the seperator, usable with `\sep`
- add packages `nicematrix`, `xltabular` and `multirow`
- new math commands `mappliesto` and `mdefinedas`
- remove array stretch
- new itemize environment for tables `tabitemize`

### 0.3.0

- add `\msetmidsa` command, a standalone mid symbol for the `\mset{}` and `\mset*{}` commands
- fix spacing error when no author is given

### 0.2.0

- add `\msetmid` command
- fix wrong primary language set
- add option to specify language for the document
- make `\mset` robust

### 0.1.2

- add `\mset*`
- removed `\msetempty` and `\mtupelempty`
- `\mtupel` now scales the angled brackets according to its elements

### 0.1.1

- add listings file path
- listings now show linebreaks resulted from long lines

### 0.1.0 first version
