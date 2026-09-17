# Contributing to Better Rizal, Nueva Ecija

Thank you for helping build a transparency portal for the Municipality of Rizal, Nueva Ecija. This guide explains how to find work, set up your environment, and get your changes merged.

## Finding a Task

The [BETTER RIZALNE PROGRESS board](https://github.com/users/njveneracion/projects/3) is the entry point — **not** the raw issue list. Priority lives in the board's `Priority` field and does not render on `/issues`.

**The rule — one rule for every contributor:**

> Take any open issue in the **highest non-empty `Priority` band** that has **no open blockers**.

- `P1` — launch blockers. Do these first.
- `P2` — enhancements and post-launch work. Do these once P1 is clear.
- `P0` is reserved for emergencies/critical bugs.

Issues are tagged `good first issue` where little repo context is needed — start there if you are new.

**How to claim a task:**

1. Pick an unblocked issue from the highest non-empty band (P1 first).
2. Read the description and acceptance criteria.
3. Comment on the issue stating you'd like to work on it.
4. Start once a maintainer assigns it (or gives a thumbs up).

## Definition of Done

Every issue closes only when all of its `Acceptance Criteria` checkboxes are met **and** the shared quality bar below passes. The acceptance criteria are the _what_; the checklist below is the _how_.

### Shared Quality Bar (applies to every PR)

- [ ] `npm run lint` passes
- [ ] `npm run build` passes (TypeScript + Vite)
- [ ] No secrets or env values committed (only `env.example`, never `.env.local`)
- [ ] Content is accurate and sourced (cite COA/COMELEC/official sources where relevant)
- [ ] No hardcoded references to another LGU (e.g. "Lapu-Lapu City") left in place
- [ ] At least one maintainer has reviewed and approved

### Content-Only Changes

- Markdown follows the [CONTENT-GUIDE.md](CONTENT-GUIDE.md) structure (title, description, clear headings)
- YAML slugs match filenames and are registered in `src/data/yamlLoader.ts`
- Verified locally with `npm run dev`

### Code Changes

- Follow existing patterns and code style (single quotes, 2-space indent, trailing commas, semicolons, 80-char width)
- Components use the shared primitives in `src/components/ui/`
- Accessibility maintained (semantic HTML, heading order, alt text)

## Development Setup

### Prerequisites

- Node.js 18+
- npm

### Setup

```bash
# Fork, then clone
git clone https://github.com/YOUR-USERNAME/betterrizalne.git
cd betterrizalne

# Add upstream (starter kit) remote to pull improvements
git remote add upstream https://github.com/iyanski/betterlocalgov.git

# Install
npm install

# Configure local env (copy env.example -> .env.local)
npm run setup

# Start dev server
npm run dev
```

### Quality Checks

```bash
npm run lint        # ESLint
npm run build       # TypeScript + production build
npm run format      # Prettier
```

A pre-commit hook (`lint-staged`) runs ESLint + Prettier on staged files automatically.

## Branching, Commits & Pull Requests

### Branch Naming

```
feature/[issue-title]-[issue-number]
```

Use a short kebab-case version of the issue title followed by the issue number.

Examples: `feature/add-civil-registry-33`, `feature/fix-footer-links-34`, `feature/agriculture-pages-5`.

### Commit Messages

The first word of every commit message is always a **verb**, in past tense.

```
<verb> <short description>
```

Common verbs: `Added`, `Changed`, `Deleted`, `Fixed`, `Updated`, `Removed`, `Refactored`, `Documented`.

Examples:

```
Added civil registry service category (#33)
Fixed broken accessibility footer link (#34)
Changed executive.json to Rizal NE officials (#2)
Deleted Lapu-Lapu City placeholder text (#3)
```

### Pull Request Titles

The PR title is the **issue title + issue number**.

```
<Issue Title> #<issue-number>
```

Examples: `Add Civil Registry services #33`, `Fix broken footer links #34`.

### Pull Request Process

1. Rebase on the latest `main`.
2. Run `npm run lint && npm run build`.
3. Verify against the issue's acceptance criteria and the shared quality bar.
4. Open a PR titled `<Issue Title> #<issue-number>`, linking the issue (e.g. `Closes #12`).
5. A maintainer reviews; address any feedback.

## Contributing Without Code

You don't need to code to help. Content edits can be made entirely in the GitHub web UI:

1. Browse to any `.md` or `.yaml` file under `content/`.
2. Click the pencil (✏️) to edit.
3. Make your change and click **Commit changes**.
4. Open a PR for review.

See [CONTENT-MANAGEMENT.md](CONTENT-MANAGEMENT.md) for a full walkthrough.

### High-value non-code work

- **Accuracy** — fix outdated service info, verify official contact details
- **Translations** — Filipino (Tagalog) content
- **Data gathering** — COA budget figures, COMELEC officials, ordinances
- **Review** — check pages for clarity, completeness, and accessibility

## Getting Help

- **Docs:** [README.md](README.md), [CONTENT-GUIDE.md](CONTENT-GUIDE.md), [DEPLOYMENT-GUIDE.md](DEPLOYMENT-GUIDE.md)
- **Issues:** open a question in [GitHub Issues](https://github.com/njveneracion/betterrizalne/issues)
- **Community:** [BetterGov.ph](https://github.com/jmacj/better-lgu-directory)

Thank you for helping make local government information accessible to every resident of Rizal, Nueva Ecija.
