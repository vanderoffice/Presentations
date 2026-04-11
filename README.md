[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

# VanderDev Presentations

Briefings and technical training decks for California government modernization.

---

## Categories

| Category | Description | Decks |
|----------|-------------|:-----:|
| **Briefings** | Executive briefings, governance frameworks, and agency overviews | 9 |
| **Training** | AI implementation patterns, production operations, and engineering practices | 4 |

---

## Briefings

| Deck | Date |
|------|------|
| Building GenAI Chatbots for Government | Mar 2026 |
| Digital Transformation in Corrections | Mar 2026 |
| Agentic Engineering for California State Government | Feb 2026 |
| CDCR Technology Landscape | Feb 2026 |
| CA Enterprise Modernization Plan | Jan 2026 |
| CA Enterprise Modernization Appendix | Jan 2026 |
| Technical Executive Assignment: Cabinet Briefing | Jan 2026 |
| Claude Code Deployment at SWRCB | Jan 2026 |
| Digital Transformation in Corrections (v1) | Jan 2026 |

## Training

| # | Module | Slides |
|:-:|--------|--------|
| 1 | Prompt & Context Engineering for Government Work | 24 |
| 2 | Quality Assurance for RAG Knowledge Bases | 16 |
| 3 | WaterBot: Building a Government AI Assistant | 23 |
| 4 | Production Hardening for Government Web Services | 20 |

---

## Architecture

All decks are standalone [Reveal.js](https://revealjs.com/) HTML files. No build step, no dependencies, no server required.

```
presentations/
├── index.html          # Hub page
├── decks.json          # Manifest (source of truth)
├── decks/              # All deck HTML + source markdown
├── briefings/          # Briefings category page
├── training/           # Training category page
└── img/                # Shared images
```

> **Manifest-driven:** `decks.json` defines all categories, decks, and metadata. Hub and category pages render from it dynamically.

## Adding a Deck

1. Build the deck HTML (via the `/deck` skill or manually)
2. Place the compiled `.html` in `decks/`
3. Add an entry to `decks.json` under the appropriate category
4. Push to `main`

## Design

Dark theme. Inter font. CSS custom properties for theming. Fully responsive layouts.

---

## License

MIT
