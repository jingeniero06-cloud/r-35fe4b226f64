# Full SEO Audit — themightymo.com

**Client site:** [https://themightymo.com/](https://themightymo.com/)  
**Business:** Minneapolis web design / WordPress / SEO / eCommerce agency (The Mighty Mo!)  
**Business type:** Hybrid local ProfessionalService + B2B agency  
**Audit date:** 20 October 2026  
**Method:** curl + Lighthouse lab + specialist findings (Python launcher fetch hit intermittent Cloudflare 520; curl/browser-like fetch used instead). No GSC/GA4/CrUX credentials available this run.

---

## Executive summary

### SEO Health Score: **72 / 100**

| Category | Score | Weight |
|----------|------:|-------:|
| Technical SEO | 84 | 22% |
| Content Quality | 72 | 23% |
| On-Page SEO | 68 | 20% |
| Schema / Structured Data | 80 | 10% |
| Performance (CWV lab) | 55 | 10% |
| AI Search Readiness | 67 | 10% |
| Images | 88 | 5% |

**Weighted total ≈ 72.**

The site is a mature WordPress agency property with strong local entity markup on the homepage, a working Rank Math sitemap (289 URLs), and clear positioning as a Minneapolis web design agency. The biggest commercial risks are **mobile performance (Lighthouse 47, LCP 6.9s)**, a **service page that canonicalizes to the homepage**, and **gaps in AI/local enrichment** (no llms.txt, no FAQ schema, geo pages without JSON-LD, no review schema despite Trustindex reviews).

### Top 5 critical / high issues
1. **Mobile LCP ~6.9s / Performance 47** — lab fails CWV “good” by a wide margin (desktop is fine at 92).
2. **`/wordpress-website-design-services/` canonical → homepage** — unique URL may not rank.
3. **No homepage FAQ / answer-first blocks** — weak AEO/GEO citability.
4. **`/llms.txt` 403** — no LLM discovery file (and some AI user-agents get edge 403).
5. **Geo/service templates missing JSON-LD** — weaker local entity signals off the homepage.

### Top 5 quick wins
1. Fix canonical + unique title/H1/meta on `/wordpress-website-design-services/`.
2. Write real meta descriptions for About and Customer Success Stories.
3. Fix grammar on SEO service metas (“services is” → “services are”).
4. Trim/defer HubSpot, Clarity, GTM, Splide autoplay on mobile; compress hero media.
5. Add FAQ block + FAQPage schema on Home and SEO services; publish `/llms.txt` (200 text/plain).

---

## Business & niche

- **Detected:** ProfessionalService / Organization — Minneapolis web design agency.
- **Offerings:** Website design, WordPress, SEO, eCommerce, support.
- **NAP (site):** Phone `612-293-8629`; email `inquiries@themightymo.com`; Minneapolis / St. Anthony area address in footer + schema.
- **Sitemap:** 289 URLs — posts 233, pages 53, case studies 3.

---

## Technical SEO (84)

**Works:** HTTPS apex preferred; www/http 301; robots.txt + sitemap_index; index/follow; Brotli; HSTS + baseline security headers; SSR WordPress (not SPA); Rank Math.

**Gaps:** Mobile CWV lab poor; ~568 KB HTML + 33 scripts on home; public `wp-login.php` 200; no CSP; no IndexNow; PSI/CrUX not available this run (quota/API key).

See `findings/technical.md`.

---

## Content quality (72)

Homepage copy is substantive (agency positioning, case-study proof points, process). E-E-A-T cues exist (years in business, testimonials, Trustindex) but founding-year inconsistency (schema 2007 vs some external 2004 mentions) and “100% 5-Star Reviews” without structured review data weaken trust for AI and raters.

Large blog corpus (233 posts) needs a separate thin/outdated content pass.

See `findings/content.md`.

---

## On-page SEO (68)

Homepage on-page is solid. Highest-severity issue is the WordPress design service URL canonicalizing to `/`. Dual H1s and thin metas on key templates reduce clarity.

See `findings/on-page.md`.

---

## Schema (80)

Homepage `@graph` includes ProfessionalService, Organization, Place/Geo, OfferCatalog (9 services), WebSite + SearchAction. Medium: GeoCoordinates longitude has a leading space. Geo landing pages often lack JSON-LD. No Person, AggregateRating, or FAQPage.

See `findings/schema.md`.

---

## Performance (55 lab composite)

| | Mobile | Desktop |
|--|--------|---------|
| Performance | **47** | **92** |
| LCP | **6.9 s** | 1.6 s |
| CLS | 0.087 | 0.003 |
| TBT | 910 ms | 40 ms |

Main mobile cost: render-blocking CSS/JS, JS bootup (~3.7s: Splide, HubSpot, Clarity, GTM), ~2.8 MiB transfer, image delivery opportunities.

See `findings/performance.md`, `findings/visual.md`, `screenshots/`.

---

## Local SEO

NAP largely consistent; Maps embed present. Gaps: no GBP URL in `sameAs`; no AggregateRating despite Google reviews widget; geo pages without LocalBusiness/ProfessionalService JSON-LD.

See `findings/local.md`.

---

## AI search readiness (67)

Search bots tested return 200. No usable llms.txt (403). Narrative homepage vs answer-first. Strong Organization/`knowsAbout`/`sameAs` (social only). Add FAQ + citations + GBP in sameAs.

See `findings/geo.md`.

---

## Images (88)

Homepage: 12 images, **0 missing alt**. Remaining work is weight/format (Lighthouse image savings ~774 KB est. on mobile).

---

## Limitations
- Intermittent Cloudflare **520/403** for some Python/user-agent fetches.
- No GSC, GA4, or CrUX field data.
- Crawl inventory from sitemaps (289 URLs); not all 289 HTML pages fully rendered.
- PSI API rate-limited; lab Lighthouse used instead.

---

## Artifact index
- `findings/*.md` — specialist reports  
- `raw/` — HTML snapshots, sitemaps, parse JSON  
- `screenshots/` — desktop + mobile above-the-fold  
- `ACTION-PLAN.md` — prioritized roadmap  
- `audit-data.json` — machine-readable envelope for PDF  
