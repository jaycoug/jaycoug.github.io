# jaycoug.github.io

Personal website for Jay Coughlon, statistician and data analyst,  built as a static Jekyll site and hosted on GitHub Pages at [jaycoug.github.io](https://jaycoug.github.io). GitHub Pages builds and deploys automatically on every push to `main`; no CI config is needed unless a future Jekyll plugin falls outside GitHub Pages' supported plugin list.

## Site overview

The site has three pages, Home, About Me, and Projects, sharing one layout (`_layouts/default.html`) that wraps every page in a responsive `.page-wrapper`, a three-link nav (`_includes/nav.html`), and a footer with a contact mailto link (`_includes/footer.html`). Site identity (title, description, canonical URL) lives in `_config.yml` and propagates into every page's browser-tab title automatically via `{{ site.title }}`.

**Home** (`index.md`) leads with a one-sentence identity statement, groups the work by outcome, names the M.S. in Biostatistics at the University of Louisville (projected December 2027), and points to the Projects page.

**About Me** (`about.md`) is a professional narrative covering the Air Force-to-statistics career pivot, the undergraduate wavelet-compression research finding that seeded the DSP Explorer Applet, and a paragraph per active project.

**Projects** (`projects.md`) renders a card per portfolio project by looping over `_data/projects.yml` with Liquid. Each entry carries a domain, a tech-stack list, and full case-study fields (question, data, data preparation, methods, findings, limitation, links). Adding, removing, or reordering a project is a YAML edit, not a markup change. Three projects are live right now, chosen as the current development priority (as of 2026-07-16):

- **KYBRFSS Dashboard App** — feature-complete, hosted externally.
- **Walmart M5 Forecasting** — early-stage; card text reflects real progress (data profiling only), not the planned end-state pipeline.
- **USL Championship Analytics** — early-stage; card text reflects the real build state (extraction and cleaning complete; modeling and the dashboard itself not yet started).

Card copy for the two early-stage projects intentionally describes what's built, with the fuller planned methodology framed as a roadmap.

The other seven portfolio projects (Stroke Registry Mortality Risk Calculator, DSP Explorer Applet, Statistics & Data Science Toolkit, SEQIP Stroke Dashboard, and the Food Demand → Freight Flow → HHS Cybersecurity sequential pipeline) are tabled in `projects_overview.md` — a planning doc kept outside this repo — with ready-to-paste YAML blocks for promoting one into `_data/projects.yml` whenever it becomes the active priority.

## Repo structure

```
jaycoug.github.io/
├── _config.yml
├── Gemfile
├── _data/
│   └── projects.yml
├── _layouts/
│   └── default.html
├── _includes/
│   ├── nav.html
│   └── footer.html
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   └── img/
├── index.md
├── about.md
├── projects.md
└── README.md
```

## Tech stack

Plain HTML/CSS/Liquid throughout, no bundler. JS interactivity (once added) uses plain `<script>` files, and any charting library gets linked via a CDN tag rather than installed as a dependency. No dark/light mode yet — visual identity (colors, fonts, spacing beyond the responsive CSS baseline) is still an open design pass, tracked in `pwbp_dev.md`.