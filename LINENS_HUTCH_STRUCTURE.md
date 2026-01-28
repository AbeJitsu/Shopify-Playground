# Linens & Hutch Homepage - Shopify Liquid Structure

> **Source HTML:** `theme/linens-and-hutch-homepage.html`
> **Purpose:** Complete structural reference for converting to Shopify Liquid sections
> **Last Updated:** 2026-01-28

---

## Table of Contents

1. [Announcement Bar](#1-announcement-bar)
2. [Hero Slideshow](#2-hero-slideshow)
3. [Shop by Category Grid](#3-shop-by-category-grid)
4. [Our Commitment Section](#4-our-commitment-section)
5. [Benefits Multicolumn](#5-benefits-multicolumn)
6. [Featured Collection - Just In](#6-featured-collection---just-in)
7. [Image with Text - Throw Pillows](#7-image-with-text---throw-pillows)
8. [Featured Collection - Best Sellers](#8-featured-collection---best-sellers)
9. [Image with Text - Second Instance](#9-image-with-text---second-instance)
10. [Featured Collection - Third Instance](#10-featured-collection---third-instance)
11. [Final Rich Text](#11-final-rich-text)
12. [Instagram Feed](#12-instagram-feed)
13. [Footer](#13-footer)

---

## 1. Announcement Bar

**Shopify Section ID:** `sections--15585542537298__announcement-bar`
**Section Type:** Announcement Bar / Slideshow
**Position:** Top of page (part of header group)

### Content
```
FREE SHIPPING & RETURNS | 101-NIGHT GUARANTEE
```

### Structure Notes
- Single message bar format
- Color scheme 3 (dark gradient background)
- Utility announcement style
- Appears before main header

### Styling
- Full-width banner
- Dark background with white text
- Part of sticky header functionality

---

## 2. Hero Slideshow

**Shopify Section ID:** `template--15585548304466__slideshow_UfqBhQ`
**Section Type:** Image Banner / Slideshow
**Component Type:** 5-slide carousel

### Slide Details

| Slide | Heading | Subheading | CTA Button | Desktop Image | Mobile Image | Link Target |
|-------|---------|-----------|-----------|---------------|-------------|-------------|
| 1 | SILK PILLOWCASES | LUXURIOUSLY SMOOTH FOR EFFORTLESS BEAUTY REST | SHOP NOW > | V2_1.jpg | SILK-M.jpg | /products/mulberry-silk-pillowcase |
| 2 | SOFT, BREATHABLE BAMBOO SHEETS | FOR A COOLER SLEEP | SHOP NOW > | BAMBOO-D1.jpg | BAMBOO-M1.jpg | /collections/bamboo-sheets |
| 3 | BRING HOME COTTON LUXURY | (none) | SHOP THE COLLECTION > | COTTON-DT.jpg | COTTON-M.jpg | /collections/textured-comforters |
| 4 | LAYER YOUR BED IN TEXTURE | (none) | SHOP THE COLLECTION > | TEXT-DT.jpg | TEXT-M.jpg | /collections/textured-comforters |
| 5 | TOWELS MADE FOR EVERYDAY LUXURY | SOFT, ABSORBENT, AND TIMELESS | SHOP NOW > | TOWEL2.jpg | TOWEL1.jpg | /collections/bath |

### Image URLs (Base Path)
```
https://www.linensandhutch.com/cdn/shop/files/
```

**Full Desktop Images:**
- `V2_1.jpg?v=1754313774&width=3840`
- `BAMBOO-D1.jpg`
- `COTTON-DT.jpg`
- `TEXT-DT.jpg`
- `TOWEL2.jpg`

**Full Mobile Images:**
- `SILK-M.jpg?v=1747339421&width=750`
- `BAMBOO-M1.jpg`
- `COTTON-M.jpg`
- `TEXT-M.jpg`
- `TOWEL1.jpg`

### Structure
```
<slideshow-component>
  ├─ Controls (top)
  │  ├─ Previous button
  │  ├─ Slide counter (1 / 5)
  │  ├─ Next button
  │  └─ Autoplay toggle
  └─ Slide grid
     └─ [5x] Slideshow slide
        ├─ Media (picture → source + img)
        └─ Text wrapper
           ├─ h2 heading
           ├─ Body text (optional)
           └─ CTA button
```

### Styling Notes
- **Layout:** Full-width with centered content
- **Text Position:** Middle-left (desktop) / Middle-center (mobile)
- **Autoplay:** 5-second interval
- **Responsive:** Picture element with srcset for mobile/desktop
- **Animations:** Fade-in on entry

### Typography
- Heading: h1/h2 size (40px desktop, 24px mobile)
- Subheading: Bold body text
- Button: Primary CTA style

### Liquid Conversion Pattern
```liquid
{% section 'hero-slider' %}
  {% for slide in slides %}
    {%- assign slide_content = slide -%}
    {%- assign slide_image = slide.image -%}
    {%- assign slide_mobile_image = slide.mobile_image -%}
  {% endfor %}
{% endsection %}
```

---

## 3. Shop by Category Grid

**Shopify Section ID:** `template--15585548304466__shop_by_category_GbzkjX`
**Section Type:** Collection List / Category Grid
**Grid Layout:** 3-column (desktop), 2-column (tablet), 1-column (mobile)

### Header
- **Heading:** "SHOP BY CATEGORY"
- **Subheading:** "Everything you need to build your bedroom sanctuary."

### Category Cards (Sample Data)

| Position | Title | Link | Image | Description |
|----------|-------|------|-------|-------------|
| 1 | Sheets | /collections/sheets | 1KLH-4PC-WHITE-HERO-C5.jpg | "Match Your Sleep Style: The Importance of Choosing the Right Bed sheets..." |
| 2 | Comforters | /collections/comforters | 1KLH-COMF-TEX-WHITE-C5A_e1f77383-2697-44d7-8d6a-0909bd2b73c2.jpg | "Discover the Versatile Comfort of..." |
| 3-24 | [Additional 22 categories] | [Collection links] | [Category images] | [Descriptions] |

### Image Base Path
```
https://www.linensandhutch.com/cdn/shop/collections/
```

### Structure
```
<div class="collection-list-wrapper">
  ├─ Title wrapper
  │  ├─ h2 heading
  │  └─ p description
  └─ Slider component
     └─ [24x] Product/category card
        ├─ Media (image)
        └─ Content
           ├─ Card heading
           └─ Card description
```

### Styling
- **Component:** Slider with mobile gutter
- **Color Scheme:** 1 (neutral background)
- **Cards:** Gradient backgrounds, full-width layout
- **Hover Effects:** Product hover state styling

### Liquid Notes
- Use collection objects for automatic linking
- Image handling with Shopify image filter
- Consider pagination or lazy loading for 24 items

---

## 4. Our Commitment Section

**Shopify Section ID:** `template--15585548304466__rich_text_KNVTXE`
**Section Type:** Rich Text

### Content
```
Heading: OUR COMMITMENT TO YOU

Body: At Linens & Hutch, our mission is to provide you with
the highest quality bedding products at unbeatable prices.
We back our products with a 100% money-back guarantee.
If you're not completely satisfied with your purchase,
our dedicated customer support team is here to ensure
your satisfaction.
```

### Structure
```
<div class="rich-text content-container">
  ├─ h2 heading
  └─ rte content (paragraph)
```

### Styling
- **Full-width:** Yes
- **Text align:** Center
- **Color Scheme:** 3 (dark gradient background)
- **Text Color:** White (#ffffff)
- **Padding:** 75px (mobile), 100px (desktop) top/bottom

### Liquid Notes
- Simple HTML/text section
- Use Shopify's RTE editor for content management
- Background gradient handled by color scheme

---

## 5. Benefits Multicolumn

**Shopify Section ID:** `template--15585548304466__multicolumn_4xTabf`
**Section Type:** Multicolumn / Feature Grid
**Layout:** 3-column (desktop), 1-column (mobile), slider component

### Benefit Cards

| Column | Icon | Title | CTA Link |
|--------|------|-------|----------|
| 1 | Arrow icon | 101-NIGHT GUARANTEE | /policies/refund-policy |
| 2 | Arrow icon | FREE SHIPPING | /policies/shipping-policy |
| 3 | Arrow icon | FREE RETURNS | /pages/returns-exchanges |

### Structure
```
<div class="multicolumn-card">
  └─ [3x] Column block
     ├─ Icon SVG
     ├─ Heading
     ├─ Body text (optional)
     └─ Link with arrow
```

### Styling
- **Grid:** 3 columns, centered content
- **Color Scheme:** 3 (dark background)
- **Text Color:** White
- **Animations:** Slide-in with scroll trigger
- **Icons:** SVG arrows, inline with text

### Icon Details
- Arrow icon appears to be right-aligned in links
- SVG embedded in HTML (reuse same SVG for all three)

### Liquid Notes
- Could be hardcoded benefits or dynamic blocks
- Consider making benefits editable in theme customizer
- Animation classes can be Shopify animations

---

## 6. Featured Collection - Just In

**Shopify Section ID:** `template--15585548304466__featured_collection`
**Section Type:** Featured Collection (Product Slider)
**Layout:** 3-column (desktop), 1-column (mobile), slider with peek

### Header
- **Heading:** "JUST IN"
- **Subheading:** "Discover new arrivals designed to bring style and warmth to every space"

### Sample Product: Cloud Weave Textured Comforter Set - Dune

**Main Image:**
```
1KLH-COMF-TCW-DUNE-02-C5-GRAPHIC_8664e7f4-82f0-4828-b480-7a01fb67e642.jpg
```

**Base Path:**
```
https://www.linensandhutch.com/cdn/shop/files/
```

**Variant Images (Color Options):**
- Dune
- Tan
- Olive

**Product Link:** `/products/cloud-weave-textured-comforter-set`

### Structure
```
<div class="collection">
  ├─ Title wrapper
  │  ├─ h2 heading
  │  └─ p description
  └─ Slider component
     ├─ [3x visible] Product cards
     │  ├─ Card media
     │  │  └─ Picture (responsive image)
     │  └─ Card content
     │     ├─ Product title
     │     ├─ Price (from product object)
     │     └─ Quick shop / variant selectors
     └─ Navigation (peek next product)
```

### Styling
- **Card Ratio:** 100% (square cards)
- **Color Scheme:** 1 (neutral)
- **Hover Effects:** Product card hover state
- **Image Ratio:** `--ratio-percent: 100%`

### Liquid Notes
- Use `{{ collection.products }}` for dynamic product listing
- Implement variant image swatches on hover
- Add to cart functionality via quick shop or cart drawer
- Lazy load product images

---

## 7. Image with Text - Throw Pillows

**Shopify Section ID:** `template--15585548304466__image_with_text_CPg4N4`
**Section Type:** Image with Text (Two-column layout)

### Content
```
Heading: ELEVATE YOUR SPACE WITH LUXE THROW PILLOWS

Body: Style meets comfort—explore our collection of plush,
decorative pillows that add the perfect finishing touch
to any room

CTA: SHOP NOW > → /collections/throw-pillows-blankets
```

### Image
```
COLLECTION-158-1x1_ff16c571-0acd-4838-a6f4-670df9f4d4a1.jpg
```

**Base Path:**
```
https://www.linensandhutch.com/cdn/shop/files/
```

**Image Ratio:** 99.98% (nearly square/1:1)

### Structure
```
<div class="image-with-text">
  ├─ [Column 1] Media
  │  └─ Picture (responsive image)
  └─ [Column 2] Content
     ├─ h2 heading
     ├─ rte body
     └─ Button link
```

### Layout Details
- **Grid:** 2-column (tablet/desktop), 1-column (mobile)
- **Image Position:** Left (desktop), top (mobile)
- **Text Alignment:** Middle (vertically centered)
- **Image Aspect Ratio:** 1:1 (square)

### Styling
- **Full-width:** Yes
- **Color Scheme:** 2 (secondary brand color background)
- **Gradient:** Applied
- **Padding:** Standard section padding

### Liquid Notes
- Use Shopify's native image-with-text section as reference
- Make image and CTA configurable
- Support both "Image Left" and "Image Right" layouts

---

## 8. Featured Collection - Best Sellers

**Shopify Section ID:** `template--15585548304466__6a65d575-4b31-4910-b3f4-d4da2b5cf9b9`
**Section Type:** Featured Collection (Product Slider)
**Layout:** 3-column (desktop), 1-column (mobile)

### Header
- **Heading:** "EXPERIENCE OUR BEST SELLERS"
- **Subheading:** "Make your room a restful oasis with our most loved bedding"

### Sample Product: Luxury Gel Pillow
```
Title: Luxury Gel Pillow / Plush Down-Alternative Gel-Fiber Pillow (2-Pack)

Image: linens-and-hutch-pillows-queen-plush-down-alternative-gel-fiber-pillow-2-pack-31128120066130.png

Link: /products/luxury-gel-pillow

Image Ratio: 100% (square)
```

### Image Base Path
```
https://www.linensandhutch.com/cdn/shop/files/
```

### Structure
```
Same as Featured Collection #6 (see section 6)
- Slider component
- Product cards with images
- Variant handling
- Navigation
```

### Styling
- **Card Ratio:** 100% (square)
- **Color Scheme:** 1 (neutral)
- **Center-aligned:** Yes
- **Responsive grid:** 3-col desktop, 1-col mobile

### Liquid Notes
- Reuse featured collection component from section 6
- Make collection configurable via theme customizer
- Support product variant selection

---

## 9. Image with Text - Second Instance

**Shopify Section ID:** `template--15585548304466__4929c0e8-8828-40f5-905e-80055d38b3a3`
**Section Type:** Image with Text

### Details
- Similar structure to section 7
- **Color Scheme:** 2 or variant
- **Layout:** 2-column grid
- **Image:** [Specific image TBD from HTML extract]

### Notes
- Use same component as section 7
- Different image and content
- Likely positioned image-right layout

---

## 10. Featured Collection - Third Instance

**Shopify Section ID:** `template--15585548304466__featured_collection_zbwyXB`
**Section Type:** Featured Collection (Product Slider)

### Details
- **Layout:** 3-column (desktop), 1-column (mobile)
- **Color Scheme:** 1 (neutral)
- **Center-aligned:** Yes
- **Slider component:** Peek navigation

### Notes
- Reuse featured collection component
- Different collection than sections 6 & 8
- Maintain consistent product card styling

---

## 11. Final Rich Text Section

**Shopify Section ID:** `template--15585548304466__rich_text_eQWDgW`
**Section Type:** Rich Text

### Details
- Similar to section 4
- **Color Scheme:** 2 or variant
- **Full-width:** Yes
- **Content:** [Specific content TBD from HTML extract]

### Styling
- Center-aligned text
- Gradient background option
- Standard padding

---

## 12. Instagram Feed

**Shopify Section ID:** `template--15585548304466__1692200686a6c7012a`
**Block Type:** App Block (Instafeed)
**App Block ID:** `shopify-block-AY2xDVUF4bEVCSGh3M__instafeed_app_block_84zj7t`

### Structure
```html
<div class="scroll-trigger animate--slide-in">
  <div id="shopify-block-AY2xDVUF4bEVCSGh3M__instafeed_app_block_84zj7t"
       class="shopify-block shopify-app-block">
    <div id="insta-feed"></div>
  </div>
</div>
```

### Styling
- **Background Color:** #E5E5DF (warm light gray)
- **Padding Bottom:** 100px
- **Text Align:** Center
- **Text Color:** #e5e5df

### Functionality
- Dynamically populated by Instafeed app
- Requires app script injection
- Shows Instagram posts/feed

### Liquid Notes
- Use `{% section 'apps' %}` or `{% section 'instagram-feed' %}`
- Requires Instafeed app to be installed
- JavaScript handles feed population
- Custom styling for container div

---

## 13. Footer

**Shopify Section ID:** `sections--15585542471762__footer`
**Section Type:** Footer

### Structure

#### Column 1: About
```
Heading: ABOUT
Links:
  - Our Story
  - Reviews
  - Blog
  - Affiliates
  - E-Gift Cards
```

#### Column 2: Contact
```
Heading: CONTACT
Links:
  - Contact
  - FAQ
  - Returns & Exchanges
  - Mobile Terms
  - Your Privacy Choices
```

#### Column 3: Newsletter
```
App Block (Klaviyo Email Form)
- Email input
- Subscribe button
```

#### Column 4: Follow Us
```
Heading: FOLLOW US
Social Links:
  - Facebook: https://www.facebook.com/LinensandHutch
  - Instagram: https://www.instagram.com/linensandhutch
  - TikTok: https://www.tiktok.com/@linensandhutch
  - X/Twitter: https://twitter.com/linensandhutch
  - Pinterest: https://www.pinterest.com/linensandhutch
```

### Footer HTML Structure
```
<footer class="footer color-scheme-3 gradient">
  ├─ Footer content top (page-width)
  │  └─ [4x] Footer block
  │     ├─ Menu heading (h2)
  │     └─ Link list or form
  └─ Footer content bottom
     ├─ Copyright notice
     ├─ Policy links
     └─ Payment icons
```

### Styling
- **Color Scheme:** 3 (dark gradient background)
- **Text Color:** White
- **Padding:** 36px top/bottom (mobile), 48px top/bottom (desktop)
- **Grid:** 1-col (mobile), 2-col (tablet), 4-col (desktop)

### Footer Layout Responsive
| Breakpoint | Layout |
|------------|--------|
| Mobile | 1 column (stacked) |
| Tablet | 2 columns |
| Desktop | 4 columns |

### Animations
- `data-cascade` on blocks with staggered entrance
- `animate--slide-in` on footer sections

### Liquid Notes
- Use `{{ section.settings.footer_content }}` for menu blocks
- Implement Klaviyo form via app block
- Social icons can be SVG or icon font
- Copyright year auto-updates: `&copy; {{ "now" | date: "%Y" }}`

---

## Reusable Components Summary

### 1. **Slideshow/Carousel Component**
Used in:
- Hero section (main slider)
- Announcement bar
- Featured collections (slider with peek)
- Shop by category (carousel)

**Key Props:**
- `slides: array`
- `autoplay: boolean`
- `autoplay_speed: number (seconds)`
- `controls_position: string`
- `show_counter: boolean`

### 2. **Featured Collection Component**
Used in: Sections 6, 8, 10

**Key Props:**
- `collection: collection`
- `product_cards_per_row: number (3)`
- `rows_per_section: number`
- `product_limit: number`
- `show_description: boolean`

### 3. **Image with Text Component**
Used in: Sections 7, 9

**Key Props:**
- `image: image`
- `heading: string`
- `body: richtext`
- `button_text: string`
- `button_link: url`
- `image_position: left|right`

### 4. **Multicolumn Component**
Used in: Section 5 (benefits)

**Key Props:**
- `columns: array`
- `column_alignment: center|start|end`
- `columns_per_row: number (3)`

### 5. **Rich Text Component**
Used in: Sections 4, 11

**Key Props:**
- `heading: string`
- `body: richtext`
- `color_scheme: number`
- `alignment: center|left|right`

### 6. **App Block Container**
Used in: Instagram Feed, Footer Newsletter

**Types:**
- Instafeed app block
- Klaviyo email form

---

## Image Asset Inventory

### Hero Slideshow Images

| Purpose | Desktop Image | Mobile Image | Dimensions |
|---------|--------------|-------------|-----------|
| Slide 1: Silk Pillowcases | V2_1.jpg | SILK-M.jpg | Desktop: 3840px wide |
| Slide 2: Bamboo Sheets | BAMBOO-D1.jpg | BAMBOO-M1.jpg | TBD |
| Slide 3: Cotton Luxury | COTTON-DT.jpg | COTTON-M.jpg | TBD |
| Slide 4: Textured Bed | TEXT-DT.jpg | TEXT-M.jpg | TBD |
| Slide 5: Towels | TOWEL2.jpg | TOWEL1.jpg | TBD |

### Collection Images

| Collection | Primary Image | Base Path |
|-----------|--------------|-----------|
| Sheets | 1KLH-4PC-WHITE-HERO-C5.jpg | `/cdn/shop/collections/` |
| Comforters | 1KLH-COMF-TEX-WHITE-C5A_*.jpg | `/cdn/shop/collections/` |
| [Additional 22 categories] | [Various] | `/cdn/shop/collections/` |

### Featured Collection Images

| Collection | Sample Image | Path |
|-----------|------------|------|
| Just In | 1KLH-COMF-TCW-DUNE-02-C5-GRAPHIC_*.jpg | `/cdn/shop/files/` |
| Pillows | linens-and-hutch-pillows-queen-plush-down-alternative-*.png | `/cdn/shop/files/` |

### Image with Text Images

| Section | Image | Ratio |
|---------|-------|-------|
| Throw Pillows | COLLECTION-158-1x1_*.jpg | 1:1 (100%) |
| [Second Instance] | [TBD] | [TBD] |

---

## Color Schemes Reference

| Scheme | Name | Background | Text | Usage |
|--------|------|-----------|------|-------|
| 1 | Neutral | Light/White | Dark gray | Featured collections, shop grid |
| 2 | Secondary | Brand color | White | Image with text sections |
| 3 | Dark | Dark gradient | White | Footer, announcement bar, commitment |

---

## Responsive Breakpoints

| Breakpoint | Width | Layout Changes |
|-----------|-------|-----------------|
| Mobile | < 750px | 1-column, full-width images |
| Tablet | 750px - 1199px | 2-column grids, adjusted spacing |
| Desktop | ≥ 1200px | 3-column grids, full layouts |

---

## Styling & Animation Classes

### Common Classes
```
- `.page-width` - Max-width container (1200px)
- `.scroll-trigger` - Intersection observer for animations
- `.animate--slide-in` - Slide-in animation on scroll
- `.animate--fade-in` - Fade-in animation on scroll
- `.grid` - CSS grid layout
- `.slider-component` - Carousel/slider functionality
- `.content-container` - Content wrapper with padding
- `.color-scheme-N` - Apply color scheme
- `.gradient` - Apply gradient background
```

### Animation Timing
- Most sections: `scroll-trigger animate--slide-in`
- Hero: `scroll-trigger animate--fade-in`
- Footer blocks: `data-cascade` with staggered timing

---

## Next Steps for Shopify Liquid Conversion

1. **Create Section Files**
   - `sections/hero-slideshow.liquid`
   - `sections/shop-by-category.liquid`
   - `sections/featured-collection.liquid`
   - `sections/image-with-text.liquid`
   - `sections/multicolumn-benefits.liquid`
   - `sections/rich-text.liquid`
   - `sections/instagram-feed.liquid`
   - `sections/footer.liquid`

2. **Create Schema for Each Section**
   - Image inputs
   - Text fields (heading, body, button)
   - Link inputs
   - Color scheme selector
   - Layout options (columns, autoplay, etc.)

3. **Extract CSS**
   - Review original CSS files referenced in HTML
   - Port styles to theme CSS or section-specific stylesheets
   - Implement responsive behavior

4. **Handle Dynamic Content**
   - Featured collections: use Shopify collection objects
   - Products: use Shopify product objects
   - Navigation: use Shopify menu objects
   - Forms: use Shopify form APIs

5. **Set Up Theme Structure**
   - Create `config/settings_schema.json` for customization
   - Add section groups (header, footer)
   - Configure product card styles
   - Set up color customizer

---

## Notes & Observations

- **Performance:** Multiple featured collections on page - consider lazy loading
- **Responsive Images:** All hero images use `<picture>` with mobile/desktop variants
- **Product Variants:** Cards show variant color swatches - implement variant selection
- **Accessibility:** Section uses proper ARIA labels, heading hierarchy, semantic HTML
- **Animations:** Scroll-triggered animations enhance engagement - keep in Liquid version
- **App Blocks:** Instagram feed and Klaviyo form require app integration
- **Color Gradients:** Extensive use of gradient backgrounds - leverage Shopify color customizer

---

## Design System & Typography

### Verified Color Palette

```
Primary Dark:       #3d3d3d (charcoal) - announcement bar, trust/commitment, instagram, footer accents
Background White:   #ffffff (white) - main content sections
Text Dark:          #121212 (near-black) - body text
Text Light:         #ffffff (white) - text on dark backgrounds
Star Rating:        Gold/amber - product reviews
Badge Accent:       Teal/green - "NEW ARRIVAL" badges
Link Color:         Blue (secondary)
```

### Typography Family

| Element | Font | Style | Usage |
|---------|------|-------|-------|
| Headings | Montserrat (or similar sans-serif) | Uppercase, wide letter-spacing (0.1-0.2em) | Section titles, product names |
| Body Text | Nunito Sans (or similar clean sans) | Regular weight, normal case | Descriptions, paragraphs |
| Logo | Custom script/cursive font | Elegant, centered | Brand identity |
| Navigation | Montserrat | Uppercase, tracking wide | Menu items |

### Spacing Rhythm

| Element | Spacing |
|---------|---------|
| Section vertical padding | 60-80px |
| Content max-width | ~1200px |
| Grid/column gaps | 20-30px |
| Card internal padding | 16-20px |
| Bottom margin section-to-section | 40-60px |

### Component Patterns (Reusable)

#### 1. Product Card
- **Layout:** Square image (1:1 ratio) above text
- **Elements:**
  - Image container (optional badge overlay in top-right)
  - Product title (2-3 lines, may be truncated)
  - Star rating (gold stars) + review count
  - Price format: "From $XXX.00"
  - Color swatch dots below price (max 6 visible)
- **Hover state:** Image slightly scales, text may highlight
- **Badge:** Teal/green background, white text (e.g., "NEW ARRIVAL")

#### 2. Feature Block (Image + Text)
- **Layout:** 50/50 two-column on desktop, stacked on mobile
- **Alternating pattern:**
  - Feature Block 1: Image Left, Text Right
  - Feature Block 2: Image Right, Text Left (reversed)
- **Text side:**
  - Large stacked headline (uppercase, wide spacing)
  - Short body paragraph (2-3 sentences)
  - Dark charcoal CTA button with arrow icon
- **Image side:** Square or near-square aspect ratio
- **Vertical alignment:** Center

#### 3. Product Carousel / Collection Slider
- **Grid:** 4 products visible (desktop), 2 (tablet), 1 (mobile)
- **Controls:**
  - Prev/next arrows on sides
  - Pagination counter (e.g., "1/23")
  - Optional "VIEW ALL" link centered below
- **Auto-scroll:** Optional based on collection
- **Touch:** Swipe-enabled on mobile

#### 4. Section Header (Standard)
- **Pattern:** Appears on most sections
- **Centered:**
  - h2 heading (uppercase, wide letter-spacing)
  - Optional subtitle (regular weight, centered)
  - Generous whitespace above/below
- **Used in:** Shop by Category, Just In, Best Sellers, Cotton Sheets, etc.

#### 5. Trust/Commitment Section
- **Layout:**
  - Dark background (charcoal #3d3d3d)
  - Centered heading + body paragraph
  - 3 horizontal ghost buttons below (white border, no fill)
- **Buttons:**
  - Text + arrow icon
  - Hover: inverts to white background / dark text
  - Links to policy pages

### Page Rhythm Pattern (Color/Style Distribution)

```
DARK    → Announcement Bar (#3d3d3d)
WHITE   → Header/Navigation
IMAGE   → Hero Slideshow (full-width background images)
WHITE   → Shop by Category (grid of category cards)
DARK    → Our Commitment to You (trust/guarantee section)
WHITE   → Benefits Multicolumn (3 feature boxes)
WHITE   → Featured Collection "Just In" (product carousel)
WHITE   → Feature Block - Throw Pillows (image + text)
WHITE   → Featured Collection "Best Sellers" (product carousel)
WHITE   → Feature Block - Quilts/Coverlets (image + text, reversed)
WHITE   → Featured Collection "Cotton Sheets" (product carousel)
DARK    → Instagram Feed Section (#3d3d3d similar)
WHITE   → Footer
```

This dark-white-image rhythm creates visual breathing room and emphasizes key content areas.

### Design System Observations

#### Button Styles
- **Primary CTA:** Dark charcoal (#3d3d3d), white text, uppercase, small caps, arrow icon
- **Secondary:** Link-style with arrow, underline on hover
- **Ghost buttons:** White border, no fill, white text on dark backgrounds

#### Image Treatment
- **Product images:** Clean, neutral white/light backgrounds, lifestyle context
- **Hero images:** Full-bleed, high-resolution lifestyle photography
- **Aspect ratios:**
  - Products: 1:1 (square)
  - Feature blocks: ~1:1 (square)
  - Hero: Full-width responsive
  - Category cards: ~4:3 or flexible

#### Borders & Shadows
- **Cards:** Subtle drop shadows (0 2px 8px rgba(0,0,0,0.1))
- **Hover states:** Shadow deepens slightly
- **Borders:** Minimal - mostly content separation via spacing/color

#### Animation Patterns (CSS/JS)
- **Scroll-triggered:** Fade/slide-in as elements enter viewport
- **Hover states:** Slight scale, shadow enhancement, color transitions
- **Carousel:** Smooth slide transitions, momentum scroll on mobile
- **Star ratings:** May have subtle fill animation

### Improvement Opportunities (As Identified)

**Performance:**
- Implement lazy loading for carousel images
- Use `srcset` for responsive image optimization
- Preload hero images (high priority)

**Accessibility:**
- ARIA labels on all carousels and sliders
- Keyboard navigation for interactive components
- Focus states visible on all interactive elements
- Screen reader text for star ratings and badges
- Proper heading hierarchy (H1, H2, etc.)

**Mobile Experience:**
- Touch-friendly carousel with swipe gestures
- Collapsible mega-menu for navigation
- Stack feature blocks fully vertical on small screens
- Tap targets minimum 44px × 44px

**Schema/Content Flexibility:**
- Make badge text customizable (not just "NEW ARRIVAL")
- Allow variable number of trust badges (currently 3)
- Configurable product count per carousel
- Configurable carousel auto-play timing
- Optional section background colors/gradients

---

## Implementation Priority Order

Based on dependencies and visibility:

1. **`announcement-bar.liquid`** - Simple, high visibility, no dependencies
2. **`hero-slideshow.liquid`** - Core homepage hero, foundation section
3. **`collection-list.liquid`** - Shop by category (reusable carousel pattern)
4. **`trust-badges.liquid`** or enhance `rich-text.liquid` - Commitment section
5. **`featured-collection.liquid`** - Reusable product carousel (used 3x)
6. **`image-with-text.liquid`** - Feature blocks (image left/right variants)
7. **`instagram-feed.liquid`** - Social proof, app block integration
8. **`footer.liquid`** - Last section, relies on navigation/menus
