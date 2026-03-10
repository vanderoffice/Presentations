[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Deployed: GitHub Pages](https://img.shields.io/badge/Deployed-GitHub_Pages-brightgreen.svg)](https://govfellows.github.io/presentations/)

# Innovation Fellowship Presentation Library

Interactive presentation decks for California's government modernization initiatives.

**Live →** [govfellows.github.io/presentations](https://govfellows.github.io/presentations/)

---

## Categories

| Category | Description | Decks |
|----------|-------------|:-----:|
| **Briefings** | Executive briefings and governance frameworks for state government leaders | 5 |
| **Training** | AI for California Government course modules for state employees | 6 live, 3 coming soon |
| **FellowOps** | Operational resources for Cohort 1 Senior Fellows | 1 |

---

## Training Course — AI for California Government

A structured course designed for California state employees with 10+ years of experience and spreadsheet-level technical skills.

| # | Module | Status |
|:-:|--------|--------|
| 1 | Perplexity AI for Government | 13 slides |
| 2 | GitHub for Non-Coders | 13 slides |
| 3 | Search, Research & Verification with AI | Coming Soon |
| 4 | Prompt Engineering for Government Work | Coming Soon |
| 5 | Quality Assurance for RAG Knowledge Bases | 16 slides |
| 6 | The Agentic Future: AI in Government Operations | Coming Soon |
| 7 | WaterBot: Building a Government AI Assistant | 23 slides |
| 8 | Building a Presentation Pipeline with AI | 19 slides |
| 9 | Production Hardening for Government Web Services | 20 slides |

---

## Architecture

All decks are standalone [Reveal.js](https://revealjs.com/) HTML files — no build step, no dependencies, no server required.

```
presentations/
├── index.html          # Hub page
├── decks.json          # Manifest (source of truth)
├── decks/              # All deck HTML + source markdown
├── briefings/          # Briefings category page
├── training/           # Training category page
├── fellowops/          # FellowOps category page
├── img/                # Shared images
└── lab/                # Experimental decks
```

> **Manifest-driven:** `decks.json` defines all categories, decks, and metadata. The hub and category pages render from it dynamically.

## Adding a Deck

1. Build the deck HTML (via the `/deck` skill or manually)
2. Place the compiled `.html` in `decks/`
3. Add an entry to `decks.json` under the appropriate category
4. Push to `main` — GitHub Pages deploys automatically

## Design

Dark theme · Inter font · CSS custom properties for theming · Fully responsive layouts. Each category has its own accent color (blue, gold, teal).

---

## License

MIT
