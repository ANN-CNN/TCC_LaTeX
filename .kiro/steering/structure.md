# Project Structure

## Root Files

| File | Purpose |
|---|---|
| `Principal.tex` | Entry point — document metadata, includes all sections, controls which parts are active via `\input{}` |
| `configuracao.tex` | Document class setup, all `\usepackage{}` declarations, custom commands, and formatting config |
| `pendencias.tex` | Additional packages loaded via `\input{pendencias}` inside `configuracao.tex` |
| `Referencias.bib` | BibTeX bibliography database |
| `abntex2.cls` | Local copy of the abntex2 document class |
| `Principal.pdf` | Compiled output (do not edit manually) |

## Folders

### `pre/` — Pre-textual elements
ABNT front matter, included in order from `Principal.tex`:

| File | Content |
|---|---|
| `sigas.tex` | Acronym/symbol definitions (loaded before `\begin{document}`) |
| `01-capa.tex` | Cover page |
| `02-rosto.tex` | Title page |
| `03-assinaturas.tex` | Signature sheet |
| `04-agradecimentos.tex` | Acknowledgements |
| `05-resumo.tex` | Abstract (Portuguese) |
| `06-abstract.tex` | Abstract (English) |
| `07-figuras.tex` | List of figures |
| `08-quadros.tex` | List of boxes/quadros |
| `09-tabelas.tex` | List of tables |
| `10-codigos.tex` | List of code listings |
| `11-siglas.tex` | List of acronyms |
| `11-simbolos.tex` | List of symbols |
| `12-sumario.tex` | Table of contents |

### `textual/` — Main body chapters

| File | Chapter |
|---|---|
| `t1-introducao.tex` | Introduction (objectives, justification) |
| `t2-fundamentacao.tex` | Theoretical background |
| `t3-trabalhos.tex` | Related works |
| `t4-material.tex` | Materials and methods |
| `t5-cronograma.tex` | Schedule (Gantt chart) |
| `t5-desenvolvimento.tex` | Development (currently commented out) |
| `t6-resultados.tex` | Results |
| `t7-conclusoes.tex` | Conclusions |
| `t8-referencias.tex` | References section wrapper |

### `pos/` — Post-textual elements

| File | Content |
|---|---|
| `pos-apendice.tex` | Appendices (currently commented out) |
| `pos-anexos.tex` | Annexes (currently commented out) |

### `media/` — Images and figures
All images referenced via `\includegraphics{}`. Current assets include architecture diagrams, flowcharts, and the Gantt chart.

## Conventions

- **Enabling/disabling sections:** Comment/uncomment `\input{...}` lines in `Principal.tex`. Do not delete them.
- **Labels:** Use descriptive prefixes — `cap:` for chapters, `sec:` for sections, `fig:` for figures, `tab:` for tables, `eq:` for equations.
- **Citations:** Use `\cite{}` for parenthetical, `\citeonline{}` for inline (author as subject), `\citeauthorandyear{}` for "Author (year)" form.
- **Custom commands:** Defined in `configuracao.tex` — e.g., `\sigla{}{}`, `\simbolo{}{}{}`, `\citeauthorandyear{}`.
- **Language:** All academic prose in Brazilian Portuguese. Chapter/section titles are auto-uppercased by the class.
- **New packages:** Add to `pendencias.tex`, not directly to `configuracao.tex`.
