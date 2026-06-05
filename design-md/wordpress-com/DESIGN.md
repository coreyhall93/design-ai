# WordPress.com Design System

WordPress.com is the hosted platform for building websites, blogs, and online stores powered by WordPress. Its design emphasizes simplicity, creativity, community, and "your story, your way." The UI is approachable for non-technical users while powerful for pros. Clean layouts, prominent content, blue accents for trust and familiarity with the WordPress ecosystem.

**Design Philosophy:** Democratize publishing. Interfaces should feel empowering, beautiful without being distracting, and consistent with the open web values of WordPress.

---

## 1. Visual Theme & Atmosphere

Light, airy, content-first. Generous whitespace, beautiful typography for reading and writing. Blue (#3858e9 or legacy WordPress blue) accents for CTAs and navigation. Feels premium yet accessible. Modern evolution toward the shared Automattic/WP design system while retaining the friendly, creative spirit of WordPress.

Density: Comfortable — focused on long-form content and site building flows.

---

## 2. Color Palette & Roles

Adopts the shared WPDS tokens, with WordPress.com brand expression.

### Key Colors (Color Studio + WPDS)

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| WordPress Blue / Brand | `#3858e9` | Primary actions, links, focus (current system) |
| Legacy / Classic WP Blue | `#0073aa` or `#24a3e0` variants | Some surfaces, heritage elements |
| Success | `#008a20` | Published, success states |
| Neutrals | Full gray scale #f6f7f7 to #101517 | Backgrounds, text |

Semantic backgrounds, text, strokes follow WPDS (see Automattic DESIGN.md for full token reference).

Product-specific: Light editor/canvas backgrounds, dashboard grays.

---

## 3. Typography Rules

System sans-serif stack (same as WPDS/Automattic).

Headings use medium/semibold weights for hierarchy. Body for long reading. Strong support for rich text in the editor (Gutenberg-powered).

Scale similar to WPDS: 32px display down to 12px captions, with appropriate line-heights (1.5-1.625).

---

## 4. Component Stylings

Migrating to @wordpress/ui components.

**Buttons:** Brand blue primary, subtle secondary, with good hover/focus.

**Cards / Site Previews:** Clean previews with subtle shadows, hover lifts.

**Navigation:** Top bar with site selector, global nav evolving (per recent design work on global footer/nav alignment).

**Editor:** Block-based, full canvas focus, sidebar controls using design tokens.

**Forms:** Clean inputs with brand focus rings.

---

## 5. Layout Principles

Content-centric. Max widths for readability. Responsive from mobile (stacked) to wide desktop.

Uses 4px base spacing. Generous padding in editor and dashboards.

Global elements (header, footer) are being aligned across Dotcom brands (Automattic bar, etc.).

---

## 6. Depth & Elevation

Subtle elevations per WPDS for cards, popovers, modals. Light mode dominant with clean surfaces. Dark mode support increasing.

---

## 7. Do's and Don'ts

**Do:**
- Prioritize the writing/creation experience.
- Use the shared design tokens and components.
- Keep it human and joyful.
- Align with broader Automattic brand unification efforts (e.g., global nav/footer).

**Don't:**
- Over-design or use heavy effects that distract from content.
- Ignore mobile or accessibility.
- Introduce custom colors outside the palette.

---

## 8. Responsive Behavior

Mobile-first. Editor adapts (collapsible sidebars on small screens). Site previews responsive. Global elements (masterbar, footer) have mobile patterns (hamburger, etc.).

---

## 9. Agent Prompt Guide

Use WordPress.com design language: clean, content-first, empowering.

- Primary color: #3858e9 blue for actions/links.
- Typography: System fonts, excellent readability.
- Layout: Generous whitespace, focused on the user's content/site.
- Components: Modern, following WPDS / @wordpress/ui (clean buttons, cards, editor canvas).
- Overall feel: Approachable premium — like a beautiful, simple publishing tool. Light backgrounds, blue accents, subtle depth.

Prompt example:
"Design this feature for WordPress.com using the modern WP design system. Primary brand blue #3858e9. Clean system typography, generous 4px-based spacing, subtle elevations. Make the interface feel joyful, focused on creation, and consistent with Automattic products. Prioritize readability and simplicity."

Reference the global footer/nav alignment work for shared elements like the "An AUTOMATTIC experiment" signature and unified patterns.

---

*Sources: wpbranddesign P2 (global nav/footer brand alignment for Dotcom brands), Automattic color-studio, Gutenberg WPDS tokens, public WordPress.com site and editor.*
