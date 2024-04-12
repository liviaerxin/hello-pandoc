# Basic Pandoc LaTeX Template for Markdown Letters

## Installation

Dependencies:
- Pandoc
- LaTex: BasicTex
- Additional LaTex packages (installed by `tlmgr`):
    - `graphicx`
    - `geometry`
    - `lmodern`
    - `fancyhdr`


## Get Started

To generate PDF letters using Markdown, I'll need to apply a custom LaTeX template. In this case, my template, `basic-template.tex`, is derived from `basic.tex`.

Generate PDF letter from markdown file, `letter.md` -> `letter.pdf`,

```sh
pandoc invoice-letter.md --template=study-plan-template.tex -o invoice-letter.pdf
```

Or, Use two-phase generation, `letter.md` -> `letter.tex` -> `letter.pdf`,

```sh
pandoc letter.md --template=lined-template.tex -o letter.tex
pdflatex letter.tex
```

View the base LaTeX,

```sh
pdflatex basic.tex
```

Specify the `signature` variable from command line, which will take precedence over metadata.

```sh
pandoc letter.md --template=lined-template.tex -v signature=./letters/formal-letter/signature.pdf -o letter.pdf 
```

## Metadata

The template contains variables that can be set in a **YAML metadata** block in markdown file.

```markdown
---
subject: Financial Support Letter
signature: Frank
fromaddress:
    - Frank
    - 123 Street Rd
    - Chicago, IL
toaddress:
    - My Home
    - 456 Road St.
    - New York, NY
opening: To whom it may concern,
closing: Sincerely,
date: 12 December 2020
---
```

Available metadata:

- `subject`: Describes the main topic or purpose of the letter.
- `signature`: Typically the sender's name or signature.
- `fromaddress`: Sender's contact information, including name and address. It can accept a list for a multi-line address.
- `toaddress`: Recipient's contact information, including name and address. It can accept a list for a multi-line address.
- `opening`: The initial greeting or salutation of the letter.
- `closing`: The closing remarks or sign-off at the end of the letter.
- `date`: The date on which the letter is written or sent.

## Resources

[LaTeX/Letters - Wikibooks, open books for an open world](https://en.wikibooks.org/wiki/LaTeX/Letters)

[Pandoc template for writing Markdown letters (DIN 5008)](https://github.com/benedictdudel/pandoc-letter-din5008)