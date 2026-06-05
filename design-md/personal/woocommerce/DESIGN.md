# WooCommerce Design System

WooCommerce is the open source eCommerce platform for WordPress. Design balances commerce functionality with the flexibility and beauty of WordPress. It feels powerful yet approachable for merchants of all sizes — from side hustles to enterprise stores. Purple accents (#720eec) bring energy and creativity to the reliable WP foundation. Focus on conversion, management, and delightful shopping experiences.

**Design Philosophy:** Sell anything, anywhere. Designs should make selling online joyful and effective. Extensible, customizable, and built on open web principles.

---

## 1. Visual Theme & Atmosphere

Energetic commerce with creative flair. Purple primary for brand (WooCommerce Purple), combined with clean neutrals and product imagery. Interfaces support complex admin tasks (orders, products, analytics) while feeling modern and not overwhelming. Increasing alignment with Automattic/WP design system for consistency.

Density: Task-oriented in admin; inspirational and conversion-focused on storefronts.

---

## 2. Color Palette & Roles

Woo-specific purple layered on shared WPDS.

### Key Colors (from Color Studio)

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| WooCommerce Purple (primary) | `#720eec` | CTAs, accents, brand elements |
| Purple variants | #873eff (40), #6108ce (60) etc. | Supporting states |
| Success Green | `#008a20` | Completed orders, positive |
| Neutrals | WPDS grays | Admin surfaces |

Semantic tokens follow WPDS for backgrounds, text, interactive states, with purple replacing or augmenting the brand blue in Woo contexts.

Storefronts often use merchant-chosen palettes on top of Woo's base styling.

---

## 3. Typography Rules

System sans for admin and core UI. Strong, clear hierarchy for product pages, carts, checkouts. Supports rich product descriptions.

Follows WPDS scale: readable body, prominent headings for product titles and sections.

---

## 4. Component Stylings

- Buttons: Purple primary for "Add to cart", "Buy now"; secondary for other actions.
- Product cards: Image-heavy, with price, ratings, quick add.
- Admin: Tables for orders/products, forms, dashboards with charts (adopting shared components).
- Checkout: Multi-step or one-page, clean and trustworthy.
- Storefront: Themeable, with Woo blocks and patterns.

Migrating admin UI elements to @wordpress/ui where appropriate.

---

## 5. Layout Principles

Admin: Sidebar navigation, main content areas for management tasks. Data tables prominent.

Storefront: Hero, featured products, categories, testimonials. Flexible for themes.

Spacing uses standard 4px+ scale. Conversion optimization drives layout decisions (clear CTAs, trust signals).

---

## 6. Depth & Elevation

Cards and modals use subtle elevation. Focus states and hovers provide feedback. Admin uses clean surfaces.

---

## 7. Do's and Don'ts

**Do:**
- Make commerce flows frictionless and delightful.
- Support heavy customization by merchants and developers.
- Use purple for brand moments, shared tokens for consistency.
- Prioritize accessibility and performance (critical for stores).

**Don't:**
- Overwhelm merchants with too many options at once.
- Use colors that clash with the purple brand.
- Neglect mobile shopping experiences.

---

## 8. Responsive Behavior

Fully responsive admin and storefronts. Cart and checkout optimized for mobile. Collapsible admin menus, touch-friendly product interactions.

---

## 9. Agent Prompt Guide

Capture eCommerce energy on the WordPress foundation.

- Primary: WooCommerce Purple #720eec for key commerce actions.
- Clean modern UI with WPDS tokens for admin tools.
- Typography: Clear, scannable for products and orders.
- Components: Strong product imagery, prominent CTAs, trustworthy forms.
- Overall: Professional yet creative commerce platform. Purple energy balanced with clean, reliable WordPress structure. Conversion-focused but human.

Prompt example:
"Build this WooCommerce feature using the Woo design language. Primary purple #720eec for buy/add-to-cart elements. Use the shared WP design system tokens for layout and components. Make admin tools efficient and storefronts beautiful and trustworthy. Emphasize clarity, speed, and merchant empowerment."

See brand alignment work for shared elements like the Automattic signature in footers ("An AUTOMATTIC thingamajig").

---

*Sources: color-studio (WooCommerce Purple), wpbranddesign P2 brand alignment, public woocommerce.com, ongoing WPDS adoption.*
