# Future Corey: design-ai

Updated: 2026-06-05

## What This Is

Personal maintained fork and local reference clone of Khalidabdi1/design-ai. A curated library of 200+ `DESIGN.md` files that capture the visual design systems (colors, typography, components, layout, elevation, responsive behavior, and agent prompt guides) of popular websites and products (Stripe, Apple, Figma, Linear, Notion, etc.).

Primary job: give AI coding and design agents concrete, high-fidelity style references so generated UIs can match a known brand's design language instead of generic defaults.

Includes our automation for keeping the fork in sync with upstream.

## Current State

- Fully functional as a reference library.
- GitHub fork with daily automated sync (PR-based, not blind push): https://github.com/coreyhall93/design-ai
- Local clone lives under Sol per workspace conventions.
- Upstream remote is configured for manual inspection or one-off merges.
- Content is read-mostly. We rarely edit upstream files directly; updates arrive via sync PRs. We added the sync workflow + these Sol docs.

## Where Things Live

- Local source: `~/Sol/02-Projects/design-ai/`
- GitHub (origin): https://github.com/coreyhall93/design-ai (your controlled fork)
- Upstream: https://github.com/Khalidabdi1/design-ai (git remote named `upstream`)
- The actual design systems: `design-md/<company-or-product-slug>/DESIGN.md` (plus optional preview-*.html)
- Sync automation: `.github/workflows/upstream-sync.yml`
- Original project docs: `README.md`, `CONTRIBUTING.md`, `AGENTS.md` (from upstream)

## Next Move

To pull the latest design systems:

1. Visit the GitHub fork and merge (or review) any open "chore: sync with upstream design-ai" PR.
2. In this directory: `git pull`
3. Copy the specific file(s) you need, e.g.:
   `cp design-md/stripe/DESIGN.md /path/to/your-project/DESIGN.md`
4. Tell your agent: "Use the DESIGN.md in this project as the design source of truth."

To force a fresh sync check (without waiting for the daily cron): GitHub → Actions → "Sync with upstream" → "Run workflow".

## Gotchas

- Syncs are delivered as PRs so you can see exactly what changed (new companies, README index updates, token fixes). Merge them when ready.
- Because we have an extra commit (the workflow + Sol docs) on our main, merges from upstream are usually clean.
- Conflicts are uncommon (most additions are new directories) but will be visible in the sync PR if they occur.
- Do **not** vendor the entire collection into every project. Selectively copy only the DESIGN.md files you are actively using.
- The upstream repo is actively maintained (new companies added frequently by the original author + community).

## Deeper Docs

- `README.md` (upstream library overview and full company list)
- `.github/workflows/upstream-sync.yml` (how the automation works)
- Upstream original + contribution guide: https://github.com/Khalidabdi1/design-ai
- `CONTRIBUTING.md` (if you ever want to improve or add a DESIGN.md following the 9-section format)
