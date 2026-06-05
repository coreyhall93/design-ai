# design-ai Context

## Purpose

Durable personal reference library of real-world website and product design systems, expressed as portable `DESIGN.md` files that AI agents can read and follow.

## Why It Exists Here

The upstream project (Khalidabdi1/design-ai) does the hard work of extracting and structuring high-quality design tokens, component patterns, and style guidance from public sites into a consistent 9-section markdown format. This is extremely valuable for:

- Rapid AI-assisted UI prototyping that feels "on-brand"
- Studying how real design systems are implemented
- Giving agents concrete examples instead of vague instructions ("make it look like Stripe")

We maintain a personal fork so we can:
- Automatically track new additions without manual effort
- Have a stable local path inside the Sol workspace
- Optionally layer personal notes, custom companies, or tweaks without affecting the public upstream

## Key Decisions

- Forked to `coreyhall93/design-ai` on GitHub (standard GitHub fork relationship preserved).
- Added a scheduled GitHub Action (`.github/workflows/upstream-sync.yml`) that opens a PR for upstream changes rather than force-pushing. This gives a review step and clean history of sync points.
- Placed at `~/Sol/02-Projects/design-ai/` per the Sol project placement rules for durable, versioned work.
- Consumption model: selective file copies into consuming projects (or git submodule / reference in prompts when appropriate). Not intended to be a dependency in the traditional sense.
- Local `FUTURE_COREY.md`, `CONTEXT.md`, and `AGENTS.md` added to make this a proper Sol citizen while leaving upstream files untouched.

## Handoff Notes

- The sync PR mechanism is the primary way updates arrive. Merge them on GitHub, then pull locally.
- If you want to contribute improvements or new companies back, the preferred path is usually an issue or PR on the original upstream repo (see their `CONTRIBUTING.md` and the 9-section template).
- For purely personal or internal brands, you can add new `design-md/personal/my-company/` directories here and they will stay in your fork (see `RESEARCH-AUTOMATTIC-BRANDS.md` for the pattern used for the 2026 Automattic brands).
- Preview HTML files (when present) are useful for visually sanity-checking the documented tokens.
- Detailed research findings + polish roadmap for the Automattic brands personal additions live in `RESEARCH-AUTOMATTIC-BRANDS.md`.

See also the root `README.md` (from upstream) for the full list of available design systems and how to use a DESIGN.md with agents.
