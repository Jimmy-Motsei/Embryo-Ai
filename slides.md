# Top‑Line Website Audit — Embryo‑AI

![MaruOnline Logo](assets/maru-logo.png)

**Prepared for:** Embryo-Ai  
**Prepared by:** Jimmy Motsei  
**Date:** 2025-09-21

---

## Executive Summary

• **Critical Issue:** Homepage returns empty HTML to non-JavaScript clients  
• **Impact:** Poor discoverability, slow mobile performance, blank social previews  
• **Priority:** Implement SSR/prerender for core routes within 3-5 days  
• **Quick Wins:** Add robots.txt, sitemap.xml, and essential meta tags  
• **Security:** Deploy security headers and verify contact form flows  
• **Context:** Built with Lovable platform, targeting South African mobile users

---

## What We Checked

• **Public-only scope:** No backend/CMS access used in this audit  
• **Rendering analysis:** Homepage HTML structure and JavaScript dependencies  
• **SEO surface:** robots.txt, sitemap.xml, and meta tag presence  
• **Performance assumptions:** Core Web Vitals risks for African mobile networks  
• **Accessibility surface:** Headings, landmarks, and semantic structure  
• **Security posture:** HTTP headers and third-party script hygiene

---

## Rendering & Discoverability

• **Empty HTML response** to non-JavaScript crawlers and social bots  
• **Client-side rendering** without server-side rendering (SSR) or prerendering  
• **Impact:** Search engines may not index content properly  
• **Social sharing:** Link previews will appear blank or incomplete  
• **Performance risk:** Late paint and hydration on slower mobile connections  
• **Solution:** Implement SSR or prerender service at CDN/edge level

---

## SEO Surface

• **robots.txt/sitemap.xml:** Could not be confirmed publicly  
• **Meta tags:** Not verifiable from non-rendered response  
• **Impact:** Missing files hinder discovery and timely indexing  
• **Social cards:** Titles/descriptions may not appear on shares  
• **Ranking snippets:** May be sub-optimal without proper meta tags  
• **Action needed:** Add robots.txt, sitemap.xml, and essential meta tags

---

## Performance

• **Mobile-first risk:** Slow LCP/INP due to JS-only rendering  
• **African context:** Variable bandwidth and higher RTTs amplify costs  
• **Bundle size:** Large JavaScript bundles delay critical rendering  
• **Hydration delay:** Content appears late on slower connections  
• **Priority:** Optimize hero/LCP media and critical CSS  
• **Strategy:** Progressive rendering and critical resource prioritization

---

## Accessibility

• **Semantic structure:** May not be available pre-render without SSR  
• **Headings hierarchy:** Ensure proper H1-H6 order in shipped HTML  
• **Landmarks:** ARIA labels and focus states need verification  
• **Keyboard navigation:** Test all interactive elements  
• **Color contrast:** Validate against WCAG guidelines  
• **Screen readers:** Ensure content is accessible to assistive technology

---

## Security & Trust

• **HTTP headers:** HSTS, CSP, X-Content-Type-Options not observable  
• **Platform risk:** Lovable hosting requires strict content policies  
• **Third-party scripts:** Need integrity checking and version pinning  
• **Form security:** Verify HTTPS endpoints for all form submissions  
• **Content policies:** Apply strict CSP starting with report-only mode  
• **Trust signals:** Add security headers to improve user confidence

---

## Recommendations — Rendering & Content

• **Implement SSR or prerender** for Home, Services, and Contact pages  
• **Add essential meta tags** in initial HTML: title, description, canonical  
• **Open Graph tags:** og:title, og:description, og:image, og:url  
• **Twitter cards:** Complete social media preview optimization  
• **JSON-LD structured data:** Organization and LocalBusiness markup  
• **Critical CSS:** Inline essential styles and defer non-critical

---

## Recommendations — Crawlability

• **robots.txt:** Allow core routes and reference sitemap.xml  
• **sitemap.xml:** Cover all key pages with proper priority/change frequency  
• **Google Search Console:** Submit sitemap and monitor indexing status  
• **Internal linking:** Ensure proper site architecture and navigation  
• **URL structure:** Use clean, descriptive URLs for better SEO  
• **Redirect mapping:** Handle any URL changes with proper redirects

---

## Recommendations — Performance & Accessibility

• **LCP optimization:** Modern image formats (WebP/AVIF), correct dimensions  
• **Critical resources:** Preload hero images with fetchpriority="high"  
• **JavaScript splitting:** Defer non-essential scripts and bundle optimization  
• **Font loading:** Use font-display: swap and limit font variants  
• **Accessibility testing:** Run axe audits and keyboard-only navigation tests  
• **Color contrast:** Ensure WCAG AA compliance for all text and UI elements

---

## Next Steps

**Option A — Quick Fixes (3-5 days):**  
• Implement SSR/prerender for critical routes  
• Add robots.txt, sitemap.xml, and essential meta tags  
• Deploy security headers and optimize LCP images  
• Basic accessibility checks and form testing  
• Provide HTML export for verification

**Option B — Deep Audit (1-2 weeks):**  
• Grant staged read-only access to CMS/build logs  
• Deliver Lighthouse/axe reports and Core Web Vitals trends  
• Complete header & redirect mapping analysis  
• Prioritized fix backlog (CSV) ready for developers
