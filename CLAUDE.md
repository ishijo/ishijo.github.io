# CLAUDE.md

## Project overview
- Personal portfolio site for **Ishika Johari**.
- Live URL: https://ishijo.github.io/
- Deployment: GitHub Pages, `master` branch, no build step (static HTML/CSS/JS).
- Template lineage: **HTML5 UP "Twenty"** (html5up.net), CC-BY 3.0 license.

## File structure

| File | Content |
|------|---------|
| `index.html` | Single-page layout: Banner (~112), About (~129), Skills (~182), Portfolio shell (~256), Experience (~346), Resume (~446), Footer (~463) |
| `project.html` | Portfolio → Projects tab (loaded dynamically via jQuery `.load()`) |
| `blog.html` | Portfolio → Blogs tab (2 Medium post cards) |
| `kaggle.html` | Portfolio → Kaggle tab (5 notebook cards) |
| `visualisation.html` | Portfolio → Visualisations tab (3 Tableau dashboards) |
| `assets/css/main.css` | Primary stylesheet (HTML5 UP Twenty base + custom overrides) |
| `assets/sass/` | SCSS source files (not compiled in-repo) |
| `assets/js/main.js` | Template JS (scrolly, dropotron, breakpoints) |
| `images/` | All images — profile photos, project screenshots, skill icons |
| `images/banners/` | Favicons and touch icons |
| `images/skills/` | Skill logo PNGs and SVGs for the carousel |

**Responsive About section:** The About bio paragraph is duplicated 4 times in `index.html` (~lines 139–170) for 4 CSS breakpoint variants. Every content edit must be applied to all 4 copies. Note: `.bigger-device-401px` variant is dead code (always hidden); only 3 of the 4 copies actually render.

## Target audience & positioning
- Aimed at recruiters and hiring managers for **Product Data Scientist, MLE, and AI Engineer** roles at consumer tech companies (Spotify/Netflix/Airbnb tier).
- Positioning wedge: **experimentation + recommendation systems**.

## Content refresh plan — Path A (in progress)

| Pass | Focus | Status |
|------|-------|--------|
| 1 | About | DEFERRED — awaiting copy finalization (not yet applied to site) |
| 2 | Projects | ✅ Done 2026-08-17 — EIA card added, CCRS card refreshed with metrics + tech tags |
| 3 | Skills | ✅ Done 2026-08-17 — carousel overhauled (removed Hadoop/Teradata/HTML/CSS, added 9 new tools) |
| 4 | Experience | Partially done 2026-08-17 — DS2 verb tenses fixed (present→past), intern bullets sharpened. Remaining: DS2 bullet content sharpening, full Experience overhaul deferred to future session. |
| 5 | Structural cleanup | ✅ Done 2026-08-17 — OG tags added, resume link updated, CSS dead code removed, jQuery 1.4 dead code removed, template placeholder cards deleted, duplicate class attribute fixed, HTML5 UP attribution added, favicon refs fixed in sub-pages, unreferenced skill PNGs deleted, text-pill SVG heights normalized. |

## Content gaps to close
- Filed patent (ML-driven insights platform) — currently invisible on site.
- Kaggle Days global keynote on A/B testing — currently invisible.
- MS in Information Management at UW — status wording needs updating (banner and About still read as "pursuing").
- Dell tenure: 2 years, DS1→DS2 promotion — DS2 bullet content still needs sharpening (deferred to Session 2B).
- ~~Experimentation Intelligence Agent project — not on site yet.~~ Added 2026-08-17.
- ~~Cross-Content Recommender — needs real screenshot, live demo link, and metrics.~~ Card refreshed 2026-08-17. Live demo link still blocked (deployment issue).

## Structural issues to fix
- About section paragraph duplicated 4x for responsive breakpoints — `.bigger-device-401px` variant is dead code; could reduce to 3 copies or investigate CSS-only solution for 1 copy.
- ~~Missing Open Graph / Twitter card meta tags.~~ Added 2026-08-17.
- ~~"Request Resume" links to Google Drive folder.~~ Changed to `assets/resume.pdf` download 2026-08-17.
- ~~Skills icons don't reflect current stack.~~ Overhauled 2026-08-17.
- ~~`index.html:38–39` loads jQuery 1.4 + `js/jquery.ba-hashchange.min.js` (file doesn't exist) — dead code.~~ Removed 2026-08-17.
- ~~Template placeholder cards commented out in project.html, blog.html, kaggle.html, visualisation.html.~~ Deleted 2026-08-17.

## Pending assets
These files are referenced in code but do not exist yet — **action required from site owner**:
- `images/og-preview.png` — OG/Twitter card image, should be 1200x630px. Tags are live but image will 404 until created.
- ~~`assets/resume.pdf`~~ — Added by site owner 2026-08-11.
- `images/eia_placeholder.svg` — placeholder for EIA project card. Replace with a real screenshot once the project has a UI.
- CCRS live demo URL — Streamlit deployment blocked; link currently points to GitHub repo.

## Implementation decisions
- **Skills icons:** LangGraph, LlamaIndex, ChromaDB, FAISS have no official distributable icon. Used text-pill SVGs (dark rounded rectangle with tool name in Lato font) matching site palette. PyTorch, Hugging Face, FastAPI, AWS, MLflow use brand-color SVG icons.
- **EIA project card:** Uses inline styles for status badge ("In active development" pill) and tech stack tags — no new CSS classes added.
- **About duplication:** Investigated the 4-copy responsive pattern. No rendering bug exists; CSS correctly shows 1 variant per breakpoint. Removed 2 dead CSS rules (orphaned `.bigger-device-401px{display:block}` outside media queries).
- **Text-pill SVG sizing:** Redesigned from 200x60 to 200x80 viewBox (font-size 22→24) and set HTML `height="120"` to match brand SVG icons in the carousel.

## Working conventions
- This is an in-place refresh — no framework migration, no build step introduced. If a change would require one, flag it, don't do it.
- **Employer attribution discipline:** Do NOT reference Dell (or any prior employer) in personal-project descriptions, code comments, commits, or READMEs. Dell references remain only in the Experience section where they already exist.
- Commit granularity: one commit per logical change (e.g., `About: update bio for MS + patent + keynote`), never a single mega-commit.
- Never commit without showing the diff first.
- If a change touches `main.css` or any structural CSS, flag it and wait for confirmation before applying.
