# Roadmap & Definition of Done

This document tracks the state of the backlog, the shared definition of done, and future features that are not yet ticketed. It is the living reference for what "done" means on **Better Rizal, Nueva Ecija** and what comes next.

## Backlog Status

The [BETTER RIZALNE PROGRESS board](https://github.com/users/njveneracion/projects/3) holds **45 issues** organized by `Priority`.

| Band   | Count                     | Scope                                                                                                      |
| ------ | ------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **P1** | #1–15, plus #28, #33, #34 | Launch blockers: Rizal NE identity, missing service pages, government categories, hotlines, civil registry |
| **P2** | everything else           | Enhancements: domain/deploy, i18n, SEO, tests, CI/CD, and larger features                                  |

Every issue carries its own `Acceptance Criteria` checkboxes — those are the _what_ of each ticket.

## Global Definition of Done

The per-issue acceptance criteria are necessary but not sufficient. Every change must also pass the shared quality bar in [CONTRIBUTING.md](CONTRIBUTING.md):

1. **Builds** — `npm run lint` and `npm run build` pass.
2. **Secure** — no secrets committed; only `env.example` (never `.env.local`).
3. **Accurate** — content sourced and current; no leftover references to another LGU.
4. **Reviewed** — at least one maintainer approval.

## What the Backlog Covers

| Area                                                   | Status                                                |
| ------------------------------------------------------ | ----------------------------------------------------- |
| Rizal NE identity (.env, officials, seal)              | ✅ Ticketed (P1)                                      |
| 10 service categories                                  | ✅ Ticketed — 4 have content, 6 need `.md` pages (P1) |
| Government categories (news, reports, transparency, …) | ✅ Ticketed (P1)                                      |
| Launch (domain, deploy, directory status)              | ✅ Ticketed (P2)                                      |
| Filipino translation                                   | ✅ Ticketed (P2)                                      |
| SEO, sitemap, 404, accessibility                       | ✅ Ticketed (P2)                                      |
| Search fallback, tests, CI/CD                          | ✅ Ticketed (P2)                                      |
| Report form, barangay map, PWA                         | ✅ Ticketed (P2)                                      |

## Future Features (Not Yet Ticketed)

These are known gaps outside the current backlog. Promote them to issues when the team is ready.

| Area                     | Why it matters                                               |
| ------------------------ | ------------------------------------------------------------ |
| Officials data pipeline  | Auto-import COMELEC/officials data instead of manual entry   |
| Budget data pipeline     | Auto-ingest COA/DBM budget figures into Reports & Statistics |
| Backend for report form  | Decide on a real intake backend (serverless / form service)  |
| Content freshness checks | Flag outdated service info automatically                     |
| Security hardening       | CSP headers, dependency scanning (Dependabot/renovate)       |
| News publishing workflow | A CMS or review flow beyond static markdown                  |
| Downloadable forms       | PDFs of permits, clearances, application forms               |
| Analytics dashboard      | Maintainer-facing view of traffic and content gaps           |
| Image/asset management   | Structured handling of mayor photos, OG images, seals        |

## Keeping This Document Current

- When a future feature is promoted to an issue, move it out of the table above.
- When a new gap is discovered, add it here and link the tracking issue.
- Revisit quarterly alongside the [BetterGov.ph](https://github.com/jmacj/better-lgu-directory) maintenance guidance.
