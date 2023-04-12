# Assignment TeXplate

## Installation

The easy way: You can just copy over the `assignment-texplate.sty` file to your assignment folder, and do this for every assignment where you'll be using the package.

The more advanced way: Put the `assignment-texplate.sty` in your TeX home directory in its own directory (e.g. `assignment-texplate/`). This way, you'll be able to `\usepackage{assignment-texplate}` from any directory without needing to have the `assignment-texplate.sty` file there (you'll still need to copy across the `assignment-preamble.tex` if you intend on using that). Your TeX home directory can be found using the following command:
```
kpsewhich -var-value=TEXMFHOME
```
For Linux users, this will usually be `~/texmf/`, so you'd put the `.sty` file under `~/texmf/tex/latex/assignment-texplate/`. For more information, see https://en.wikibooks.org/wiki/LaTeX/Installing_Extra_Packages.

## Usage

There is a template preamble file `assignment-preamble.tex` that you can use to start from. This is where you can change the details that appear on the title page. You can start fresh with `empty.tex` (which imports the `assignment-preamble.tex` file).

See the `assignment/example.tex` file for an example usage of the template.

### Questions
`\question` inserts a new question (starting from 1). To start at or skip to a different number, use

```tex
\questiongoto{<number>}
```

to set the next `\question` to start from `<number>`.

### Subquestions

For questions with multiple parts, you can use the `squestions`, `ssquestions`, and `sssquestions` environments. Each environment has their own set of item types;

- `\squestionalph`, `\ssquestionalph`, `\sssquestionalph` for alphabetical enumerating
- `\squestionnum`, `\ssquestionnum`, `\sssquestionnum` for numerical enumerating
- `\squestionroman`, `\ssquestionroman`, `\sssquestionroman` for roman numeral enumerating

Example usage:

```tex
\question
\begin{squestions}
    \squestionroman
    This creates subquestion part (i).
    \begin{ssquestions}
        \ssquestionalph
        This creates subsubquestion part (a).

        \ssquestionalph
        This creates subsubquestion part (b).
    \end{ssquestions}

    \squestionroman
    This creates subquestion part (ii).

    \squestionroman
    This creates subquestion part (iii).
    \begin{ssquestions}
        \ssquestionnum
        This creates subsubquestion part (1).

        \ssquestionnum
        This creates subsubquestion part (2).
        \begin{sssquestions}
            \sssquestionroman
            This creates subsubsubquestion part (i).

            \sssquestiongoto{5}
            \sssquestionroman
            Look! I'm at subsubsubquestion part (v) now.

            \sssquestionroman
            This creates subsubsubquestion part (vi).
        \end{sssquestions}

        \ssquestionnum
        This creates subsubquestion part (3).
    \end{ssquestions}

    \squestionroman
    This creates subquestion part (iv).
\end{squestions}

\questiongoto{7}
\question
Look! I'm at question 7 now.
```

![Assignment TeXplate 2](../assets/assignment-texplate-2.png)