# md2pdf

High-fidelity Markdown to PDF skill for OpenClaw.

## What this repo contains

- `SKILL.md` — skill metadata + workflow guidance
- `scripts/install_deps_ubuntu.sh` — dependency install helper (Ubuntu/Debian)
- `scripts/md2pdf.sh` — Pandoc/XeLaTeX converter entrypoint
- `scripts/md2pdf-browser.sh` — browser/CDP converter entrypoint for emoji-friendly output
- `scripts/md2pdf_browser.js` — HTML/Twemoji + browser PDF renderer
- `assets/defaults/hifi.yaml` — reusable Pandoc defaults preset
- `references/style-guide.md` — style and tuning guidance

## Quick start

```bash
# 1) Install base dependencies
bash scripts/install_deps_ubuntu.sh

# 2) Formal print-style PDF
bash scripts/md2pdf.sh input.md output.pdf

# 3) Emoji-friendly/browser-rendered PDF
BROWSER_CDP_URL=http://127.0.0.1:9222 bash scripts/md2pdf-browser.sh input.md output.pdf

# 4) Optional: use defaults preset with Pandoc/XeLaTeX
bash scripts/md2pdf.sh input.md output.pdf --defaults assets/defaults/hifi.yaml
```

## Requirements

### Pandoc/XeLaTeX pipeline

- `pandoc`
- `xelatex` (via `texlive-xetex`)
- CJK fonts (e.g. `fonts-noto-cjk`)

### Browser pipeline

- `node`
- `npm`
- reachable CDP browser endpoint (default `http://127.0.0.1:9222` or set `BROWSER_CDP_URL`)

## When to use which pipeline

- Use `scripts/md2pdf.sh` for formal reports/manuals where TeX typography matters most.
- Use `scripts/md2pdf-browser.sh` when emoji must survive PDF export or when browser-like rendering is preferred.

## License

MIT
