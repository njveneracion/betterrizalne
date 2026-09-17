# Better Rizal, Nueva Ecija

A community-maintained digital transparency portal for the Municipality of Rizal, Nueva Ecija. Built as part of the [BetterGov.ph](https://github.com/jmacj/better-lgu-directory) initiative — an independent, civic-minded website that makes local government information (services, officials, budgets, ordinances, and contacts) easy for citizens to find and understand.

> **Status:** 🔵 Planned — building toward a public launch at `betterrizalne.org`.
> Registered in the [Better LGU Directory](https://lgu.bettergov.ph) under _Rizal, Nueva Ecija_.

## Features

- **YAML-driven content** — edit Markdown and YAML files, never touch code
- **10 service categories** — Health, Education, Business, Social Welfare, Agriculture, Infrastructure, Waste, Environment, Disaster Preparedness, Housing
- **Government section** — Officials, Departments, News, Guides & Regulations, Reports & Statistics, Public Consultations, Transparency
- **Multilingual** — English today; Filipino and other Philippine languages supported via i18next
- **Full-text search** — Meilisearch-backed (with a static fallback planned)
- **SEO & Open Graph** — per-page metadata via react-helmet-async
- **Accessible** — WCAG 2.1 design
- **Mobile-first** — responsive layouts with Tailwind CSS v4
- **One-command setup** — `npm run setup` configures branding interactively

## Tech Stack

- **Framework:** [React 19](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/) (strict)
- **Build:** [Vite](https://vite.dev/)
- **Styling:** [Tailwind CSS v4](https://tailwindcss.com/)
- **Routing:** [React Router](https://reactrouter.com/)
- **i18n:** [i18next](https://www.i18next.com/)
- **Search:** [Meilisearch](https://www.meilisearch.com/)
- **Content:** YAML + Markdown via [js-yaml](https://github.com/nodeca/js-yaml) and [react-markdown](https://github.com/remarkjs/react-markdown)
- **UI:** [@bettergov/kapwa](https://github.com/bettergov/kapwa) + [Lucide](https://lucide.dev/) icons

## Quick Start

### Prerequisites

- Node.js 18+
- npm

### Install & Run

```bash
# Fork & clone
git clone https://github.com/njveneracion/betterrizalne.git
cd betterrizalne

# Install dependencies
npm install

# Configure your LGU (optional — defaults to the starter kit)
npm run setup

# Start the dev server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173).

## Scripts

| Command                 | Purpose                            |
| ----------------------- | ---------------------------------- |
| `npm run dev`           | Start dev server (localhost:5173)  |
| `npm run build`         | Type-check + production build      |
| `npm run lint`          | ESLint check                       |
| `npm run lint:fix`      | Auto-fix lint issues               |
| `npm run format`        | Prettier formatting                |
| `npm run setup`         | Interactive LGU setup script       |
| `npm run convert-yaml`  | Convert YAML content to JSON       |
| `npm run dev:yaml`      | Convert YAML then start dev server |
| `npm run index-content` | Index content into Meilisearch     |

## Project Structure

```
content/
├── government/           # Government pages (departments, news, reports, …)
│   └── departments/      # Department markdown & YAML
└── services/             # Service pages (10 categories)
    ├── health-services/
    ├── education/
    ├── business/
    └── …

public/
└── locales/              # i18next translation files (en, …)

src/
├── components/           # Reusable UI components
│   ├── home/             # Home page sections
│   ├── layout/           # Navbar, Footer
│   ├── sections/         # Shared sections
│   └── ui/               # UI primitives
├── data/                 # Top-level YAML configs + loaders
├── hooks/                # Custom React hooks
├── i18n/                 # i18next setup
├── lib/                  # Utilities (markdownLoader, yamlLoader, meilisearch)
├── pages/                # Route components (Home, Services, Government, Document, Search)
└── types/                # TypeScript types
```

## Routes

| Path                                  | Page                 |
| ------------------------------------- | -------------------- |
| `/`                                   | Home                 |
| `/services`                           | Services index       |
| `/services/:category`                 | Category listing     |
| `/services/:category/:documentSlug`   | Service document     |
| `/government`                         | Government index     |
| `/government/:category`               | Category listing     |
| `/government/:category/:documentSlug` | Government document  |
| `/search`                             | Search (Meilisearch) |
| `/:documentSlug`                      | Document (catch-all) |

## Content System

Content lives in `content/` as YAML indexes and Markdown pages:

1. `src/data/services.yaml` — service categories (name, slug, icon, description)
2. `content/services/{slug}/index.yaml` — pages per category
3. `content/services/{slug}/{page}.md` — Markdown content

The same pattern applies to `content/government/`. See [CONTENT-GUIDE.md](CONTENT-GUIDE.md) for the full authoring guide, and [CONTENT-MANAGEMENT.md](CONTENT-MANAGEMENT.md) for non-technical editing.

Markdown pages support `{PLACEHOLDER}` tokens resolved from companion `.json` files or `VITE_*` env vars (e.g. `{MAYOR}` in `executive.md`).

## Contributing

Contributions are welcome — from Rizal developers, civic volunteers, and residents.

- **Find a task:** the [BETTER RIZALNE PROGRESS board](https://github.com/users/njveneracion/projects/3) is the ranked backlog. Pick an open issue in the highest `Priority` band (P1 = launch blocker, P2 = enhancement).
- **Read the guide:** [CONTRIBUTING.md](CONTRIBUTING.md) covers setup, standards, and the definition of done.
- **Non-technical?** You can edit content directly on GitHub — see [CONTENT-MANAGEMENT.md](CONTENT-MANAGEMENT.md).

See [ROADMAP.md](ROADMAP.md) for the definition of done and planned future features.

## Documentation

| File                                           | Description                          |
| ---------------------------------------------- | ------------------------------------ |
| [ROADMAP.md](ROADMAP.md)                       | Definition of done + future features |
| [CONTRIBUTING.md](CONTRIBUTING.md)             | Contribution guidelines              |
| [CONTENT-GUIDE.md](CONTENT-GUIDE.md)           | Content writing guidelines           |
| [CONTENT-MANAGEMENT.md](CONTENT-MANAGEMENT.md) | Non-technical content editing guide  |
| [DEPLOYMENT-GUIDE.md](DEPLOYMENT-GUIDE.md)     | Deploy to Vercel & other platforms   |
| [docs/meilisearch.md](docs/meilisearch.md)     | Meilisearch setup                    |
| [CHANGELOG.md](CHANGELOG.md)                   | Version history                      |

## License

[CC0 1.0 Universal](LICENSE) — public domain. Use, modify, and distribute freely, no attribution required.

This project is a fork of [iyanski/betterlocalgov](https://github.com/iyanski/betterlocalgov), a starter kit for Philippine LGUs.

## Acknowledgments

- Built with [React](https://reactjs.org/) · [Vite](https://vite.dev/) · [TypeScript](https://www.typescriptlang.org/) · [Tailwind CSS v4](https://tailwindcss.com/)
- UI components by [@bettergov/kapwa](https://github.com/bettergov/kapwa)
- Icons by [Lucide](https://lucide.dev/) · i18n by [i18next](https://www.i18next.com/) · Search by [Meilisearch](https://www.meilisearch.com/)
- Community: [BetterGov.ph](https://github.com/jmacj/better-lgu-directory)

---

**Made with ❤️ for better local governance.**
