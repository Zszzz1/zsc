# AGENTS.md

Static HTML coursework site (张顺昌《高级网页设计》课堂实践). No build tooling, no package manager, no tests or linters — do not invent npm/scripts.

## Structure
- `index.html` — course landing page; links to every lesson page.
- `{chapter}-{lesson} {中文主题}.html` — one file per lesson (e.g. `5-1层叠与继承.html`). Follow this naming when adding lessons; `index.html` links each file by exact name.
- `img/` — all images, referenced via relative paths (`img/xxx.png`). Never use absolute paths or move images without updating references.

## Conventions
- Lesson pages are self-contained: CSS lives in inline `<style>` blocks. Only `5-1层叠与继承.html` links the shared `css.css` (a scratch file with global `p`/`h2` rules — beware it overrides inline-less styles).
- `index.html` and pages use CSS custom properties defined in each page's `:root` (`--accent`, `--text`, etc.) — reuse these variables rather than hardcoding colors.
- Content is Chinese; keep new copy in Simplified Chinese matching existing pages.
- **New HTML files must be added to `index.html`** — every new lesson page gets a work-card entry in the "作品列表" section (and update the stats count).

## Verifying changes
- No test/lint commands exist. Verify by opening the modified HTML file directly in a browser (or serving the folder, e.g. `python -m http.server`) and checking it renders.
