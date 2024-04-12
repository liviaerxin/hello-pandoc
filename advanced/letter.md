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
# LaTex
documentclass: letter
papersize: a4
fontsize: 12pt
header-includes:
  - \begin{center}\Large\textbf{Header}\end{center}
include-before:
  - \address{$for(fromaddress)$$fromaddress$$sep$\\$endfor$}
  - \begin{letter}{$for(toaddress)$$toaddress$$sep$\\$endfor$$if(subject)$\\ ~ \\\textbf{Subject: $subject$}$endif$}
  - \opening{$opening$}
include-after:
  - \longindentation=0pt
  - \closing{$closing$}
  - \signature{$signature$}
  - \end{letter}
---

I am writing to you on behalf of the Wikipedia project (http://www.wikipedia.org/),
an endeavour to build a fully-fledged multilingual encyclopaedia in an entirely
open manner, to ask for permission to use your copyrighted material.