# Agent Notes — design-ai (Sol reference)

## Read Order (when the task involves matching a known design language)

1. `FUTURE_COREY.md` — current local state and resume steps
2. `README.md` — upstream overview + full index of available companies
3. The specific target: `design-md/<slug>/DESIGN.md` (e.g. `design-md/linear/DESIGN.md`)
4. `CONTEXT.md` — why we maintain this fork
5. `.github/workflows/upstream-sync.yml` — only if modifying the automation

## Guidance

- **Primary use case**: When asked to "build this in the style of X" or "match the Stripe / Figma / Linear / Apple design system", locate the matching DESIGN.md here (or in the personal GitHub fork) and have the user (or the target project) copy it in as the source of truth.
- Prefer references from `~/Sol/02-Projects/design-ai/` or `https://github.com/coreyhall93/design-ai` so that updates flow through our controlled sync process.
- The files are intentionally human + LLM readable. Quote or inline relevant sections (color roles, typography scale, component rules, do's/don'ts, agent prompt guide) when giving instructions to other agents or models.
- If a requested brand is missing, the cleanest path is usually:
  1. Open an issue on the upstream repo (https://github.com/Khalidabdi1/design-ai) using their request template, or
  2. Create a local `design-md/my-internal-brand/` following the 9-section structure documented in upstream `CONTRIBUTING.md` and `README.md`.
- Do not suggest committing the entire `design-md/` tree into random projects. The value is selective reuse of individual DESIGN.md files.
- The preview HTML files (when present) can be opened in a browser for quick visual confirmation of the documented tokens and components.

## Local vs Upstream

- Upstream = the canonical, community-curated collection.
- This fork = our always-available local mirror + any personal extensions.
- Sync PRs on the GitHub fork are the mechanism that keeps the two aligned. Merge them deliberately.

## Related

- Upstream repo and contribution rules: https://github.com/Khalidabdi1/design-ai
- Sol workspace conventions: `~/Sol/README.md`, `~/Sol/07-Systems/Conventions/Project-Creation-Directive.md`
