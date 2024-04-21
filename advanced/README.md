# Pandoc Latex Template for Writing Letters in Markdown

The workflow for writing a letter in markdown is:

1. **Pandoc** parse markdown files.
    - set a series of variables
2. **Pandoc** apply a Latex template.
    - **Pandoc** will substitute the variables in the LaTeX template.
    - To find variables values, **Pandoc** will look for the key in metadata which can be YAML metadata blocks.
    - Outputted **LaTex** documents are fully capable of generating PDFs.
3. Then, **Pandoc** creates PDFs from the LaTex documents using **LaTeX** by default.
    - `--pdf-engine` is optional used to specify which TeX engine to use to generate PDFs.
        - `pdflatex`: LaTex
        - `xelatex`: XeLaTex

## Installation

## Generate letter from markdown

```sh
pandoc letter.md --template=letter_template.tex -o letter.tex
```

standalone: convert markdown to latex with applying the default template,

```sh
pandoc letter.md -s -o letter.tex
```

convert markdown to latex without applying the default template,

```sh
pandoc letter.md -o letter.tex
```

## Other useful Pandoc functions

Get the default LaTeX template for Markdown file,

```sh
pandoc -D latex
```
