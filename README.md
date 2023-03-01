![Template Screenshot](assets/screenshot.png)

---

<h3 align="center">Assignment Texplate</h3>

This is a LaTeX template that you can use for your math assignments and homework. It provides a cleanly formatted document layout, simple commands to add new questions and subquestions, and some useful miscellaneous macros.

## Usage

HTTPS:

```
git clone https://github.com/your-username/assignment-texplate.git assignment-name
cd assignment-name
```

SSH:

```
git clone git@github.com:LimaoC/assignment-texplate.git assignment-name
cd assignment-name
```

There are two options for usage; you can either clone the repository for each assignment/homework piece you do, or just copy the `texplate.sty` file to the directory you want to use it in and add the following command to the preamble:
```tex
\usepackage{style}
```

There may occasionally be updates to the template; to receive these updates, run

```
git pull
```

### Questions
`\question` inserts a new question, which starts at 1. To start at a different number, use

```tex
\setcounter{questionCounter}{<questionNumber> - 1}
```

just before the first `\question` and replace `<questionNumber>` with the question number you want to start at.

### Subquestions

For questions with multiple parts, you can use the `subquestions` environment like so:

```tex
\begin{subquestions}
    \subquestionroman
        This creates subquestion part (i).
    \subquestionroman
        This creates subquestion part (ii).
    \subquestionroman
        This creates subquestion part (iii).
\end{subquestions}
```

You can also use `\subquestionalph` for alphabetical parts, i.e. `(a), (b), (c)`, or `\subquestionnum` for numerical parts, i.e. `(1), (2), (3)`. This can be changed in `texplate.sty`, or if you'd like, you can define your own too.

### Miscellaneous Macros

These are the custom macros defined for common symbols I use.

#### Auto-sized Bracketing
| Code       | Description                 | Example               | Output                       |
|------------|-----------------------------|-----------------------|------------------------------|
| `\br{}`    | Auto-sized round brackets.  | `\br{\frac{a}{b}}`    | $\left(\frac{a}{b}\right)$   |
| `\sqbr{}`  | Auto-sized square brackets. | `\sqbr{\frac{a}{b}}`  | $\left[\frac{a}{b}\right]$   |
| `\curbr{}` | Auto-sized curly brackets.  | `\curbr{\frac{a}{b}}` | $\left\lbrace\frac{a}{b}\right\rbrace$ |
| `\mgnt{}`  | Auto-sized pipes (\|).      | `\mgnt{\frac{a}{b}}`  | $\left\|\frac{a}{b}\right\|$ |


#### Sets of Numbers
| Code   | Description          | Output       |
|--------|----------------------|--------------|
| `\R`   | Set of real numbers. | $\mathbb{R}$ |
| `\N`   | Set of naturals.     | $\mathbb{N}$ |
| `\Q`   | Set of rationals.    | $\mathbb{Q}$ |

#### Statistics
Each of these macros takes an optional argument `[br]` to specify the bracket type used (`br` for round brackets, `sqbr` for square brackets, `nobr` for no brackets). The default is `br`. These also support subscripts and superscripts; e.g. `\E{x}_\theta` yields $\mathbb{E}_\theta(X)$, and `\Var{X}^2` yields $\mathbb{V}\text{ar}^2(X)$.
| Code          | Description                      | Example             | Output                      |
|---------------|----------------------------------|---------------------|-----------------------------|
| `\Prob[br]{}` | Probability measure.             | `\Prob{X \leq x}`   | $\mathbb{P}(X \leq x)$      |
| `\E[br]{}`    | Expectation.                     | `\E[nobr]{X}`       | $\mathbb{E}X$               |
| `\Var[br]{}`  | Variance.                        | `\Var[sqbr]{X\| Y}` | $\mathbb{V}\text{ar}[X\|Y]$ |
| `\Cov[br]{}`  | Covariance.                      | `\Cov{X, X}`        | $\mathbb{C}\text{ov}(X, X)$ |
| `\PGF[br]{}`  | Probability Generating Function. | `\PGF{z}`           | $\mathcal{G}(z)$            |
| `\MGF[br]{}`  | Moment Generating Function.      | `\MGF{m}`           | $\mathcal{M}(m)$            |

#### Symbols
| Code   | Description               | Output        |
|--------|---------------------------|---------------|
| `\eps` | Alternate epsilon symbol. | $\varepsilon$ |

There are also some useful packages that have been included in `texplate.sty` (which you can also add to). For example, the `physics` package provides `\dd` or `\dd{x}` for differentials, `\dv{x}` for ordinary derivatives, `\pdv{x}` for partial derivatives, etc.

## License
(MIT License) See [LICENSE](https://github.com/LimaoC/assignment-texplate/blob/main/LICENSE).
