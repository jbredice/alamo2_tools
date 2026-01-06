# AGENTS.md — House rules for EDA HTML tools (no build step)

## Project goal
Build small, static, self-contained browser tools for data exploration, hosted on GitHub Pages.

## Non-negotiables
- Each tool is a single `*.html` file (HTML/CSS/JS inside).
- No build step, no server required.
- External deps are OK via ESM CDNs, but pin versions.
- Must work on GitHub Pages and when opened locally.

## Default stack
- D3.js for charts and lightweight data utilities
- Lodash for data wrangling and convenience helpers
- Light custom UI controls (vanilla JS/HTML/CSS)

## UX requirements (minimum)
- Import: drag/drop + file picker; show schema + row count
- Profiling: null %, distinct, top values, min/max
- Explore: filters + aggregation (simple in-browser ops; avoid SQL-first UX)
- Output: table + chart, both interactive
- Persist UI state in localStorage + Reset button

## Engineering
- Avoid UI freezes; sample or paginate large tables
- No external services, no secrets, no analytics
- Add a small in-page self-test/demo dataset
- Update `index.html` with a link to each new tool
