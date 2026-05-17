# ReWired — SEO Implementation Checklist
# Staying on Vercel — full optimisation guide
# ============================================================
#
# Work through these in order. Each section is a sprint.
# Estimated time: Sprint 1 = ~2 hours | Sprint 2 = ~4 hours
#
# ============================================================


## SPRINT 1 — Deploy today (highest impact, no content needed)
## ──────────────────────────────────────────────────────────

### 1. Add vercel.json to your repo root
   File: vercel.json (provided)
   - Sets correct cache headers for assets (1 year immutable)
   - Ensures HTML is never cached (always fresh for Googlebot)
   - Adds X-Robots-Tag: index, follow to all pages
   - Adds security headers that improve trust signals

   ✓ Copy vercel.json → project root
   ✓ git commit && git push → Vercel auto-deploys


### 2. Add robots.txt to /public/
   File: robots.txt (provided)
   - Tells crawlers they can index everything
   - Points to sitemap.xml location
   - Blocks /_vercel/ system paths from crawling

   ✓ Copy robots.txt → public/robots.txt
   ✓ Verify live at: https://rewiredxapp.vercel.app/robots.txt


### 3. Add sitemap.xml to /public/
   File: sitemap.xml (provided)
   - Single URL for now; add new pages as you build them
   - Update <lastmod> date whenever you make significant changes

   ✓ Copy sitemap.xml → public/sitemap.xml
   ✓ Verify live at: https://rewiredxapp.vercel.app/sitemap.xml


### 4. Replace your <head> with seo-head.html
   File: seo-head.html (provided)
   BEFORE deploying, update these placeholders:
   □ og:image URL — create a 1200×630 og-image.png and add to /public/
   □ twitter:site — change @rewiredxapp to your real handle (or remove)
   □ theme-color — update #0f0f0f to your actual brand dark colour
   □ sameAs in Organization schema — add your real social profile URLs
   □ favicon files — generate at realfavicongenerator.net and add to /public/

   ✓ Replace <head>…</head> in index.html
   ✓ Create and add /public/og-image.png (1200×630px)
   ✓ git commit && git push


### 5. Apply copy rewrites from copy-rewrites.html
   File: copy-rewrites.html (provided)
   Priority order (highest SEO impact first):
   □ H1 — replace with keyword-bearing version
   □ Features H2 — add "digital detox app" to the section heading
   □ CTA section — add the <ul> benefits list above the Tally iframes
   □ Footer — link Privacy/Terms to real URLs, update tagline
   □ H3 feature headings — replace with keyword-loaded versions
   □ Built Different H2 and H3s

   ✓ Apply changes to index.html
   ✓ git commit && git push


### 6. Set up Google Search Console
   Go to: https://search.google.com/search-console/

   a) Add property: https://rewiredxapp.vercel.app/
   b) Verify via HTML tag method (add the <meta name="google-site-verification" ...>
      tag to your <head> — add it to seo-head.html above the title tag)
   c) Submit sitemap: Sitemaps → Add: https://rewiredxapp.vercel.app/sitemap.xml
   d) Request indexing: URL Inspection → enter / → Request Indexing

   ✓ Property verified in Search Console
   ✓ Sitemap submitted
   ✓ Index requested


## SPRINT 2 — Week 2–4 (deeper improvements)
## ──────────────────────────────────────────

### 7. Optimise images
   File: image-optimisation.html (provided)
   □ Convert 3 PNG screenshots to WebP using @squoosh/cli
   □ Replace <img> tags with <picture> + WebP source + PNG fallback
   □ Add explicit width/height attributes to all images
   □ Add loading="eager" + fetchpriority="high" to onboarding screen only
   □ Add loading="lazy" to dashboard and rewards marketplace screens
   □ Run PageSpeed Insights mobile test — target LCP < 2.5s

   ✓ Images converted and deployed
   ✓ PageSpeed mobile score confirmed ≥ 75


### 8. Create /privacy and /terms pages
   Currently these links go to # (broken).
   Google's quality raters flag sites without real legal pages.

   Minimum viable versions:
   □ /privacy — basic privacy policy (use a generator like privacypolicygenerator.info)
   □ /terms — basic terms of service
   □ Update sitemap.xml to include these URLs

   ✓ Pages live and linked from footer


### 9. Add FAQ section to homepage
   Adding an FAQ section lets you enable the FAQPage JSON-LD schema
   (already written in seo-head.html, just commented out).
   FAQs unlock accordion rich results in Google — they dramatically
   increase click-through rate without requiring higher rankings.

   Suggested questions:
   □ How does ReWired help reduce screen time?
   □ Is ReWired free?
   □ What rewards can I earn from The Vault?
   □ Does ReWired work on iPhone and Android?
   □ How is ReWired different from Apple Screen Time or Android Digital Wellbeing?

   ✓ FAQ section added to page (above footer is conventional)
   ✓ FAQPage schema uncommented in seo-head.html


### 10. Add aggregateRating to SoftwareApplication schema
    Once you have user reviews (beta testers, waitlist feedback,
    product hunt upvotes), add this to your SoftwareApplication schema:

    "aggregateRating": {
      "@type": "AggregateRating",
      "ratingValue": "4.8",
      "ratingCount": "127",
      "bestRating": "5",
      "worstRating": "1"
    }

    This unlocks star ratings in search results — one of the highest
    CTR improvements available in the app category.

    ✓ Reviews collected
    ✓ aggregateRating added to schema


## SPRINT 3 — Month 2+ (authority building)
## ──────────────────────────────────────────

### 11. Build a /blog directory
    Add these four posts (in priority order):

    Post 1: /blog/how-to-stop-doomscrolling
    Target keyword: "how to stop doomscrolling" (high volume, moderate competition)
    Angle: Science-backed. Reference the behavioral psychology behind scroll loops.
    Length: 1,800–2,200 words
    Internal links: Link to homepage with anchor text "ReWired screen time app"

    Post 2: /blog/best-screen-time-apps-2026
    Target keyword: "best screen time apps" (very high volume)
    Angle: Honest comparison — ReWired vs Forest vs Opal vs One Sec vs Digital Wellbeing
    Length: 2,000–2,500 words
    Internal links: Link to homepage from "earn real rewards" mentions

    Post 3: /blog/phone-addiction-how-much-time-are-you-losing
    Target keyword: "phone addiction" (high volume, broad)
    Angle: Data-driven. The 2.5 hours/day calculation. Productivity/money cost.
    Length: 1,500–2,000 words

    Post 4: /blog/dopamine-infinite-scroll-science
    Target keyword: "dopamine scrolling" (growing trend query)
    Angle: Academic/editorial. Links from psychology and wellness publications.
    Length: 2,000+ words

    ✓ Blog infrastructure built (/blog listing + individual post pages)
    ✓ First post published and added to sitemap
    ✓ Posts interlink to each other and to homepage


### 12. Launch on Product Hunt
    Product Hunt links are followed (DR 90+) and drive genuine traffic.
    Coordinate a launch day:
    □ Build a product gallery with your best screenshots
    □ Write a maker comment explaining the rewards mechanic
    □ Ask your waitlist to upvote on launch day
    □ The Product Hunt listing creates a permanent backlink

    ✓ Product Hunt listing live
    ✓ URL added to Organization schema sameAs


### 13. Get listed in app roundup articles
    Search for: "best screen time apps" → find top 10 ranking articles
    → reach out to authors asking to be included.

    Key targets:
    □ androidpolice.com — already ranks for this topic
    □ blog.nextgrowthlabs.com — reviewed 15+ screen time apps
    □ digitalwellbeingapps.com — dedicated comparison site
    □ readreboot.com — digital wellness newsletter with engaged audience
    □ Wirecutter/NYT — if you have enough reviews to qualify

    Email template angle:
    "ReWired is the only screen time app that pays users back with real
    rewards — I think your readers would find it a genuinely different
    option from Forest/Opal. Happy to provide a promo code for your readers."


## TRACKING PROGRESS
## ──────────────────────────────────────────

    Weekly checks (every Monday, 15 minutes):
    □ Google Search Console → Coverage → any new errors?
    □ Search Console → Performance → impressions growing?
    □ PageSpeed Insights → mobile score still ≥ 75?

    Monthly checks:
    □ Search Console → Queries → which terms are you ranking for?
    □ Ahrefs Free / Ubersuggest → check domain rating growth
    □ Update <lastmod> in sitemap.xml if significant changes made

    Success metrics for 90 days post-Sprint-1:
    □ Site indexed in Google (check: site:rewiredxapp.vercel.app)
    □ Appearing for brand name "rewired app"
    □ 1 long-tail keyword in top 20 (e.g. "screen time rewards app")
    □ PageSpeed mobile LCP < 2.5s


## FILE SUMMARY
## ──────────────────────────────────────────

    vercel.json           → project root (not in /public/)
    robots.txt            → public/robots.txt
    sitemap.xml           → public/sitemap.xml
    seo-head.html         → copy <head> contents into index.html
    copy-rewrites.html    → apply copy changes section by section
    image-optimisation.html → follow steps to convert images to WebP
    THIS FILE             → your implementation roadmap
