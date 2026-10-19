# Action Plan — themightymo.com

**Health score:** 72 / 100  
**Goal:** Fix indexation cannibalization, recover mobile CWV, strengthen local + AI citation signals.

---

## Phase 1 — Critical / high (Week 1)

1. **Fix `/wordpress-website-design-services/`**
   - Self-canonical to that URL
   - Unique title, meta, H1 focused on WordPress website design (not identical to home)
   - Effort: S | Owner: WP/content

2. **Mobile performance sprint (target LCP &lt; 4s lab, then &lt; 2.5s)**
   - Defer/async non-critical JS; delay HubSpot/Clarity until interaction or idle
   - Stop Splide auto-scroll above the fold on mobile or replace with static hero
   - Compress/resize LCP image; serve AVIF/WebP
   - Effort: M–L | Owner: front-end

3. **One H1 on `/seo-services/`** + grammar fix on metas
   - Effort: S

---

## Phase 2 — High-impact (Weeks 2–3)

4. **Rewrite thin metas** (About, Customer Success Stories, any “Title = Meta” pages).
5. **Add FAQ + FAQPage schema** on Home and SEO Services (real questions: pricing model, timelines, WordPress vs rebuild, SEO process).
6. **Publish `/llms.txt`** as `text/plain` 200 (services, service areas, contact, key case studies). Allow AI search bots in Cloudflare if GPTBot/ClaudeBot still 403.
7. **JSON-LD on geo pages** (`/seo-services/minneapolis/`, St Paul/local templates) — ProfessionalService + areaServed.
8. **Review schema** — AggregateRating or Review from real Google reviews (or link prominently to GBP); add GBP URL to Organization `sameAs`.
9. **Fix GeoCoordinates longitude** leading space in Rank Math / schema output.

---

## Phase 3 — Content & authority (Month 2)

10. **Blog hygiene** — 233 posts: noindex or consolidate thin/outdated 2012-era posts; refresh money posts with answer-first intros.
11. **Case study expansion** — only 3 case-study URLs in sitemap; add measurable before/after (traffic, leads, speed) for AEO/GEO citations.
12. **Founding year consistency** — pick one year (2004 vs 2007) across About, schema, directories.
13. **Author/Person schema** for key staff on About + blog bylines.

---

## Phase 4 — Monitoring (Ongoing)

14. Connect GSC + GA4 (or share access) for index coverage and query tracking.
15. Monthly Lighthouse mobile + CrUX field check on Home, SEO Services, WordPress Design.
16. Rank track: “web design agency Minneapolis”, “WordPress agency Minneapolis”, “SEO services Minneapolis”.
17. Optional: IndexNow; CSP report-only; harden `wp-login.php` via Cloudflare WAF.

---

## Effort key
- **S** = &lt; half day  
- **M** = 1–3 days  
- **L** = multi-day / engineering  
