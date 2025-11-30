# Pawtograph Landing Page & Promotional Boxes Implementation Plan

## Overview

Add a dedicated SEO-optimized Pawtograph landing page and promotional boxes throughout the Mäusenews.de static site to drive traffic to Pawtograph app.

**Key Deliverables:**
1. SEO-optimized landing page targeting "haustierportrait app"
2. Navigation menu integration under "Fotos und Videos"
3. Mid-article promotional boxes on 16 article pages
4. Supporting CSS and image assets

---

## 1. Landing Page Structure

### URL & Location
**Path:** `/haustierportrait-app/index.html`

**SEO Rationale:**
- Contains primary keyword "haustierportrait app" in URL
- Root-level directory for better SEO authority
- Clean, readable structure

### Page Sections

**1. Hero Section**
- Headline: "Studio-Look in 20 Sekunden: Die Haustierportrait-App für perfekte Fotos"
- Subheadline: "Verwandle normale Handyfotos deiner Rennmäuse, Hamster und anderen Haustiere in professionelle Porträts – ganz ohne Stress fürs Tier"
- Primary CTA: "Pawtograph jetzt kostenlos ausprobieren"
- Hero image: Phone mockup with app

**2. Benefits Section (3 columns)**
- Studio-Look in 20 Sekunden
- Ohne Stress fürs Tier
- Kostüme & Hintergründe

**3. How It Works (3 steps)**
1. Foto hochladen
2. Stil auswählen
3. Fertig!

**4. Example Gallery**
- Before/after comparisons (gerbil and hamster examples)

**5. Use Cases**
- Geschenke, Social Media, Wanddekoration

**6. Features Deep Dive**
- Hunderte professionelle Hintergründe
- Virtuelle Kostüme & Accessoires
- Intelligente KI-Technologie

**7. Testimonials**
- 3 customer quotes from pet owners

**8. FAQ Section**
- 6 common questions with Schema.org FAQPage markup

**9. Final CTA**
- "Bereit für professionelle Haustierporträts?"

### SEO Optimization

**Title Tag:**
```
Haustierportrait App: Studio-Fotos in 20 Sekunden mit Pawtograph
```

**Meta Description:**
```
Verwandle Handy-Fotos deiner Rennmäuse, Hamster und anderen Haustiere in professionelle Porträts. Die KI-App Pawtograph erstellt Studio-Look-Fotos mit Kostümen und Hintergründen – ganz ohne Stress fürs Tier.
```

**Schema.org Markup:**
- SoftwareApplication schema
- FAQPage schema
- Organization schema

**Keyword Strategy:**
- Primary: "haustierportrait app" (6-8 mentions)
- Secondary: "haustierfotos app", "tierportrait app"
- Long-tail: "haustier foto bearbeiten", "rennmaus foto"

### Required Image Assets

Upload to `/wp-content/uploads/`:

1. **pawtograph-hero-phone.png** (800x600px) - App mockup
2. **pawtograph-example-before-1.jpg** (600x600px) - Rennmaus normal photo
3. **pawtograph-example-after-1.jpg** (600x600px) - Rennmaus portrait
4. **pawtograph-example-before-2.jpg** (600x600px) - Hamster normal photo
5. **pawtograph-example-after-2.jpg** (600x600px) - Hamster portrait
6. **pawtograph-feature-backgrounds.jpg** (600x400px) - Backgrounds showcase
7. **pawtograph-feature-costumes.jpg** (600x400px) - Costumes showcase
8. **pawtograph-feature-ai.jpg** (600x400px) - AI visualization

All images: optimized, compressed, under 200KB each

---

## 2. Navigation Menu Integration

### Location
Add under **"Fotos und Videos"** dropdown as FIRST item

### HTML Code to Insert

```html
<li id="menu-item-pawtograph" class='menu-item menu-item-type-custom menu-item-object-custom menu-item-pawtograph'>
<a title="Pawtograph: Haustierportrait-App" href="/haustierportrait-app/?utm_source=maeusenews&utm_medium=navigation&utm_campaign=menu_fotos_videos" tabindex="-1">
<i class="fa fa-star"></i> Pawtograph: Haustierportrait-App
</a>
</li>
```

### Files Requiring Navigation Update

Approximately 50+ HTML files:
- `/index.html`
- All 11 `/bauanleitungen/*/index.html`
- All 5 `/rennmaus-ratgeber/*/index.html`
- All `/kategorie/*/index.html`
- All `/page/N/index.html`
- All `/specials/*/index.html`
- Other article pages

**Implementation approach:** Use find/replace across all files or create automation script

---

## 3. Mid-Article Promotional Boxes

### Visual Design

**Style:** Tip/info box with lightbulb icon, matching site's brown/tan color scheme

**CSS File:** `/wp-content/uploads/pawtograph-promo.css`

```css
.pawtograph-promo-box {
    background-color: #FFF8E7;
    border-left: 4px solid #8b7355;
    border-radius: 4px;
    padding: 20px 25px;
    margin: 30px 0;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.pawtograph-promo-box .promo-icon {
    color: #8b7355;
    font-size: 24px;
    margin-right: 12px;
    vertical-align: middle;
}

.pawtograph-promo-box .promo-title {
    color: #603E2D;
    font-size: 18px;
    font-weight: 700;
    margin: 0 0 10px 0;
    display: inline-block;
}

.pawtograph-promo-box .promo-text {
    color: #4c3023;
    font-size: 16px;
    line-height: 1.6;
    margin: 0 0 15px 0;
}

.pawtograph-promo-box .promo-link {
    display: inline-block;
    background-color: #8b7355;
    color: #FAECD5;
    padding: 10px 20px;
    border-radius: 4px;
    text-decoration: none;
    font-weight: 600;
    transition: background-color 0.3s ease;
}

.pawtograph-promo-box .promo-link:hover {
    background-color: #603E2D;
    color: #FAECD5;
    text-decoration: none;
}

.pawtograph-promo-box .promo-link i {
    margin-left: 5px;
}
```

### HTML Structure

```html
<div class="pawtograph-promo-box">
    <div>
        <i class="fa fa-lightbulb-o promo-icon"></i>
        <h3 class="promo-title">Tipp: Schönere Fotos von deinen Rennmäusen</h3>
    </div>
    <p class="promo-text">
        Mit der App Pawtograph kannst du aus normalen Handyfotos richtig hochwertige Tierporträts machen – inklusive Hintergründen und Effekten, ohne Stress fürs Tier. In nur 20 Sekunden zum Studio-Look!
    </p>
    <a href="/haustierportrait-app/?utm_source=maeusenews&utm_medium=article_promo&utm_campaign=inline_tip_bauanleitungen" class="promo-link">
        Mehr über Pawtograph erfahren <i class="fa fa-arrow-right"></i>
    </a>
</div>
```

### Content Variations

Create 4 variations to avoid repetition:

**Variation 1 - Photo-focused (bauanleitungen):**
```
Tipp: Schönere Fotos von deinen Rennmäusen

Mit der App Pawtograph kannst du aus normalen Handyfotos richtig hochwertige Tierporträts machen – inklusive Hintergründen und Effekten, ohne Stress fürs Tier. In nur 20 Sekunden zum Studio-Look!
```

**Variation 2 - Stress-free focus (ratgeber):**
```
Tipp: Professionelle Tierfotos ohne Stress

Keine Blitzlichter, kein Posieren: Mit Pawtograph verwandelst du einfache Handyfotos in professionelle Haustierporträts. Die KI-App fügt Hintergründe und Kostüme digital hinzu – deine Rennmäuse bleiben entspannt.
```

**Variation 3 - Gift/sharing focus:**
```
Tipp: Besondere Erinnerungen schaffen

Möchtest du deine Rennmausfotos teilen oder verschenken? Mit Pawtograph erstellst du in Sekunden professionelle Portraits mit Studio-Qualität – perfekt für Social Media, Drucke oder Geschenke.
```

**Variation 4 - DIY tie-in:**
```
Tipp: Das perfekte Foto fürs selbstgebaute Projekt

Du bist kreativ beim Basteln – warum nicht auch bei Fotos? Pawtograph macht aus deinen Handyfotos professionelle Tierporträts mit individuellen Hintergründen und Effekten. Ganz ohne Profi-Ausrüstung!
```

### Placement Strategy

**Where:** After first 2-3 paragraphs or after first H2 heading

**Location in HTML:** Within `<div class="section-inner card single-content-card content-card">`

### UTM Tracking

**Bauanleitungen:**
```
?utm_source=maeusenews&utm_medium=article_promo&utm_campaign=inline_tip_bauanleitungen
```

**Rennmaus-Ratgeber:**
```
?utm_source=maeusenews&utm_medium=article_promo&utm_campaign=inline_tip_ratgeber
```

### Files Requiring Promotional Box (16 total)

**Bauanleitungen (11):**
1. `/bauanleitungen/tipps-zum-bauen-fuer-rennmaeuse/index.html`
2. `/bauanleitungen/rennmaus-labyrinth-selber-bauen/index.html`
3. `/bauanleitungen/haus-und-fressnapf-aus-einer-kokosnuss/index.html`
4. `/bauanleitungen/trinkflaschenhalterung-fuer-die-classic-heimtiertraenke/index.html`
5. `/bauanleitungen/deckel-fuer-ein-aquarium-bauen/index.html`
6. `/bauanleitungen/mandarinenleuchte-basteln/index.html`
7. `/bauanleitungen/ein-weihnachtsmann-zum-anknabbern/index.html`
8. `/bauanleitungen/nikolausstiefel-zum-anknabbern/index.html`
9. `/bauanleitungen/rennmaus-plaetzchenausstecher/index.html`
10. `/bauanleitungen/fledermaus-aus-socke-basteln/index.html`
11. `/bauanleitungen/maeusegesicht-plaetzchenausstecher/index.html`

**Rennmaus-Ratgeber (5):**
1. `/rennmaus-ratgeber/eine-kurze-zusammenfassung/index.html`
2. `/rennmaus-ratgeber/herkunft-fellfarben-sinne-rennmausarten-und-mehr/index.html`
3. `/rennmaus-ratgeber/kauf-einrichtung/index.html`
4. `/rennmaus-ratgeber/pflege-tipps-freilauf/index.html`
5. `/rennmaus-ratgeber/probleme-mit-rennmaeusen/index.html`

---

## 4. Landing Page CSS

**File:** `/wp-content/uploads/pawtograph-landing.css`

Key components:
- Hero section with gradient background
- Benefit cards with hover effects
- Step numbers with circular badges
- Example cards with before/after layout
- Testimonial cards with left border accent
- FAQ items with schema markup support
- CTA section with dark gradient background
- Fully responsive (mobile breakpoints)

Colors match site theme: #8b7355 (brown), #603E2D (dark brown), #FAECD5 (tan)

---

## 5. Implementation Steps

### Phase 1: Asset Preparation
1. Gather/create all 8 images
2. Optimize images for web (compress, resize)
3. Upload to `/wp-content/uploads/`
4. Create CSS files (`pawtograph-landing.css`, `pawtograph-promo.css`)

### Phase 2: Landing Page Creation
1. Create `/haustierportrait-app/` directory
2. Build `/haustierportrait-app/index.html`
3. Copy navigation from existing page template
4. Add all content sections
5. Implement SEO meta tags and Schema.org markup
6. Link CSS and images
7. Test (desktop, mobile, browsers)

### Phase 3: Navigation Menu Update
1. Update navigation in `/index.html` first
2. Test navigation functionality
3. Update all ~50+ HTML files (use find/replace or script)
4. Verify navigation on sample pages
5. Test mobile dropdown

### Phase 4: Promotional Box Implementation
1. Link `pawtograph-promo.css` in all 16 article pages
2. Insert promotional boxes:
   - Bauanleitungen (11 files) - Variation 1 or 4
   - Ratgeber (5 files) - Variation 2 or 3
3. Customize UTM parameters per category
4. Test visual appearance and links

### Phase 5: Quality Assurance
1. Cross-browser testing (Chrome, Firefox, Safari, Edge)
2. Mobile responsiveness testing
3. SEO validation (title tags, meta descriptions, schema)
4. Performance testing (page speed, image optimization)
5. Link testing (all CTAs, UTM parameters)
6. Analytics tracking verification

### Phase 6: Launch & Monitor
1. Deploy to production
2. Submit to Google Search Console
3. Monitor analytics (traffic, CTR, conversions)
4. Track keyword rankings
5. Iterate based on data

---

## Critical Files

1. **`/haustierportrait-app/index.html`** - Main landing page (NEW)
2. **`/index.html`** - Navigation template
3. **`/bauanleitungen/rennmaus-labyrinth-selber-bauen/index.html`** - Article template for promo box
4. **`/wp-content/uploads/pawtograph-landing.css`** - Landing page styles (NEW)
5. **`/wp-content/uploads/pawtograph-promo.css`** - Promotional box styles (NEW)

---

## Success Metrics

**Primary KPIs:**
- Traffic to landing page: 3,000 visits/month by Month 6
- Click-through rate to Pawtograph: > 10%
- Promotional box CTR: > 5%
- SEO ranking: Top 3 for "haustierportrait app" by Month 6

**UTM Campaign Tracking:**
- Landing page hero: `utm_campaign=landingpage_cta_hero`
- Landing page final: `utm_campaign=landingpage_cta_final`
- Sidebar banner: `utm_campaign=maeusenews_sidebar`
- Article promo (Bauanleitungen): `utm_campaign=inline_tip_bauanleitungen`
- Article promo (Ratgeber): `utm_campaign=inline_tip_ratgeber`
- Navigation menu: `utm_campaign=menu_fotos_videos`

---

## Project Scope

- **Timeline:** 10-14 days
- **New files:** 10 (1 HTML + 2 CSS + 7 images)
- **Files to modify:** 66+ (50+ navigation + 16 promo boxes)
- **Estimated effort:** 40-60 hours
