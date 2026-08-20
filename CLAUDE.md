# CLAUDE.md

## Project overview
- Personal portfolio site for **Ishika Johari**.
- Live URL: https://ishijo.github.io/
- Deployment: GitHub Pages, `master` branch, no build step (static HTML/CSS/JS).
- Template lineage: **HTML5 UP "Twenty"** (html5up.net), CC-BY 3.0 license.

## File structure

| File | Content |
|------|---------|
| `index.html` | Single-page layout: Banner (~112), About (~129), Highlights (~188), Skills (~212), Portfolio shell (~275), Experience (~371), Resume (~446), Footer (~463) |
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
| 1 | About | ✅ Done 2026-08-18 — behavioral-science-wedge copy, TIA→EIA lineage, MS completed, patent + Kaggle Days + Google capstone mentioned. Applied to all 4 responsive variants. |
| 2 | Projects | ✅ Done 2026-08-18 — EIA card added (2026-08-17), CCRS card refreshed (2026-08-17), Google Vanir capstone card added at position 2 (2026-08-18) |
| 3 | Skills | ✅ Done 2026-08-17 — carousel overhauled (removed Hadoop/Teradata/HTML/CSS, added 9 new tools) |
| 4 | Experience | ✅ Done 2026-08-18 — Full overhaul with resume-verbatim bullets. 5 entries: Grad Research Scholar (3 bullets), DS Intern (1), DS2 (3), DS1 (4), Data Analyst Intern (1, consolidated from 2 intern entries). |
| 5 | Structural cleanup | ✅ Done 2026-08-17, regression fixed 2026-08-19 — OG tags added, resume link updated, CSS dead code removed, jQuery 1.4 CDN removed (tab script moved to EOF to compensate — see `b933904`), template placeholder cards deleted, duplicate class attribute fixed, HTML5 UP attribution added, favicon refs fixed in sub-pages, unreferenced skill PNGs deleted, text-pill SVG heights normalized. |

## Content gaps to close
- ~~Filed patent (ML-driven insights platform) — currently invisible on site.~~ Mentioned in About copy and DS1 Experience bullet 2026-08-18.
- ~~Kaggle Days global keynote on A/B testing — currently invisible.~~ Mentioned in About copy and Highlights section 2026-08-18.
- ~~MS in Information Management at UW — status wording needs updating (banner and About still read as "pursuing").~~ Fixed in About and banner 2026-08-18 (now reads "recently finished").
- ~~Dell tenure: 2 years, DS1→DS2 promotion.~~ Split into DS1 (4 bullets) and DS2 (3 bullets) entries 2026-08-18.
- ~~Experimentation Intelligence Agent project — not on site yet.~~ Added 2026-08-17.
- ~~Cross-Content Recommender — needs real screenshot, live demo link, and metrics.~~ Card refreshed 2026-08-17. Live demo link still blocked (deployment issue).
- ~~Google capstone — not on site.~~ Vanir card added 2026-08-18; mentioned in About copy.

## Structural issues to fix
- About section paragraph duplicated 4x for responsive breakpoints — `.bigger-device-401px` variant is dead code; could reduce to 3 copies or investigate CSS-only solution for 1 copy.
- ~~Missing Open Graph / Twitter card meta tags.~~ Added 2026-08-17.
- ~~"Request Resume" links to Google Drive folder.~~ Changed to `assets/resume.pdf` download 2026-08-17.
- ~~Skills icons don't reflect current stack.~~ Overhauled 2026-08-17.
- ~~`index.html:38–39` loads jQuery 1.4 + `js/jquery.ba-hashchange.min.js` (file doesn't exist) — dead code.~~ jQuery 1.4 CDN removed 2026-08-17; caused Portfolio tab regression (tabs navigated as full pages). Fixed 2026-08-19 by moving tab script to after EOF jQuery load (`b933904`). Hashchange plugin was genuinely dead code.
- ~~Template placeholder cards commented out in project.html, blog.html, kaggle.html, visualisation.html.~~ Deleted 2026-08-17.

## Pending assets
These files are referenced in code but do not exist yet — **action required from site owner**:
- `images/og-preview.png` — OG/Twitter card image, should be 1200x630px. Tags are live but image will 404 until created.
- ~~`assets/resume.pdf`~~ — Added by site owner 2026-08-11.
- `images/eia_placeholder.svg` — placeholder for EIA project card. Replace with a real screenshot once the project has a UI.
- `images/vanir_placeholder.svg` — placeholder for Vanir capstone card. Replace with a real screenshot.
- CCRS live demo URL — Streamlit deployment blocked; link currently points to GitHub repo.

## Implementation decisions
- **Skills icons:** LangGraph, LlamaIndex, ChromaDB now use real PNG icons (added 2026-08-20). FAISS still uses text-pill SVG (no PNG available). PyTorch, Hugging Face, FastAPI, AWS, MLflow use brand-color SVG icons. All icons at `height="120"` except Python/PostgreSQL/Docker/Tableau PNGs at `height="150"`.
- **EIA project card:** Uses inline styles for tech stack tags — no new CSS classes added. Status badge and "Repo coming soon" text removed 2026-08-20; GitHub link added.
- **About duplication:** Investigated the 4-copy responsive pattern. No rendering bug exists; CSS correctly shows 1 variant per breakpoint. Removed 2 dead CSS rules (orphaned `.bigger-device-401px{display:block}` outside media queries).
- **Text-pill SVG sizing:** Redesigned from 200x60 to 200x80 viewBox (font-size 22→24) and set HTML `height="120"` to match brand SVG icons in the carousel.
- **Highlights section:** Inline flexbox layout (no new CSS classes) with emoji + text + right-aligned muted date. Uses `wrapper style2 container special` for visual contrast from adjacent Skills (style1).
- **Vanir card:** Links to upstream Google repo (`github.com/google/vanir`), not a personal fork. Status badge removed 2026-08-20.
- **Banner tagline:** Dropped credential list in favor of single positioning statement. No longer mentions Kaggle 3X Expert (moved to Highlights).
- **Experience DS1/DS2 split:** Dell tenure split into two entries with distinct date ranges and team attribution ("Experimentation Team" vs "Data Governance Team"). Title deliberately uses "Graduate Research Scholar" (not "AI Research Scholar" from resume) for consistency with Highlights section.

## Working conventions
- This is an in-place refresh — no framework migration, no build step introduced. If a change would require one, flag it, don't do it.
- **Employer attribution discipline:** Do NOT reference Dell (or any prior employer) in personal-project descriptions, code comments, commits, or READMEs. Dell references remain only in the Experience section where they already exist.
- Commit granularity: one commit per logical change (e.g., `About: update bio for MS + patent + keynote`), never a single mega-commit.
- Never commit without showing the diff first.
- If a change touches `main.css` or any structural CSS, flag it and wait for confirmation before applying.
- **Portfolio tab script dependency:** The inline `<script>` after `main.js` at EOF registers `.click()` handlers for Portfolio tab fragment loading via jQuery `.load()`. Do not move this script to `<head>` or remove/relocate `assets/js/jquery.min.js` without verifying that all 4 Portfolio tabs (Projects, Visualisations, Kaggle, Blogs) still load inline. The jQuery 1.4 CDN removal in Session 2A caused a silent regression because this script originally lived in `<head>` and depended on early jQuery availability.
