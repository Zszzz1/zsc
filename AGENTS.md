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
- 所有 JS 变量名、CSS 类名、id 名必须以 `zsc_` 前缀开始（如 `zsc_card`、`zsc_nav_list`、`zsc_timer`）。
- 每个 HTML 页面必须包含注释：`<!-- 姓名：张顺昌；建立时间：YYYY-MM-DD；使用模型：<模型名>；功能名称：<页面主题> -->`，新页面写在 `<head>` 内（模型名填写创建该页面时所用的大模型，如 GLM-5.3-Flash）；修改旧页面时同步保持该注释格式一致。
- 新页面一律使用原生 HTML、CSS、JavaScript 实现，不引入第三方库和 CDN（已有 `cdn/` 目录仅供 13-1/13-2 旧页面使用）。
- 图标统一使用 `font/` 目录下的 iconfont 图标（引入 `font/iconfont.css`，用法参考 13-3.html）。
- 需要获取服务器端数据时使用 `fetch` API；fetch 需在 HTTP 服务下运行（如 `python -m http.server`），直接双击打开 file:// 会跨域失败。

## Verifying changes
- No test/lint commands exist. Verify by opening the modified HTML file directly in a browser (or serving the folder, e.g. `python -m http.server`) and checking it renders.
