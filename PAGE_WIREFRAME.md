# Linens & Hutch Homepage - Visual Wireframe & Layout Guide

> **Purpose:** Visual reference for page layout, section ordering, and responsive behavior
> **Format:** ASCII wireframes + responsive breakpoint guide
> **Use for:** Planning Shopify section assembly and layout decisions

---

## Page Layout (Scrolling Top-to-Bottom)

```
┌────────────────────────────────────────────────────────────┐
│                   ANNOUNCEMENT BAR                          │
│          FREE SHIPPING & RETURNS | 101-NIGHT GUARANTEE      │
├────────────────────────────────────────────────────────────┤
│                      HEADER (STICKY)                         │
│  Logo | Nav Menu | Search | Cart | Account                  │
├────────────────────────────────────────────────────────────┤
│                                                              │
│                   HERO SLIDESHOW (5 SLIDES)                 │
│              [LARGE HERO IMAGE WITH TEXT OVERLAY]           │
│                    Heading: SILK PILLOWCASES                │
│                    CTA Button: SHOP NOW >                   │
│              Prev | Slide Counter (1/5) | Next              │
│                                                              │
├────────────────────────────────────────────────────────────┤
│         SHOP BY CATEGORY (3-COL GRID CAROUSEL)              │
│          Heading: SHOP BY CATEGORY                          │
│    [Card 1]    [Card 2]    [Card 3]  [Card 4 Peek]         │
│   Sheets     Comforters   Duvet     Quilts...              │
├────────────────────────────────────────────────────────────┤
│                    OUR COMMITMENT (RICH TEXT)               │
│            [DARK GRADIENT BACKGROUND]                       │
│           Heading: OUR COMMITMENT TO YOU                    │
│                                                              │
├────────────────────────────────────────────────────────────┤
│          BENEFITS / FEATURES (3-COL MULTICOLUMN)            │
│                    [DARK GRADIENT]                          │
│     [Benefit 1]    [Benefit 2]    [Benefit 3]              │
│     101-NIGHT     FREE SHIPPING  FREE RETURNS              │
│                                                              │
├────────────────────────────────────────────────────────────┤
│        FEATURED COLLECTION - "JUST IN" (3-COL SLIDER)       │
│              Heading: JUST IN                               │
│    [Product 1]  [Product 2]  [Product 3]  [Product 4]      │
│   [Image 1x1]  [Image 1x1] [Image 1x1]  [Peek]            │
│                                                              │
├────────────────────────────────────────────────────────────┤
│              IMAGE WITH TEXT - THROW PILLOWS                │
│   [Image 1x1]  |  Heading: ELEVATE YOUR SPACE...          │
│                |  Body: Style meets comfort...             │
│                |  Button: SHOP NOW >                        │
│                                                              │
├────────────────────────────────────────────────────────────┤
│       FEATURED COLLECTION - "BEST SELLERS" (3-COL SLIDER)   │
│    [Product 1]  [Product 2]  [Product 3]  [Product 4]      │
│                                                              │
├────────────────────────────────────────────────────────────┤
│              IMAGE WITH TEXT - [SECOND INSTANCE]            │
│              Heading: [Content varies]                      │
│           [Layout: Image Right, Text Left]                  │
│                                                              │
├────────────────────────────────────────────────────────────┤
│       FEATURED COLLECTION - [THIRD INSTANCE] (3-COL)        │
│              Heading: [Collection name]                     │
│    [Product 1]  [Product 2]  [Product 3]                    │
│                                                              │
├────────────────────────────────────────────────────────────┤
│                   INSTAGRAM FEED SECTION                    │
│              Background: Light warm gray (#E5E5DF)          │
│         Heading: #LINENSANDHUTCH                            │
│         [INSTAGRAM FEED GRID - 4-6 POSTS]                  │
│         CTA: LINENS & HUTCH INSTAGRAM > @linensandhutch    │
│                                                              │
├────────────────────────────────────────────────────────────┤
│                       FOOTER                                │
│                  (Dark Gradient Background)                 │
│  ABOUT       CONTACT      NEWSLETTER      FOLLOW US         │
│  ----        -------      ----------      ---------         │
│  • Our Story • Contact    [Email Form]    • Facebook       │
│  • Reviews   • FAQ        [Klaviyo App]   • Instagram      │
│  • Blog      • Returns    Signup→         • TikTok        │
│  • Affiliates• Mobile T.  [Button]        • Twitter       │
│  • E-Gifts   • Privacy    [Success Msg]   • Pinterest      │
└────────────────────────────────────────────────────────────┘
```

---

## Responsive Breakpoints & Layout Changes

### Desktop (≥ 1200px)
- 3-column grids
- 2-column image-with-text (side-by-side)
- Full-width hero
- 4-column footer
- Maximum width: 1200px (page-width container)

### Tablet (750px - 1199px)
- 2-column grids
- Image-with-text stacked or side-by-side
- Slider with fewer visible products
- 2-column footer

### Mobile (< 750px)
- 1-column layout throughout
- Full-width sections with gutters
- Carousel for multi-item sections
- Stacked image-with-text
- 1-column footer

---

## Section Component Hierarchy

```
1. Announcement Bar
2. Header (Navigation)
3. Hero Slideshow (5 slides)
4. Shop by Category (24 items carousel)
5. Our Commitment (Rich Text)
6. Benefits Multicolumn (3 features)
7. Featured Collection - "Just In"
8. Image with Text - Throw Pillows
9. Featured Collection - "Best Sellers"
10. Image with Text - Second Instance
11. Featured Collection - Third Instance
12. Rich Text - Final CTA
13. Instagram Feed (App Block)
14. Footer
```

---

## Color Scheme Visual Distribution

```
Color Scheme 1 (Neutral/White):
├─ Hero Slideshow
├─ Shop by Category
├─ Featured Collections
└─ General spacing

Color Scheme 2 (Secondary Brand):
├─ Image with Text sections
└─ Some CTAs/accents

Color Scheme 3 (Dark Gradient):
├─ Announcement Bar
├─ Our Commitment
├─ Benefits
├─ Final Rich Text
└─ Footer
```

---

## Section Spacing & Padding

| Section | Top Padding | Bottom Padding |
|---------|-----------|---------------|
| Hero Slideshow | 0px | 60px |
| Shop by Category | 60px | 60px |
| Our Commitment | 75px (m), 100px (d) | 75px (m), 100px (d) |
| Benefits | 60px | 60px |
| Featured Collections | 60px | 60px |
| Image with Text | 60px | 60px |
| Instagram Feed | 60px | 100px |
| Footer | 36px (m), 48px (d) | 36px (m), 48px (d) |

---

## Card Aspect Ratios

| Card Type | Ratio | Used In |
|-----------|-------|---------|
| Category Card | Varies (~4:3) | Shop by Category |
| Product Card | 1:1 (100%) | Featured Collections |
| Image with Text | 1:1 (square) | Image with Text sections |
| Hero Slide | Full-width responsive | Hero Slideshow |

---

## Navigation & Interaction Points

```
Top Navigation:
├─ Logo (click → home)
├─ Menu Items (expandable)
├─ Search (click → overlay)
├─ Cart (click → drawer)
└─ Account (click → menu)

Hero Slideshow Controls:
├─ Previous button
├─ Slide counter (1/5)
├─ Next button
├─ Autoplay toggle

Category Carousel:
├─ Left/Right nav arrows
├─ Drag/swipe navigation

Featured Collection Sliders:
├─ Left/Right nav arrows
├─ Variant selection on hover

Footer Links:
├─ Column headings
├─ Navigation links
├─ Social icons
└─ Newsletter form
```

---

## Animation & Scroll Behavior

| Section | Animation | Trigger |
|---------|-----------|---------|
| Hero | fade-in | on load |
| Shop by Category | slide-in | scroll into view |
| Benefits | cascade | scroll into view |
| Featured Collections | slide-in | scroll into view |
| Image with Text | slide-in | scroll into view |
| Instagram Feed | slide-in | scroll into view |
| Footer | cascade + slide | scroll into view |

---

## Design System Colors

- **Primary CTA:** Emerald green
- **Secondary:** Blue for links
- **Tertiary:** Purple for emphasis
- **Neutral:** Gray scale
- **Dark:** Dark gray/charcoal for text

---

## Typography

- **Font Family:** Inter
- **Headlines:** Bold, increased size at desktop
- **Body:** Regular weight, standard line-height
- **Links:** Colored or underlined

---

## Responsive Image Sizing

### Hero Slideshow
```
Widths: 375, 550, 750, 1100, 1500, 1780, 2000, 3000, 3840
Mobile (≤750px): 550-750px
Tablet (751-1199px): 1100px
Desktop (≥1200px): 1500px+
```

### Product Card Images
```
Dynamic width calculation based on grid columns
Widths: 165 - 3000px range
```

---

## Performance Considerations

### Image Loading Priority
```
Hero: fetchpriority=high (eager)
Products: fetchpriority=auto (lazy)
Instagram: fetchpriority=low (lazy)
Footer: defer (load after content)
```

---

## Mobile Menu Structure

```
Mobile Header:
├─ Logo (center)
├─ Menu toggle (left)
└─ Search + Cart (right)

Mobile Menu (slide-in):
├─ Main menu items (expandable)
├─ Account link
├─ Search
└─ Close button
```

---

## Breakpoint-Specific Behaviors

### < 750px (Mobile)
- Full-width sections with gutters (12-16px)
- Single column grids
- Carousel for multi-item sections
- Stacked layouts
- Mobile navigation drawer

### 750px - 1199px (Tablet)
- 2-column grids
- Wider gutters (20-32px)
- Mixed layouts
- Touch-friendly targets (44px+)

### ≥ 1200px (Desktop)
- 3-column grids
- Side-by-side layouts
- Full-width sliders
- Maximum container: 1200px
- Centered layout with equal margins
