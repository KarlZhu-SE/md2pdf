---
name: md2pdf
description: High-fidelity Markdown to PDF conversion using Pandoc + XeLaTeX with strong Chinese/CJK support, clean typography, table/code rendering, and reusable defaults. Use when users ask for formal/professional PDF output from .md (reports, docs, proposals, manuals), want better visual quality than basic markdown renderers, or need a repeatable md→pdf workflow/skill.
---

# md2pdf

Produce polished, print-ready PDF from Markdown with a stable, reusable pipeline.

## Quick start

1. Install dependencies (Ubuntu/Debian):
   - `bash scripts/install_deps_ubuntu.sh`
2. Convert Markdown:
   - `bash scripts/md2pdf.sh input.md output.pdf`
3. Optional: enable cover page / metadata style via defaults:
   - `bash scripts/md2pdf.sh input.md output.pdf --defaults assets/defaults/hifi.yaml`

## Workflow

### 1) Prepare source markdown

- Prefer `#`/`##` heading hierarchy (for TOC quality).
- Keep code blocks fenced with language tags (for syntax highlight).
- Keep tables in GFM format.

### 2) Run high-fidelity conversion

Use `scripts/md2pdf.sh` as the default entrypoint.

It applies a professional baseline:

- `--pdf-engine=xelatex`
- Chinese font fallback (`Noto Sans CJK SC`)
- Table of contents (`--toc`)
- Section numbering (`--number-sections`)
- Reasonable margins / line spread / link coloring
- Code highlight style

### 3) Tune output quality

Use either:

- CLI flags in `scripts/md2pdf.sh` (quick tuning), or
- defaults file (`assets/defaults/hifi.yaml`) for stable team-wide style.

Recommended adjustments:

- business report: keep `11pt`, margin `2.2cm`, TOC on
- printable manual: increase margin to `2.5cm`
- dense technical doc: keep section numbers and monospace code font

## Troubleshooting

- `pandoc: command not found`: run `scripts/install_deps_ubuntu.sh`.
- `xelatex not found`: ensure `texlive-xetex` installed.
- CJK glyph squares/tofu: install `fonts-noto-cjk` and keep `CJKmainfont` as Noto Sans CJK.
- Weird table wrapping: reduce table width in markdown or use landscape layout for large tables.

## References

- Style baseline and knobs: `references/style-guide.md`
- Reusable defaults preset: `assets/defaults/hifi.yaml`
