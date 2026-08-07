# UL Lafayette Thesis Template

LaTeX thesis and dissertation template for the University of Louisiana at Lafayette. The template descends from earlier UL Lafayette dissertation-format work by Steven White, Malcolm Hutson, and Adam Lewis, with later updates by Nicholas Lipari.

> [!IMPORTANT]
> This repository is a convenience template, not an authoritative statement of current Graduate School requirements. Always compare the generated document with the current University of Louisiana at Lafayette Graduate School formatting requirements before submission.

## Repository layout

- `example.tex` — primary example document and user configuration entry point.
- `example.bib` — example BibTeX database.
- `source/` — thesis content included by `example.tex`.
- `media/` — images and other graphics referenced by the document.
- `template/uldiss.sty` — UL Lafayette thesis/dissertation formatting implementation. Most users should not need to edit this file.
- `template/acmtrans/` — legacy ACM bibliography support retained by the template.
- `example.pdf` — compiled reference output, intentionally tracked.

A later repository-cleanup phase may reorganize the content directories. Until then, the paths in `example.tex` are authoritative.

## Using the template

1. Copy or clone the repository into your working environment.
2. Edit the document type, school, author, degree, graduation, and committee information near the beginning of `example.tex`.
3. Put thesis text in the `.tex` files under `source/`, or add additional source files and reference them from `example.tex`.
4. Put figures and other graphics in `media/`. `example.tex` configures LaTeX to search that directory for graphics.
5. Add bibliography entries to `example.bib`, or change the bibliography command in `example.tex` to use another `.bib` file.
6. Compile `example.tex` using a LaTeX environment that provides the packages required by the template.

The document currently uses BibTeX. A typical manual build sequence is:

```text
pdflatex example.tex
bibtex example
pdflatex example.tex
pdflatex example.tex
```

Additional passes may be required after changes that affect references, the table of contents, lists of figures/tables, or the index.

## Editing guidance

For ordinary thesis work, prefer editing:

- metadata and document-level options in `example.tex`
- content files under `source/`
- bibliography entries in `example.bib`
- graphics under `media/`

Avoid modifying `template/uldiss.sty` unless you are maintaining the template itself. It contains the formatting implementation and has substantial historical compatibility behavior.

## Generated files

Common transient LaTeX build products are ignored by `.gitignore`. The checked-in `example.pdf` is retained as a reference output and is not ignored.

## License and third-party material

The principal template sources contain a Creative Commons Attribution-NonCommercial 3.0 United States notice. See `LICENSE` for repository licensing notes and scope.

Files under `template/acmtrans/` are derived from older ACM/Chicago bibliography-style work and carry their own provenance comments. No explicit license statement was found in their file headers, so this repository does not assert that those third-party files are relicensed under the template's Creative Commons notice.
