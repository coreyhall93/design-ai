# Jetpack Design System

Jetpack is the essential plugin (and now suite of products) that brings security, performance, growth, and seamless WordPress.com integration to self-hosted WordPress sites. Design language communicates reliability, speed, and "set it and forget it" protection with a modern, approachable tech feel. Green accents (#069e08 or legacy #00a0d2) signal safety and growth. Heavy focus on admin dashboards, stats, and one-click features.

**Design Philosophy:** Jetpack makes WordPress better. Designs should feel secure, fast, and empowering — reducing complexity for site owners while providing powerful tools under the hood. Part of the Automattic family.

---

## 1. Visual Theme & Atmosphere

Professional, trustworthy, tech-forward. Clean dashboards with data visualizations (stats, security scans). Green for positive/success states. Increasing adoption of the shared WordPress Design System (WPDS) and @wordpress/ui components for consistency with Calypso and Gutenberg. Legacy `_inc` styles coexist during migration.

Density: Information-rich in admin (stats, lists, settings); focused CTAs for features.

---

## 2. Color Palette & Roles

Jetpack Green + migrating to WPDS.

### Key Colors (Color Studio + migration)

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Jetpack Green (primary/legacy) | `#069e08` | Accents, success, branding |
| Updated tokens | WPDS greens (#008a20 etc.) and neutrals | Current components |
| Info Blue | `#006bd7` | Informational states |
| Neutrals | Full WPDS gray scale | Backgrounds, text |

From migration work: Legacy `--jp-*` colors being replaced by `--wpds-*` tokens (e.g., neutral-weak #707070, success-weak #008030, etc.). Runtime design-tokens.css provides the source of truth.

See Slack/design-systems and Jetpack PRs for details on token adoption.

---

## 3. Typography Rules

System sans-serif. Clear data tables and settings use standard sizes. Headings for feature sections.

Aligning with WPDS scale during component migrations.

---

## 4. Component Stylings

- Admin UI: Cards for features (Protect, Boost, Stats), status indicators (green active, gray inactive), tables for logs/history.
- Buttons: Green or brand for primary actions (e.g., "Activate", "Upgrade").
- Status: Colored dots/labels (active green, error red, etc.) — migrating from internal Status component to Text + indicator + WPDS colors.
- Dashboards: Stats charts, quick actions.
- Connection/Onboarding: Clear flows with trust signals.

Legacy pages use older styles; modernized ones use @wordpress/ui + tokens.

---

## 5. Layout Principles

Admin pages with header, main content, side panels or tabs. Data-heavy: tables, lists, graphs.

Uses standard spacing tokens. Feature cards in grids.

Global Jetpack header and navigation.

---

## 6. Depth & Elevation

Subtle for cards and popovers. Focus on clarity for security/performance data.

---

## 7. Do's and Don'ts

**Do:**
- Emphasize security, speed, and growth benefits.
- Migrate to shared WPDS tokens and @wordpress/ui for new work (see admin-ui and componentry PRs).
- Provide clear status and actionable insights.
- Support both simple and advanced users.

**Don't:**
- Use outdated per-package token copies (version skew risk).
- Leave legacy `_inc` styles without plan for migration.
- Overwhelm with too many settings at once.

---

## 8. Responsive Behavior

Admin responsive (collapses on mobile). Stats and dashboards usable on tablets/phones. Onboarding flows mobile-friendly.

---

## 9. Agent Prompt Guide

Reliable, protective, modern WordPress companion.

- Primary accent: Jetpack Green (#069e08 legacy or WPDS greens) for success/protection states.
- Clean data-focused admin UI using shared design tokens (avoid legacy hex fallbacks where possible).
- Typography: Readable for stats and settings.
- Components: Status indicators, feature cards, upgrade CTAs. Prefer @wordpress/ui patterns.
- Overall: Trustworthy tech tool. Green for "protected and fast." Clean, professional, with data visualizations. Part of the Automattic/WP family.

Prompt example:
"Design this Jetpack feature screen using the current design system. Use Jetpack Green for positive states and shared WPDS tokens (--wpds-*) for everything else. Clean admin layout with status indicators, cards, and clear actions. Make it feel secure, performant, and easy to manage. Reference the runtime design tokens stylesheet."

See internal Jetpack issues on admin-ui and design token adoption for latest patterns. Brand alignment includes the "An AUTOMATTIC airline" tone in some contexts.

---

*Sources: Automattic/color-studio (Jetpack Green), extensive internal Slack #design-systems and #jetpack-r2d2 discussions on WPDS migration, Gutenberg @wordpress/theme design-tokens, public jetpack.com.*
