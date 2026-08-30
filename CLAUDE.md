# EXTREME Lab website — CLAUDE.md

This is the GitHub Pages site for the EXTREME Lab at the University of Illinois Urbana-Champaign.

- **Live URL**: https://extremelab-illinois.github.io
- **Future custom domain**: extreme.aerospace.illinois.edu
- **GitHub org**: https://github.com/extremelab-illinois
- **PI**: Francesco Panerai (fpanerai@illinois.edu)
- **Lab**: EXperimental Thermo-REactive Materials & Environments

## Stack

- Jekyll (GitHub Pages built-in renderer — no extra plugins, no build step needed locally)
- Pure HTML + CSS, no JavaScript frameworks
- IBM Plex font family (Sans Condensed, Serif, Mono) loaded from Google Fonts

## File structure

```
.
├── CLAUDE.md               ← you are here
├── _config.yml             ← site metadata and nav
├── index.html              ← homepage (Research, Code, Contact sections)
├── _layouts/
│   └── default.html        ← shared header, nav, footer
├── assets/
│   └── css/
│       └── site.css        ← all styles, design tokens as CSS variables
└── _data/                  ← YAML data files (to be added)
    ├── people.yml          ← lab members (coming soon)
    └── publications.yml    ← papers (coming soon)
```

## Pages roadmap (add one per session)

- [x] Homepage (index.html)
- [ ] People (_data/people.yml + people.html)
- [ ] Research (research.html)
- [ ] Publications (_data/publications.yml + publications.html)
- [ ] News / updates
- [ ] Openings

## Design system

The palette is a **temperature ramp** — used as a real scale, not decoration.
Each research area is tagged with the thermal regime it works in.

### Color tokens (defined in assets/css/site.css)

```
--paper:       #F1F2EF   background
--paper-sunk:  #E5E7E2   recessed surfaces
--ink:         #101418   primary text
--ink-mid:     #4B525A   secondary text
--rule:        #C7CAC3   dividers

--t-ambient:   #1B2A4A   300 K
--t-warm:      #3A4C8C   1200 K
--t-plasma:    #7A3FA6   2000–10000 K
--t-hot:       #C6402A   ablation regime
--t-incand:    #E8761B   incandescent
--t-white:     #EFC24E   white hot
```

### Typography

- `--display`: IBM Plex Sans Condensed — headings, labels, nav (uppercase, tight tracking)
- `--body`:    IBM Plex Serif — body text
- `--utility`: IBM Plex Mono — eyebrows, metadata, code

### Key CSS classes

- `.eyebrow` — small mono label above a section
- `.section-head` — condensed uppercase section title
- `.area` — research area card, accepts `--area-color` CSS variable
- `.repo` — code repository card
- `.scale` / `.scale__bar` — the thermal ramp bar (signature element)

## Conventions

- **Draft copy** is marked with `<!-- DRAFT -->` HTML comments — always rewrite before publishing
- **Data-driven pages**: add members, publications etc. as YAML in `_data/`, not hardcoded HTML
- **No JavaScript** unless absolutely necessary — keep it fast and accessible
- **Responsive**: mobile-first, test at narrow viewport
- **Accessibility**: semantic HTML, visible focus styles, skip link in layout
- **One commit per logical change** — small and incremental, one page or feature at a time