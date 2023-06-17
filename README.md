![Assignment TeXplate 1](assets/assignment-texplate-1.png)

---

<h3 align="center">Limao's TeXplates</h3>

This repo is a collection of my custom LaTeX templates.

- [assignment-texplate](/assignment-texplate/): A template for assignments and homework sets.
- [cheatsheet-texplate](/cheatsheet-texplate/): A template for cheatsheets.
- [limao-preamble](/preamble-texplate/): A general preamble with commonly-used packages imported and some helpful macros defined.

Aside: If you're interested in using TeX snippets, mine can be found [here](https://github.com/LimaoC/dotfiles/blob/main/.config/nvim/UltiSnips/tex.snippets).

## Installation

Follow the steps below to install the templates in this repository.

1. Clone the repository to some local directory:
    ```
    git clone git@github.com:LimaoC/TeXplate
    ```
2. Create symlinks for each template you'd like in your TeX home directory. Your TeX home directory can be found using the following command:
    ```
    kpsewhich -var-value=TEXMFHOME
    ```
    For linux users, this will usually be `~/texmf/`. If the path to the cloned repository is `path/TeXplate`, you'd create your symlinks like so:
    ```
    cd ~/texmf/tex/latex
    ln -s path/TeXplate/assignment-texplate assignment-texplate
    ln -s path/TeXplate/limao-preamble limao-preamble
    ```
    For more information about installing LaTeX packages this way, see https://en.wikibooks.org/wiki/LaTeX/Installing_Extra_Packages.

    **NOTE: All packages rely on `limao-preamble` being installed.**
    
Storing the templates in your TeX home directory lets you conveniently import them from anywhere on your machine with
```tex
\usepackage{assignment-texplate}  % for the package templates
\input{limao-preamble}            % for the general preamble file
```

Symlinking makes it easy to grab any updates that I make to the templates - just use `git pull` and the templates will stay up-to-date.

## Usage

See the `README.md`'s in each respective template's directory.

## License
(MIT License) See [LICENSE](https://github.com/LimaoC/assignment-texplate/blob/main/LICENSE).

