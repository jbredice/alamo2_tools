# AGENTS.md — House rules for EDA HTML tools (no build step)

## Project goal
Build small, static, self-contained browser tools for data exploration, hosted on GitHub Pages.

## Non-negotiables
- Each tool is a single `*.html` file (HTML/CSS/JS inside).
- No build step, no server required.
- External deps are OK via ESM CDNs, but pin versions.
- Must work on GitHub Pages and when opened locally.

## Default stack
- DuckDB-WASM for analytics
- Observable Plot for charts
- Observable Inputs (or light custom UI) for controls

## UX requirements (minimum)
- Import: drag/drop + file picker; show schema + row count
- Profiling: null %, distinct, top values, min/max
- Explore: filters + aggregation (or SQL editor if tool is SQL-first)
- Output: table + chart, both interactive
- Persist UI state in localStorage + Reset button

## Engineering
- Avoid UI freezes; sample or paginate large tables
- No external services, no secrets, no analytics
- Add a small in-page self-test/demo dataset
- Update `index.html` with a link to each new tool
