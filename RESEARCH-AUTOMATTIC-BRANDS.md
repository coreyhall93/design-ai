# Research & Polish Notes: Automattic Brands Personal DESIGN.md Additions

**Created:** 2026-06-05 (via Grok session with context-a8c MCP research)  
**Location in repo:** Root of this personal fork (`~/Sol/02-Projects/design-ai/RESEARCH-AUTOMATTIC-BRANDS.md`)  
**Related files:** 
- `design-md/personal/{automattic,wordpress-com,wordpress-org,woocommerce,jetpack}/` (the additions + previews)
- `AGENTS.md` (especially "Managing the Fork & Upstream Syncs" section)
- `FUTURE_COREY.md` and `CONTEXT.md` (high-level context)
- `README.md` (updated index with *(personal)* notes)

This document is for **future you (or any AI agent)** when you have time to come back. It captures what was done, sources, findings, limitations, and prioritized next steps for polishing.

## Summary of What Was Done

- Confirmed none of the requested brands existed in the (synced) collection.
- Used **context-a8c MCP** (as explicitly requested) to search internally:
  - Loaded providers: `mgs`, `wpcom`, `slack`, `github`, `themes`, `jetpack`, `linear`.
  - Key actions: `mgs.search`, `wpcom.p2-sites` + `posts-text` (on designomattic, wpbranddesign), `slack.search` + `messages` (design-systems channel), `github.file` + `search-repositories` + `search-code` (color-studio, gutenberg), etc.
- Created 5 new entries under `design-md/personal/` (safe location to avoid upstream conflicts, per our fork guidance).
- Each has:
  - Complete 9-section `DESIGN.md` (following the exact template from the repo: Visual Theme, Color Palette & Roles, Typography, Components, Layout, Depth/Elevation, Do's/Don'ts, Responsive, Agent Prompt Guide).
  - Minimal `preview.html` + `preview-dark.html` (color swatches + basic component examples using the tokens).
- Updated `README.md` company library + badge.
- Committed and pushed everything to your fork (`coreyhall93/design-ai`).
- The entries are based on the **shared modern WordPress Design System (WPDS)** that Automattic products are actively migrating to/adopting (see findings below), with brand-specific overlays.

These are **personal additions** for your use with AI agents in your projects. They live only in your fork (not upstream).

## Key Research Sources & Findings

### 1. Shared Foundation: WordPress Design System (WPDS) + Design Tokens
- **Primary source:** `WordPress/gutenberg` repo, `packages/theme/`
  - Full design tokens fetched: `src/prebuilt/css/design-tokens.css` (all `--wpds-*` CSS custom properties).
  - Also the JS list of tokens.
  - This is the **current source of truth** being rolled out across Automattic (Calypso/WordPress.com, Jetpack, etc.).
- Key values extracted (examples; full file in the DESIGN.mds or re-fetch as needed):
  - Brand interactive: `--wpds-color-bg-interactive-brand-strong: #3858e9`
  - Neutrals: Full gray scale (#f6f7f7 Gray 0 → #101517 Gray 100)
  - Typography: System sans (`-apple-system, system-ui...`), specific sizes/weights/line-heights (e.g., 32px/600 for large headings, 16px/400 body).
  - Spacing: Base 4px unit, padding/gap scales (xs 4px → 3xl 40px+).
  - Elevation: Layered box-shadows (xs for tooltips → lg for modals).
  - Motion, cursors, focus rings, etc.
- Migration context (from Slack #design-systems):
  - Active "Design System: Reimagined" project (Linear).
  - Heavy use of `@wordpress/ui` components + `@wordpress/theme` tokens.
  - Jetpack/Calypso adopting runtime `design-tokens.css` (with build-time fallbacks for legacy `_inc` pages).
  - Specific PRs mentioned for token linting, component migrations, Storybook improvements, AI tooling for the design system (e.g., search synonyms in stories, MCP server manifest).

### 2. Brand-Specific Palettes: Automattic/color-studio
- Official repo: `Automattic/color-studio`
- Fetched `dist/colors.json` (v4.1.0).
- Exact hex values used:
  - **Automattic Blue**: `#24a3e0` (legacy/primary accent); modern WPDS uses `#3858e9` (also listed as "WordPress Blue").
  - **WooCommerce Purple**: `#720eec` (and variants like #873eff, #6108ce).
  - **Jetpack Green**: `#069e08` (and variants).
  - **WordPress Blue**: `#3858e9` (core for .com / .org alignment).
  - Full neutrals + semantic states (success #008a20, error #d63638, etc.).
- README confirms it's the palette for Automattic products, with SCSS/JS exports.

### 3. Brand Alignment & Personality: wpbranddesign + designomattic P2s
- `wpbranddesign.wordpress.com` (recent posts fetched via wpcom `posts-text`):
  - "1. Global Footer - Redesign" and "2. Global Footer - Brands alignment Audit" (June 2026).
  - Exact Tier 1 list matching your request: Automattic (automattic.com, .design, for-agencies), WordPress.com, WordPress.org, WooCommerce, WP VIP, Jetpack.
  - Audits of "Automattic bar" taglines (e.g., "An AUTOMATTIC experiment" for WP.com, "thingamajig" for Woo, "airline" for Jetpack, "Creation" for VIP, etc.).
  - Layout commonalities, mobile menu patterns, CTA banners, newsletter modules.
  - Figma links provided (e.g., https://www.figma.com/design/nRuj7a7p0EsBuyJjVopxcF/Dotcom-Global-Navigation-2026---New-taxonomy?... ) for visual explorations and alignment.
  - Proposals for "to each their own" or "choose your adventure" layouts while unifying the Automattic signature.
- `designomattic.wordpress.com`: Hub with daily digests, cross-posts from other design P2s (payments, radical updates, etc.). Good for ongoing context.
- Other P2s surfaced: dotcomdesignp2, dotorgdesign, woocommercep2, jetpackp2, vipmarketingp2.

### 4. Product-Specific Migration & Usage
- **Jetpack**: Heavy focus in Slack (admin-ui package, token-only stylesheet enqueue, legacy `_inc` handling, Status component migration to Text + WPDS colors). PRs like #49345, #48750, #48711.
- **WordPress.com (Calypso)**: Adopting @wordpress/ui Badge, Masterbar, etc. Removing custom @automattic/ui duplicates. Design token stylelint rules.
- **Automattic overall**: Unifying under WPDS while preserving brand personality (see alignment posts).
- **WooCommerce / WordPress.org**: Referenced in the same Tier 1 alignment work; Woo has distinct purple energy; .org has classic community blue + open-source practical feel.
- Linear mentions of design system project updates.

### 5. Public Cross-Checks
- Sites like automattic.com (haiku style, product list), wordpress.com, woocommerce.com, jetpack.com, wordpress.org for current visual language.
- Confirmed shared blue/purple/green accents + clean modern UIs.

## Limitations of the Current Additions
- **Synthesized, not exhaustive extraction**: Pulled tokens + snippets + P2 summaries + public sites. Not full pixel audits or direct Figma scraping (tools don't provide Figma file access; links are in the P2 posts for you to open manually).
- Previews are **very minimal** (basic swatches + one button/card). Not full component catalogs.
- Some details (exact current component styles on live sites, full typography scales per brand, dark mode nuances) could be refined with more time.
- These reflect the **2026 state** of migration to WPDS. Legacy styles still exist in some places (e.g., Jetpack `_inc`).
- Personal only — upstream may eventually add official versions (hence the `personal/` subdir).

The DESIGN.md files include "Sources" sections at the bottom for traceability.

## Best Practices / Patterns Established Here
- **For personal/custom brands**: Always add under `design-md/personal/<slug>/` (or `local/`). This was followed and documented.
- **Base on shared systems**: For Automattic ecosystem brands, start with WPDS tokens + color-studio, then layer brand personality/accents + product-specific notes (e.g., ecomm focus for Woo, community for .org).
- **Agent-friendly docs**: Every addition references the fork management section in `AGENTS.md`. FUTURE_COREY.md points here.
- **Sources in the file**: Always credit internal (P2s, Slack, repos) + public.
- **Previews**: Required by CONTRIBUTING.md. Start minimal and iterate.
- **Sync safety**: Edits to root README (company index) may conflict with upstream "Sync README company index" commits — resolve in PRs. Personal subdirs are protected.
- **Workflow reminder** (from AGENTS.md):
  - Changes: `git checkout -b add/my-brand; ...; git push origin <branch>`
  - Updates from upstream: Merge the automated "chore: sync..." PR on GitHub, then `git pull`.
  - Manual trigger: GitHub Actions → "Sync with upstream" → Run workflow.
  - Explore: `git remote -v`, `git fetch upstream`, etc.

See the full "Managing the Fork & Upstream Syncs (First-timer / Agent Guide)" in `AGENTS.md` for commands.

## Next Steps / Polish Roadmap (Prioritized — Do These When You Have Time)

1. **Immediate Polish on These Additions (High Value, Low Effort)**
   - Open the Figma links from the wpbranddesign posts (search the P2 content for "figma.com/design").
   - Extract specific UI patterns (exact button radii/colors, card treatments, nav/footer visuals, icon styles) for each brand and add to the DESIGN.md "Component Stylings" sections + previews.
   - Enhance previews: Add more swatches (full semantic colors from the tokens), typography samples, multiple component examples (e.g., cards, forms, status indicators), and perhaps embed simple Tailwind or inline styles matching the tokens.
   - Add more "personality" flavor text from the taglines and alignment posts (e.g., "An AUTOMATTIC experiment" for WordPress.com tone).
   - For Jetpack/Woo/others: Pull more specific migration details from the linked Slack threads or GitHub PRs (e.g., exact legacy vs. new color mappings).

2. **Deeper Internal Research**
   - Use context-a8c again: `wpcom.posts-text` on more slugs from designomattic/wpbranddesign (or search for "design tokens" / "color" in those sites).
   - Slack: Targeted searches in #design-systems for each brand (e.g., "woocommerce design tokens").
   - GitHub: Browse more files in Automattic repos (calypso, jetpack) for any remaining brand-specific variables before full WPDS migration.
   - Linear: If you have access, look at the "Design System: Reimagined" project for specs.
   - mgs or fieldguide for any official internal style guides / brand books.

3. **Test & Validate the Fork Workflow with These**
   - Make a small test change to one (e.g., add a note in one DESIGN.md or tweak a preview).
   - Commit/push to a branch or main.
   - Manually trigger the sync Action on GitHub.
   - Observe the PR (should be clean since additions are in `personal/`).
   - Practice conflict resolution if any (edit the README index at the same time as a hypothetical upstream change).
   - Update `FUTURE_COREY.md` "Current State" or "Next Move" after any real work.

4. **Upstream & Sharing**
   - Open issues on the original `Khalidabdi1/design-ai` (use their design-md-request template) linking to these as starting points + the wpbranddesign P2s. Offer to contribute the files.
   - Consider whether to keep them "personal" forever or propose as official once polished.
   - If useful pattern, document in Sol/07-Systems/Conventions (e.g., a general "adding personal design systems" note).

5. **Repo Maintenance / Agent Polish**
   - Add a short section or link to *this* file in `FUTURE_COREY.md`, `CONTEXT.md`, `AGENTS.md`, and the root `README.md` (under the personal brands).
   - If previews grow, consider a `design-md/personal/shared-preview-helpers.css` or similar.
   - Periodically re-fetch the design-tokens.css (it’s autogenerated by Terrazzo) and color-studio for updates.
   - For future brands: Follow the same process (MCP research → WPDS + color-studio base → brand P2s for personality → `personal/` subdir → update index + this doc).

6. **Longer-Term Ideas**
   - Script or agent prompt to help generate future DESIGN.md from a brand's site + these tokens.
   - Visual verification: Use any design-review skills or screenshots against the Figma links.
   - Dark mode / RTL specifics if the brands have them.
   - Integrate with your other Sol projects (e.g., reference these in web-prototyping or other AI UI work).

## Quick Commands to Resume (Copy-Paste Ready)

```bash
cd ~/Sol/02-Projects/design-ai

# View this doc
cat RESEARCH-AUTOMATTIC-BRANDS.md

# View one of the additions
cat design-md/personal/automattic/DESIGN.md

# Check fork health
git remote -v
git status
git log --oneline -5

# Pull latest from your fork (after merging a sync PR on GitHub)
git pull

# To trigger a manual sync from GitHub UI (recommended): Actions tab → "Sync with upstream" → Run workflow

# Make a test change safely
git checkout -b polish/automattic-preview
# ... edit ...
git add .
git commit -m "Polish automattic preview"
git push origin polish/automattic-preview
# Then open PR on GitHub or merge to main
```

See `AGENTS.md` for the full first-timer guide (including conflict handling).

## Notes for Future Agents
When Corey says "come back to the Automattic brands research" or "polish the personal DESIGN.mds":
- Read this file first (after FUTURE_COREY.md).
- Read the specific brand's DESIGN.md + its sources section.
- Use context-a8c MCP again for fresh data (start by loading mgs/wpcom/slack/github).
- Prioritize the numbered next steps above.
- Always keep personal work in `design-md/personal/`.
- Update this doc + the brand DESIGN.mds + FUTURE_COREY.md when progress is made.

This should let you (or an agent) pick up exactly where we left off without re-researching everything.

---

*End of document. Feel free to edit/expand when you return.*
