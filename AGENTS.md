# Repository Guidelines

## Project Structure & Module Organization
All source files live at the repository root. `index.html` houses the page markup and links to the shared stylesheet. `style.css` defines the light/dark themes, layout rules, and component classes such as `site-header`, `hero`, and `project-grid`. Static assets (`logo*.png`, `logo.svg`, `avatar.jpeg`, favicons) stay alongside the HTML so GitHub Pages serves them without additional routing. Keep any new media web-optimized and name it descriptively (`logo-256.png`, `profile-teaching.jpg`) to stay consistent.

## Build, Test, and Development Commands
This site is static, so no build step is required. For local previews, start a lightweight server from the project root:
```bash
python3 -m http.server 4000
```
Then open `http://localhost:4000` to validate changes. If you prefer Node tooling, `npx serve@latest .` provides equivalent behavior. After edits, a quick reload (and `Cmd+Shift+R` for cache busting) ensures stylesheets update correctly.

## Coding Style & Naming Conventions
Follow the existing two-space indentation in `index.html` and collapse attributes onto new lines only when readability demands it. CSS selectors are lower-case, hyphen-separated (`.site-header`, `.accent-pill`), with utility tokens defined at the top via CSS variables—extend those tokens instead of hard-coding new colors. Prefer semantic HTML elements (`<main>`, `<section>`, `<article>`) and keep aria labels meaningful. Run `npx prettier@latest --check index.html style.css` before committing to catch stray whitespace or formatting drifts.

## Testing Guidelines
There is no automated test suite; rely on manual verification. After spinning up the local server, check the layout in both light and dark appearance (use your browser’s “prefers-color-scheme” overrides) and confirm the responsive breakpoints by resizing the viewport from 320px upward. Validate external links and Font Awesome icons, and, when possible, review the page in at least one Chromium-based browser and Safari/Firefox to spot rendering quirks.

## Commit & Pull Request Guidelines
Existing history favors concise, present-tense summaries (`Update style`, `Add hero copy`). Continue using one-line imperatives under ~60 characters, and group related changes into single commits to simplify review. For pull requests, include a short motivation, a bullet list of key changes, any manual test steps performed, and screenshots or screen recordings for visible updates. Link issues when applicable, and confirm that the site was checked locally with the commands above before requesting review.

## Deployment & Hosting Notes
The repository is published via GitHub Pages. Merges to the default branch redeploy the site automatically; no extra workflow triggers are needed. After a PR merges, allow a few minutes for the CDN to update, then spot-check `https://tehanhunter.github.io/` to ensure assets load and theme switching still works.
