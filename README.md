# Pandoc Latex Template for Writing Letters in Markdown

The workflow for writing a letter in markdown is:

1. **Pandoc** converts markdown files to **LaTex** documents using a Latex template.
    - **Pandoc** will substitute the variables in the LaTeX template.
    - To find variables values, **Pandoc** will look for the key in metadata which can be YAML metadata blocks.
    - Outputted **LaTex** documents are fully capable of generating PDFs.
2. Then, **Pandoc** creates PDFs from the LaTex documents using **LaTeX** by default.
    - `--pdf-engine` is optional used to specify which TeX engine to use to generate PDFs.
        - `pdflatex`: LaTex
        - `xelatex`: XeLaTex

## Installation

### macOS

Install **Pandoc**,

```sh
brew install pandoc
```

Install **BasicTex**, then using the `tlmgr` tool to install additional packages as needed, as a full **MacTex** will eat up 4GB of disk.

**BasicTex** already includes:
    - `tlmgr`: tex live manager
    - `xelatex`

```sh
brew install basictex
# required
sudo tlmgr update --self
```

Install additional packages via `tlmgr` as needed, such as `fonts`, `graphix`, `geometry`.

```sh
sudo tlmgr install collection-fontsrecommended graphicx geometry fancyhdr
```


## Generate letter from markdown

```sh
pandoc letter.md --template=letter_template.tex -o letter.tex
```