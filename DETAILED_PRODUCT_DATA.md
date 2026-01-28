# Linens & Hutch - Detailed Product & Category Data

> **Purpose:** Complete product, category, and link data extracted from homepage HTML
> **Source:** linens-and-hutch-homepage.html
> **Use for:** Populating Shopify theme with actual product/category content

---

## Shop By Category - Complete Item List

**Section ID:** `template--15585548304466__shop_by_category_GbzkjX`
**Total Items:** 24 (8 unique categories repeated 3x)
**Grid Layout:** 3-column (desktop), 2-column (tablet), 1-column (mobile), carousel slider
**Image Base Path:** `https://www.linensandhutch.com/cdn/shop/collections/`

### All 8 Unique Categories

| Item # | Category Title | Collection URL | Image Filename | Description | Note |
|--------|---|---|---|---|---|
| 1 | Sheets | /collections/sheets | 1KLH-4PC-WHITE-HERO-C5.jpg | Match Your Sleep Style: The Importance of Choosing the Right Bed sheets. When it comes to creating the perfect sleep environment, there are many... | Core product |
| 2 | Comforters | /collections/comforters | 1KLH-COMF-TEX-WHITE-C5A_e1f77383-2697-44d7-8d6a-0909bd2b73c2.jpg | Discover the Versatile Comfort of Linens & Hutch's Full Comforter Collection. When designing your bedroom sanctuary, a comforter is the centerpiece... | Core product |
| 3 | Duvet Covers | /collections/duvet-covers | 1KLH-DUVET-WHITE-C2A_cb7379ee-0471-4d14-9de6-46319d487f02.png | Elevate Your Room's Style with Duvet Covers. Duvet covers serve as a protective layer that keeps your comforter clean while adding a... | Core product |
| 4 | Quilts | /collections/quilts | 1KLH-QLT-FLO-WHITE-C2A_4e798ac8-3f74-4b91-bca5-1692c6a8aadf.jpg | Discover the world of Linens & Hutch quilts, where luxury and comfort meet tradition. Our quilts feature premium materials and... | Core product |
| 5 | Bedding Essentials | /collections/bedding-essentials | BASIC-COLLECTION-1-1x1.jpg | Your bedroom is more than just a place to sleep; it's your sanctuary. At Linens & Hutch, we understand that quality matters when it... | Core product |
| 6 | Throw Pillows | /collections/throw-pillows | 1KLH-IN-SO-SO-20-NTWH-ALT4A.jpg | Introducing Linens & Hutch Decorator Pillows: Elevate Your Room with Style and Comfort. Decorator pillows are the finishing touch... | Core product |
| 7 | Blankets | /collections/blankets | IEH-THW-CHKN-IVORY-CR-03_f4edcce0-db22-4da3-962c-944c83425e00.jpg | Stay warm in style with our selection of durable and ultra-soft throw blankets. Perfect for snuggling on the couch... | Core product |
| 8 | Bath | /collections/bath | TOWEL-COLLECTION-WHITE_06d48d45-afb3-4120-94c6-e67dd5f3fd72.jpg | Softness and Comfort: Linens & Hutch bath towels are crafted from 100% premium materials for ultimate comfort and absorbency... | Extends beyond bedding |

---

## Featured Collections - Complete Product Details

### Featured Collection #1: "JUST IN"

**Section ID:** `template--15585548304466__featured_collection`
**Heading:** JUST IN
**Description:** Discover new arrivals designed to bring style and warmth to every space
**Layout:** 3-column (desktop), slider with peek navigation, 1-column (mobile)
**Card Ratio:** 100% (square)

**Sample Product: Cloud Weave Textured Down-Alternative Comforter Set**
```
Title: Cloud Weave Textured Down-Alternative Comforter Set
Product URL: /products/cloud-weave-textured-comforter-set
Primary Image: 1KLH-COMF-TCW-DUNE-02-C5-GRAPHIC_8664e7f4-82f0-4828-b480-7a01fb67e642.jpg
Color Variants: Dune, Tan, Olive, Fog, Slate-Blue
Price: $179.00
Rating: 4.7/5 stars (69 reviews)
```

### Featured Collection #2: "EXPERIENCE OUR BEST SELLERS"

**Section ID:** `template--15585548304466__6a65d575-4b31-4910-b3f4-d4da2b5cf9b9`
**Heading:** EXPERIENCE OUR BEST SELLERS
**Description:** Make your room a restful oasis with our most loved bedding

**Sample Product: Luxury Gel Pillow**
```
Title: Luxury Gel Pillow / Plush Down-Alternative Gel-Fiber Pillow (2-Pack)
Product URL: /products/luxury-gel-pillow
Primary Image: linens-and-hutch-pillows-queen-plush-down-alternative-gel-fiber-pillow-2-pack-31128120066130.png
```

---

## Footer Navigation - Complete Link Structure

### Column 1: ABOUT
- Our Story → /pages/about-us
- Reviews → /pages/reviews
- Blog → /blogs/linens-hutch-blog
- Affiliates → /pages/linens-hutch-affiliate-program
- E-Gift Cards → /products/linens-hutch-e-gift-card

### Column 2: CONTACT
- Contact → /pages/contact-us
- FAQ → /pages/faq
- Returns & Exchanges → /pages/returns-exchanges
- Mobile Terms → https://www.linensandhutch.com/pages/mobile-terms-of-service
- Your Privacy Choices → /pages/data-sharing-opt-out

### Column 3: NEWSLETTER
- Klaviyo email signup form (app block)

### Column 4: FOLLOW US
- Facebook → https://www.facebook.com/LinensandHutch
- Instagram → https://www.instagram.com/linensandhutch
- TikTok → https://www.tiktok.com/@linensandhutch
- X/Twitter → https://twitter.com/linensandhutch
- Pinterest → https://www.pinterest.com/linensandhutch

### Footer Bottom: Policy Links
- Refund policy → /policies/refund-policy
- Privacy policy → /policies/privacy-policy
- Terms of service → /policies/terms-of-service
- Shipping policy → /policies/shipping-policy
- Contact information → /policies/contact-information

---

## Shopify Liquid Implementation Templates

### Featured Collection Section
```liquid
{% for product in collection.products limit: 6 %}
  <div class="product-card">
    <div class="product-image">
      {% if product.featured_image %}
        <img src="{{ product.featured_image | img_url: '500x500' }}"
             alt="{{ product.featured_image.alt | escape }}"
             loading="lazy">
      {% endif %}
    </div>
    <div class="product-content">
      <h3>{{ product.title }}</h3>
      <p class="price">{{ product.price | money }}</p>
    </div>
  </div>
{% endfor %}
```

### Category Grid Section
```liquid
{% assign categories = "Sheets,Comforters,Duvet Covers,Quilts" | split: "," %}
<div class="category-grid">
  {% for category in categories %}
    {% assign collection = collections[category | downcase | replace: ' ', '-'] %}
    <div class="category-card">
      {% if collection.image %}
        <img src="{{ collection.image | img_url: '400x400' }}"
             alt="{{ collection.title }}">
      {% endif %}
      <h3>{{ collection.title }}</h3>
      <a href="{{ collection.url }}">Shop Now →</a>
    </div>
  {% endfor %}
</div>
```

---

## CDN Image Base Paths

| Content Type | Base Path |
|---|---|
| Hero/Banner Images | `/cdn/shop/files/` |
| Product Images | `/cdn/shop/files/` |
| Collection Images | `/cdn/shop/collections/` |
| Category Images | `/cdn/shop/collections/` |

---

## Notes for Implementation

### Product Variant Management
- Featured collections show color swatches
- Implement variant selection on hover/click
- Display variant images in product cards
- Update pricing based on selected variant

### Responsive Behavior
- Hero: Mobile-specific image srcset
- Collections: Grid columns change at breakpoints
- Images: Automatic sizing based on viewport
- Text: Font sizes adjust for mobile

### Performance Considerations
- Lazy load product images
- Use appropriate image widths for each breakpoint
- Implement image optimization (WebP, AVIF)

### Accessibility
- All images have alt text
- Links have descriptive text
- Color contrast meets WCAG AA standards
- Semantic HTML structure

### Dynamic Content Sources
- Collections pull from Shopify collection objects
- Products pull from featured collection settings
- Footer links pull from Shopify menu system
- Social links from shop settings
