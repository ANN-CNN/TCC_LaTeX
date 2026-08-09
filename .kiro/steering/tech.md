# Tech Stack

## Document Class

- **`abntex2`** — custom class built on top of `memoir`, enforces ABNT academic formatting
- Configured in `configuracao.tex` with options: `12pt`, `oneside`, `a4paper`, `chapter=TITLE`, `section=TITLE`, `brazil`

## Key Packages

| Package | Purpose |
|---|---|
| `helvet` / `sfdefault` | Arial-equivalent font (Helvetica) |
| `fontenc` (T1) + `inputenc` (utf8) | Font encoding and UTF-8 input |
| `abntex2cite` (alf) | ABNT author-date citations |
| `glossaries` (acronyms, symbols) | Acronym and symbol lists |
| `listings` | Source code blocks |
| `graphicx`, `subfig` | Images and sub-figures |
| `amsmath`, `amssymb` | Math environments |
| `tikz` | Diagrams and flowcharts |
| `hyperref` | Colored PDF links (blue) |
| `backref` | Back-references in bibliography |
| `siunitx` | SI units |
| `booktabs`, `multirow`, `longtable` | Tables |
| `pdfpages` | Embedding external PDFs |

## Build System

**Recommended:** `latexmk` via the VS Code **LaTeX Workshop** extension (auto-compiles on save).

**Manual full build (with bibliography):**
```bash
pdflatex Principal.tex && bibtex Principal && pdflatex Principal.tex && pdflatex Principal.tex
```

The 4-step sequence is required because:
1. First `pdflatex` — generates `.aux` and identifies citations
2. `bibtex` — processes `Referencias.bib`
3. Second `pdflatex` — incorporates bibliography
4. Third `pdflatex` — resolves cross-references and page numbering

## Clean Auxiliary Files

```bash
rm -f Principal.{aux,bbl,blg,brf,idx,lof,log,toc}
```

## Output

`Principal.pdf` is generated at the project root alongside `Principal.tex`.

## Dependencies (Linux)

```bash
sudo apt install latexmk texlive-full
```

## VS Code Extensions

- **LaTeX Workshop** (`James-Yu.latex-workshop`) — primary build/preview tool
- **LaTeX Utilities** (`tecosaur.latex-utilities`) — snippets and utilities

## Troubleshooting

If compilation fails with stale cache errors on `configuracao.tex`, use **Ctrl+Shift+P → Developer: Reload Window** in VS Code to clear the LaTeX Workshop cache.
