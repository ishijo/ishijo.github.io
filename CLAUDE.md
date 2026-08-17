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
| `images/skills/` | Skill logo PNGs for the carousel |

**Responsive About section:** The About bio paragraph is duplicated 4 times in `index.html` (~lines 139–170) for 4 CSS breakpoint variants. Every content edit must be applied to all 4 copies.

## Target audience & positioning
- Aimed at recruiters and hiring managers for **Product Data Scientist, MLE, and AI Engineer** roles at consumer tech companies (Spotify/Netflix/Airbnb tier).
- Positioning wedge: **experimentation + recommendation systems**.

## Content refresh plan — Path A (in progress)

| Pass | Focus | Status |
|------|-------|--------|
| 1 | About | Copy-drafting stage (not yet applied to site) |
| 2 | Projects | Not started |
| 3 | Skills | Not started |
| 4 | Experience | Not started |
| 5 | Structural cleanup | Not started |

## Content gaps to close
- Filed patent (ML-driven insights platform) — currently invisible on site.
- Kaggle Days global keynote on A/B testing — currently invisible.
- MS in Information Management at UW — status wording needs updating (banner and About still read as "pursuing").
- Dell tenure: 2 years, DS1→DS2 promotion — currently understated.
- Experimentation Intelligence Agent project — not on site yet.
- Cross-Content Recommender — needs real screenshot (see ccrs.jpg update), live demo link, and metrics.

## Structural issues to fix
- About section paragraph duplicated 4x for responsive breakpoints — investigate whether CSS-only solution can reduce to 1 copy.
- Missing Open Graph / Twitter card meta tags — link preview renders blank when shared.
- "Request Resume" links to a Google Drive folder — replace with a direct PDF download from the repo.
- Skills icons don't reflect current stack. Remove: Hadoop, Teradata, standalone HTML/CSS. Add: PyTorch, LangGraph, LlamaIndex, ChromaDB/FAISS, SBERT/sentence-transformers, FastAPI, AWS, MLflow, and experimentation tooling.
- `index.html:38–39` loads jQuery 1.4 + `js/jquery.ba-hashchange.min.js` (file doesn't exist) — dead code, safe to remove.
- Template placeholder cards commented out in project.html, blog.html, kaggle.html, visualisation.html — safe to delete.

## Working conventions
- This is an in-place refresh — no framework migration, no build step introduced. If a change would require one, flag it, don't do it.
- **Employer attribution discipline:** Do NOT reference Dell (or any prior employer) in personal-project descriptions, code comments, commits, or READMEs. Dell references remain only in the Experience section where they already exist.
- Commit granularity: one commit per logical change (e.g., `About: update bio for MS + patent + keynote`), never a single mega-commit.
- Never commit without showing the diff first.
- If a change touches `main.css` or any structural CSS, flag it and wait for confirmation before applying.
