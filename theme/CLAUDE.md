# Theme Customization Guide

## Custom Sections vs Default Shopify

This theme uses **custom `lh-` prefixed sections** that override the default Shopify Dawn sections. Always check for `lh-` versions first.

| Area | Custom File | Default File (NOT used) |
|------|-------------|------------------------|
| Header/Logo/Nav | `sections/lh-header.liquid` | `sections/header.liquid` |
| Announcement Bar | `sections/lh-announcement-bar.liquid` | built-in |
| Hero Slideshow | `sections/lh-hero-slideshow.liquid` | `sections/slideshow.liquid` |

**Key rule**: If CSS changes to `header.liquid` have no effect, you're editing the wrong file. The site renders `lh-header.liquid`.

## CSS Class Naming

All custom classes use the `lh-` prefix:

| Element | Class |
|---------|-------|
| Header wrapper | `.lh-header__wrapper` |
| Logo image | `.lh-header__logo-image` |
| Logo text fallback | `.lh-header__logo-text` |
| Icon buttons (search, account, cart) | `.lh-header__icon` |
| Nav bar | `.lh-nav` |
| Nav link | `.lh-nav__link` |
| Nav list container | `.lh-nav__list` |
| Nav item wrapper | `.lh-nav__item` |
| Announcement text | `.lh-announcement__text` |
| Hero text card | `.lh-hero__text` |
| Hero heading | `.lh-hero__heading` |
| Hero subheading | `.lh-hero__subheading` |
| Hero button | `.lh-hero__button` |

## Responsive Breakpoint Strategy

Sizes are kept small by default and scale up only at 1400px+ for large monitors. This ensures laptops (typically 1280-1440px) get compact sizing.

| Breakpoint | Target |
|------------|--------|
| Base (no media query) | Mobile |
| `min-width: 750px` | Tablet |
| `min-width: 990px` | Small laptop |
| `min-width: 1400px` | Large desktop |

## Quick Reference: Current Values

### Header (`lh-header.liquid`)

| Property | Base/Tablet | 1400px+ |
|----------|------------|---------|
| Wrapper padding | `0.5rem 1.5rem` | `1rem 2.5rem` |
| Logo height | `40px` / `45px` | `65px` |
| Icon size | `32px` | `32px` |
| Nav font-size | `0.8rem` / `0.85rem` | `0.85rem` |
| Nav list gap | `1rem` / `1.75rem` | `1.75rem` |

### Announcement Bar (`lh-announcement-bar.liquid`)

| Property | Base | 750px+ | 1400px+ |
|----------|------|--------|---------|
| Font-size | `0.6875rem` | `0.75rem` | `0.8125rem` |
| Padding | `0.5rem 1rem` | `0.5rem 1.25rem` | `0.625rem 1.5rem` |

### Hero Slideshow (`lh-hero-slideshow.liquid`)

| Property | Base | 750px+ | 1400px+ |
|----------|------|--------|---------|
| Card max-width | `90%` | `320px` | `400px` |
| Heading font-size | `1.5rem` | `1.5rem` | `2.25rem` |
| Subheading font-size | `0.75rem` | `0.75rem` | `0.9375rem` |
| Button font-size | `0.75rem` | `0.75rem` | `0.875rem` |

## Where NOT to Look

- `theme/assets/base.css` — Default Dawn styles. The `lh-` sections have their own inline `{%- style -%}` blocks that take priority.
- `theme/sections/header.liquid` — Default Dawn header. Not rendered on the storefront (replaced by `lh-header.liquid`).
- `theme/snippets/header-dropdown-menu.liquid` — Used by the default header, not by `lh-header`.

## Theme Settings

Logo width is set in Shopify admin (`settings.logo_width`), currently `90`. But the custom header ignores this and uses hardcoded `height` on `.lh-header__logo-image`.

Body font scale is `100` (16px base). All `rem` values are relative to this.
