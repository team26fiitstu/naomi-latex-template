
# NAOMI LaTeX Template

A reusable LaTeX template for NAOMI team documentation.

## Getting Started

Click the button below to create a new Overleaf project using this template.

[![Open in Overleaf](https://img.shields.io/badge/Open_in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/team26fiitstu/naomi-latex-template/archive/refs/heads/main.zip)

## Features

- Custom title page
- Team leaders and members
- University logos
- Headers and footers
- Figure and table placeholders
- IEEE bibliography
- Optional title page, table of contents and references
- Reusable NAOMI table style with a dark header, alternating row colors, and readable text alignment

## Tables

Use `\tableplaceholder{Caption}{label}` for the ready-made three-column example. For custom content, use the `naomitable` environment and the `L{width}` and `Y` column types:

```latex
\begin{naomitable}{Verification levels}{tab:verification}
    \begin{tabularx}{\textwidth}{L{2.8cm} L{3.5cm} Y}
        \rowcolor{naomiTableHeader}
        \textcolor{white}{\bfseries Level} &
        \textcolor{white}{\bfseries When} &
        \textcolor{white}{\bfseries Evidence} \\
        Static checks & Every PR & Lint and configuration validation \\
        Unit tests & Behaviour changes & Automated test results \\
        \arrayrulecolor{naomiTableRule}\bottomrule[1pt]
    \end{tabularx}
\end{naomitable}
```

`L{width}` is a fixed-width, left-aligned column. `Y` uses the remaining width and aligns text to the left. The environment applies the caption, row spacing, and alternating colors.

## Configuration

Edit the configuration section in `main.tex`:

```latex
\showtitlepagetrue
\showtoctrue
\showbibliographytrue
```

Change `true` to `false` to disable a section.
