# Automattic Design System

Automattic is the company behind WordPress.com, WooCommerce, Jetpack, Tumblr, and many other products that power the open web. Its design language emphasizes openness, simplicity, passion for the web, and a collaborative, diverse spirit. The visual identity is modern, clean, and accessible, with a strong focus on blue accents representing trust and technology, balanced with neutral grays and white space for clarity.

**Design Philosophy:** Make the web a better place. Designs should feel approachable, performant, inclusive, and true to open source values. "We don’t make software for free, we make it for freedom."

---

## 1. Visual Theme & Atmosphere

Clean, modern, optimistic, and human. Lots of white space, generous typography, subtle animations. Interfaces feel lightweight and focused on content and community. Brand expression is playful yet professional (see haiku on homepage). Products share a family resemblance but allow individual personality (e.g., Woo's commerce energy, Jetpack's reliability).

Density: Medium — comfortable reading and interaction without feeling sparse or cramped. Overall mood: trustworthy, creative, empowering.

---

## 2. Color Palette & Roles

Automattic products increasingly adopt the shared **WordPress Design System (WPDS)** tokens from `@wordpress/theme` / Gutenberg, with brand-specific accents from the official [@automattic/color-studio](https://github.com/Automattic/color-studio).

### Primary Brand Colors (from Color Studio + current WPDS adoption)

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Automattic Blue (legacy/primary accent) | `#24a3e0` | Links, accents on some properties |
| WordPress / Current Brand Blue | `#3858e9` | Primary interactive (buttons, links, focus) — WPDS `--wpds-color-bg-interactive-brand-strong` / `--wpds-color-fg-interactive-brand` |
| WooCommerce Purple | `#720eec` | Woo-specific primary |
| Jetpack Green | `#069e08` | Jetpack-specific primary |
| Success Green | `#008a20` / `#00a32a` | Positive states |
| Error Red | `#d63638` / `#cc1818` | Destructive, errors |
| Warning Orange/Yellow | `#b26200` / `#9d6e00` | Attention |
| Neutrals | Grays from #f6f7f7 (Gray 0) to #101517 (Gray 100) | Backgrounds, text, borders |

### Semantic Roles (WPDS aligned)

**Backgrounds (Light mode base):**
- Surface neutral: #fcfcfc
- Surface strong: #fff
- Surface weak: #f4f4f4
- Brand surface: #ecf0fa (light blue tint)

**Text:**
- Content neutral: #1e1e1e
- Content neutral weak: #707070
- Interactive brand: #3858e9

**Strokes/Borders:**
- Surface neutral: #dbdbdb
- Interactive brand: #3858e9

Dark mode uses inverted neutrals with the same accent tokens.

See full tokens in `packages/theme` of Gutenberg or the design-tokens.css for complete list (spacing `--wpds-dimension-*`, elevation, motion).

---

## 3. Typography Rules

System font stack for performance and familiarity:

```css
--wpds-typography-font-family-heading: -apple-system, system-ui, 'Segoe UI', Roboto, 'Oxygen-Sans', Ubuntu, 'Cantarell', 'Helvetica Neue', sans-serif;
--wpds-typography-font-family-body: same as heading;
--wpds-typography-font-family-mono: 'Menlo', 'Consolas', monaco, monospace;
```

### Type Scale (WPDS)

| Style | Size | Weight | Line Height | Notes |
|-------|------|--------|-------------|-------|
| Heading (large) | 32px / 2rem | 600 (medium) | 1.5 | Page titles |
| Heading medium | 20px | 600 | 1.625 | Section headers |
| Body | 16px / 1rem | 400 | 1.5 | Default reading |
| Body small | 14px / 0.875rem | 400 | 1.5 | Secondary text |
| Caption / small | 12px / 0.75rem | 400 | 1.625 | Labels, meta |
| Code | 13px | 400 | 1.5 | Monospace |

Font weights: Regular 400, Medium ~499-600 for emphasis.

---

## 4. Component Stylings

Adopting `@wordpress/ui` components and primitives from Gutenberg for consistency across Automattic products (Calypso, Jetpack, etc.).

**Buttons:**
- Primary (brand): Blue #3858e9 background, white text, rounded (md 4px or lg 8px per tokens).
- Secondary: Transparent or light gray, brand text on hover.
- States: Hover darkens brand blue to #2e49d9; focus ring uses --wpds-color-stroke-focus-brand.

**Cards / Surfaces:**
- Subtle elevation shadows from WPDS (xs to lg).
- Background white or surface-neutral.
- Border subtle gray.

**Inputs / Form elements:**
- Clean borders, focus ring in brand blue.
- Consistent padding from --wpds-dimension-padding-* (sm 8px, md 12px).

**Navigation / Headers:**
- Clean, often with Automattic signature "An AUTOMATTIC experiment" etc. in footers (per brand tone).

Legacy per-product components are being migrated to the shared system.

---

## 5. Layout Principles

Base unit: 4px (--wpds-dimension-base).

Spacing scale: 4px, 8px, 12px, 16px, 20px, 24px, 32px, 40px etc.

Generous whitespace. Content areas have max-widths for readability (e.g., 720px-960px for main content).

Grid: Flexible, often 12-col or CSS Grid/Flex with gap tokens.

Containers use surface widths from tokens (sm 320px etc for side panels).

---

## 6. Depth & Elevation

Uses layered shadows from WPDS:

- xs (tooltips, subtle): 0 1px 1px 0 #00000008, ...
- sm (snackbars): ...
- md (menus, command palette)
- lg (modals)

Surfaces stack with these elevations. No heavy drop shadows; subtle for modern feel.

---

## 7. Do's and Don'ts

**Do:**
- Use the shared WPDS tokens and @wordpress/ui components for new work.
- Prioritize accessibility (contrast, focus states).
- Allow brand personality while maintaining the Automattic family feel (unified "Automattic bar" in footers).
- Embrace open source aesthetic: clear, functional, joyful.

**Don't:**
- Introduce new one-off colors or components (migrate to tokens/ui).
- Overcrowd — respect whitespace.
- Ignore dark mode support.
- Use heavy corporate gradients or dated effects.

---

## 8. Responsive Behavior

Mobile-first. Breakpoints aligned with WP standards (often 782px, 960px+ for admin).

Touch targets min 44px.

On small screens: stack layouts, collapse menus, larger tap areas.

Icons scale appropriately; text remains readable.

---

## 9. Agent Prompt Guide

Use the Automattic / WPDS design language as source of truth.

Match:
- Primary interactive color: #3858e9 (brand blue) or product-specific (Woo purple, Jetpack green).
- Typography: System sans, clear hierarchy with medium weights on headings.
- Spacing: Multiples of 4px, generous padding (8-16px+).
- Elevation: Subtle layered shadows per WPDS.
- Components: Prefer modern @wordpress/ui patterns (clean buttons, cards with light borders/elevation).
- Overall: Clean, open, trustworthy, with blue (or brand) accents on white/ light gray backgrounds. Light and approachable, never heavy.

Example prompt snippet:
"Build this using Automattic's modern design language based on the WordPress Design System (WPDS). Use #3858e9 as the primary brand blue for interactive elements. Apply system fonts, 4px spacing base, subtle elevations, and clean components. Make it feel open-source friendly and professional."

For product-specific: Layer the accent (e.g., WooCommerce Purple #720eec for primary on Woo surfaces).

Reference the full token list from Gutenberg packages/theme for exact values.

---

*Sources: @automattic/color-studio, WordPress/gutenberg packages/theme (WPDS), internal Automattic design discussions (design-systems Slack, wpbranddesign P2 brand alignment work), public product sites.*
