# Assignment TeXplate

![Assignment TeXplate 1](../assets/assignment-texplate-1.png)
## Usage

**NOTE: Make sure you've followed the installation instructions in the repo's main README.md ([here](../README.md)).**

A `preamble.tex` file is provided (which builds ontop of `limao-preamble`) where you can change the details that appear on the title page.

You can start fresh with `empty.tex` (which imports the `preamble.tex` file). If you'd prefer not to have a title page, comment out these lines in `empty.tex`:

```tex
\begin{titlingpage}
    \maketitle
\end{titlingpage}
```

See the `example.tex` file for an example usage of the template.

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

