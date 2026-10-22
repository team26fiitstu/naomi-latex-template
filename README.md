
# NAOMI LaTeX Template

A reusable LaTeX template for documentation created by the **NAOMI team** at the Faculty of Informatics and Information Technologies, Slovak University of Technology in Bratislava.

The template provides a consistent structure and visual style for technical documentation, project methodologies, reports, and other team documents.

## Getting Started

Click the button below to create a new Overleaf project using this template.

[![Open in Overleaf](https://img.shields.io/badge/Open_in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/team26fiitstu/naomi-latex-template/archive/refs/heads/main.zip)

### Creating a Document

1. Click **Open in Overleaf**.
2. Sign in to Overleaf if necessary.
3. Create a new project using the template.
4. Open `main.tex`.
5. Update the document information in the configuration section.
6. Replace the example content with your own documentation.
7. Click **Recompile** to generate the PDF.

Each document is created as an independent Overleaf project. Changes made to one document do not affect the original template or other documents.

## Features

- Custom university title page
- Team leaders and members
- University logos
- Consistent headers and footers
- Automatic page numbering
- Custom section and subsection formatting
- Figure and table placeholders
- Reusable NAOMI table style
- IEEE-style bibliography
- Lorem ipsum placeholder text
- Optional title page and bibliography
- Support for automatic table of contents

## Project Structure

```text
naomi-latex-template/
├── main.tex
├── references.bib
├── assets/
│   ├── horizontal.png
│   └── vertical.png
└── README.md
```

| File | Description |
|------|-------------|
| `main.tex` | Main document, formatting, and configuration |
| `references.bib` | Bibliography entries |
| `assets/horizontal.png` | Logo displayed in the document header |
| `assets/vertical.png` | Logo displayed on the title page |
| `README.md` | Template documentation |

## Configuration

All basic document settings are located at the beginning of `main.tex`.

### Document Information

Update the following commands:

```latex
\newcommand{\worktitle}{Documentation Template}
\newcommand{\worksubtitle}{NAO Robot Exercise System}
\newcommand{\teamname}{NAOMI}
\newcommand{\subject}{NAO Robot Exercise System}
```

- `\worktitle` — main title displayed on the title page.
- `\worksubtitle` — subtitle displayed on the title page and in the header.
- `\teamname` — team name.
- `\subject` — project or course name displayed in the footer.

University information, academic year, team leaders, and team members can also be modified in this section.

### Optional Sections

The template supports enabling or disabling the title page and bibliography.

```latex
% Enable
\showtitlepagetrue
\showbibliographytrue

% Disable
\showtitlepagefalse
\showbibliographyfalse
```

To disable the table of contents in the current template, comment out the following lines:

```latex
% \tableofcontents
% \newpage
```

### Compiling

The template is designed to work with **pdfLaTeX** in Overleaf.

Bibliography processing uses **Biber**.

## Writing Content

The document body begins after:

```latex
\begin{document}
```

Use standard LaTeX section commands to organise the document:

```latex
\section{Introduction}

This section introduces the document.

\subsection{Project Objectives}

Description of the project objectives.

\subsubsection{Functional Requirements}

Detailed information about functional requirements.
```

Sections are numbered automatically.

### Placeholder Text

The template includes the `lipsum` package for generating sample text.

```latex
\lipsum[1]
```

Generate multiple paragraphs:

```latex
\lipsum[1-3]
```

Replace placeholder text with actual documentation before publishing.

## Images

Images should be stored in the `assets/` directory.


### Inserting a Image

Upload the image to `assets/` and use:

```latex
\documentimage
    {assets/architecture.png}
    {System Architecture}
    {fig:architecture}
```

Arguments:

1. Image path
2. Figure caption
3. Reference label

Reference the image elsewhere in the document:

```latex
As shown in Figure~\ref{fig:architecture},
the system consists of several components.
```

Figure numbering is handled automatically.

## Tables

The template includes a custom NAOMI table style with:

- Dark blue header background
- White header text
- Alternating light-blue and white rows
- Consistent spacing
- Automatic captions and numbering
- Left-aligned text columns
- Automatic adjustment of column widths

This generates a sample table containing Name, Description, and Status columns.

### Custom Tables

For custom tables, use the `naomitable` environment.

```latex
\begin{naomitable}{Verification Levels}{tab:verification}
    \begin{tabularx}{\textwidth}{L{2.8cm} L{3.5cm} Y}

        \rowcolor{naomiTableHeader}

        \textcolor{white}{\bfseries Level} &
        \textcolor{white}{\bfseries When} &
        \textcolor{white}{\bfseries Evidence} \\

        Static checks &
        Every pull request &
        Lint and configuration validation \\

        Unit tests &
        Behaviour changes &
        Automated test results \\

        Integration tests &
        Component integration &
        Integration test results \\

        \arrayrulecolor{naomiTableRule}
        \bottomrule[1pt]

    \end{tabularx}
\end{naomitable}
```

### Column Types

| Column | Description |
|--------|-------------|
| `L{width}` | Fixed-width, left-aligned column |
| `Y` | Automatically fills remaining width and aligns text to the left |
| `l` | Standard left-aligned LaTeX column |
| `c` | Standard centered LaTeX column |
| `r` | Standard right-aligned LaTeX column |

The `naomitable` environment automatically applies row spacing, alternating colors, and table captions.

### Referencing Tables

Every table should have a unique label.

```latex
\label{tab:verification}
```

Reference the table using:

```latex
Table~\ref{tab:verification}
```

## References and Bibliography

Bibliography entries are stored in `references.bib`.

The template uses `biblatex` with the IEEE citation style.

### Adding a Reference

Example entry in `references.bib`:

```bibtex
@online{jira_docs,
    author  = {{Atlassian}},
    title   = {Jira Documentation},
    url     = {https://support.atlassian.com/jira/},
    urldate = {2026-10-22}
}
```

### Citing a Source

Use the citation key inside your document:

```latex
Jira is used for project management~\cite{jira_docs}.
```

LaTeX automatically generates the citation number and adds the source to the bibliography.

The bibliography is displayed at the end of the document when enabled.

## Headers and Footers

All standard document pages use a consistent layout.

### Header

- Logo on the left
- Document subtitle on the right
- Academic year below the subtitle

### Footer

- Team and project name on the left
- Current page and total number of pages on the right

The title page does not display headers or footers.

## Recommended Usage

This template can be used for:

- Technical documentation
- Development methodologies
- Sprint reports
- Project progress reports
- Architecture documentation
- Research reports
- Testing documentation
- Internal team procedures

Before publishing a document, make sure that:

- The document title is correct.
- All placeholder text has been removed.
- Figures and tables have meaningful captions.
- References are included where necessary.
- The document compiles without errors.
- The generated PDF has been reviewed.

## Maintaining the Template

The original template is maintained in this GitHub repository.

When creating a new document, always use the **Open in Overleaf** button to obtain the current template version.

Existing Overleaf projects are independent copies and do not automatically receive future template updates.

Changes to the shared template should be made through the GitHub repository.

## Team

**NAOMI — Academic Year 2026/2027**

Faculty of Informatics and Information Technologies  
Slovak University of Technology in Bratislava
