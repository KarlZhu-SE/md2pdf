# md2pdf

High-fidelity Markdown to PDF skill for OpenClaw.

## What this repo contains

- `SKILL.md` — skill metadata + workflow guidance
- `scripts/install_deps_ubuntu.sh` — dependency install helper (Ubuntu/Debian)
- `scripts/md2pdf.sh` — markdown-to-pdf converter entrypoint
- `assets/defaults/hifi.yaml` — reusable Pandoc defaults preset
- `references/style-guide.md` — style and tuning guidance

## Quick start

```bash
# 1) Install dependencies
bash scripts/install_deps_ubuntu.sh

# 2) Convert markdown to pdf
bash scripts/md2pdf.sh input.md output.pdf

# 3) Optional: use defaults preset
bash scripts/md2pdf.sh input.md output.pdf --defaults assets/defaults/hifi.yaml
```

## Requirements

- `pandoc`
- `xelatex` (via `texlive-xetex`)
- CJK fonts (e.g. `fonts-noto-cjk`)

## License

MIT
