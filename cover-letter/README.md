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
pandoc letter.md --template=basic-template.tex -o letter.pdf
```

Or, Use two-phase generation, `letter.md` -> `letter.tex` -> `letter.pdf`,

```sh
pandoc letter.md --template=basic-template.tex -o letter.tex
pdflatex letter.tex
```

View the base LaTeX,

```sh
pdflatex basic.tex
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

[pandoc-letter/template-letter.tex at master · aaronwolen/pandoc-letter · GitHub](https://github.com/aaronwolen/pandoc-letter/blob/master/template-letter.tex)

[Helpful_Lab_Materials/WritingCoverLetter/cltemplate.tex at master · Microbiology/Helpful_Lab_Materials · GitHub](https://github.com/Microbiology/Helpful_Lab_Materials/blob/master/WritingCoverLetter/cltemplate.tex)