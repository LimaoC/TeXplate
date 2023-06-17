# Cheatsheet TeXplate

![Cheatsheet TeXplate 1](../assets/cheatsheet-texplate-1.png)

## Usage

There is a template preamble file `preamble.tex` that you can use to start from. It contains all the page formatting options and included packages etc. Feel free to change these. You can start fresh with `empty.tex` (which imports the `preamble.tex` file).

See the `example.tex` file for an example usage of the template. If you'd prefer not to have a title page, comment out these lines in your `.tex` file:

```tex
\begin{titlingpage}
    \maketitle
\end{titlingpage}
```

