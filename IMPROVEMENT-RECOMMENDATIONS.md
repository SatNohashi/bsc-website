# Website Improvement Recommendations

Remaining items identified during the BSC notes vs. website comparison audit. Each item includes an explanation of what it is, why it matters, and whether it should make it into the final product.

---

## SEO & Social Sharing

### OpenGraph / Social Meta Tags
**What:** Add `<meta property="og:title">`, `og:description`, `og:image`, `og:url`, and `twitter:card` tags to all pages so links shared on Twitter, Discord, Telegram, etc. display proper previews with title, description, and the BSC seal image.

**Why it should go in:** This is a near-zero-effort, high-impact change. Without it, any link shared to the constitution looks like a blank URL with no context. For a document that depends on public awareness and voluntary adoption, social sharing previews are essential. Every serious website has these.

**Recommendation: Yes — high value, low effort.**

---

## UX Improvements

### Switch Checklist from sessionStorage to localStorage
**What:** The interactive checklist on `checklist.html` currently uses browser session storage to save checkbox state. When the user closes the browser tab, all progress is lost. Switching to `localStorage` preserves progress across sessions.

**Why it should go in:** Anyone evaluating a system against 50+ checklist items will not finish in one sitting. Losing progress on tab close is a genuine usability bug, not a feature. This is a one-line JavaScript change (`sessionStorage` → `localStorage`).

**Recommendation: Yes — this is a bug fix, not a feature.**

---

### Print Stylesheet
**What:** Add `@media print` CSS rules so that the constitution, companion standards, and one-pager render cleanly when printed or saved as PDF from the browser. Hide navigation, adjust colors for white backgrounds, remove decorative elements, ensure readable font sizes.

**Why it should go in:** A constitutional document will be printed, archived, and referenced offline. Currently printing any page produces a dark-background mess with hidden navigation overlapping content. This is expected for any document-heavy site.

**Recommendation: Yes — important for a reference document.**

---

### Search Functionality
**What:** Add a client-side search feature that lets users search across all constitutional text, companion standards, commentary, and FAQ content. Could be implemented with a lightweight library like Lunr.js or a simple regex-based search over pre-built JSON.

**Why it should go in (maybe):** With 31 articles, 7 companion standards, 31 commentary entries, and 21 FAQ items, finding specific topics by scrolling is slow. A search would significantly improve usability for evaluators, developers, and researchers.

**Why it might not:** The site is intentionally dependency-free (no JS frameworks, no build tools). Adding a search library introduces complexity. The Table of Contents on the constitution page and the accordion labels on other pages already serve as a manual index.

**Recommendation: Consider for a future version. Not essential for launch, but valuable once the site sees regular use.**

---

### Governance Timeline Visual
**What:** Create a standalone visual diagram or timeline showing the 5/25/30-year governance windows. Currently this information is embedded in Article XIX text but has no visual summary.

**Why it should go in:** The governance ossification schedule is one of the most distinctive and important features of the constitution. A clear visual makes it immediately graspable. Could be a simple CSS-only timeline bar on the constitution or one-pager page.

**Recommendation: Yes — small effort, high clarity for a key concept.**

---

### Back-to-Top Button
**What:** Add a floating "back to top" button that appears when the user scrolls down on long pages (especially constitution.html with 31 articles).

**Why it should go in (maybe):** The constitution page is extremely long. The sticky table of contents helps on desktop, but on mobile (where the TOC collapses) scrolling back up is tedious.

**Why it might not:** The TOC sidebar already handles this on desktop. On mobile, the browser's native scroll-to-top gesture exists.

**Recommendation: Nice to have. Low priority but easy to add.**

---

### Anchor Copy-Link Buttons
**What:** Add a small "copy link" icon next to each article heading so users can easily share direct links to specific articles (e.g., `constitution.html#article-ix`).

**Why it should go in:** Evaluators, researchers, and commentators frequently need to reference specific articles. Currently the anchors exist in the HTML but there's no visible way to discover or copy them.

**Recommendation: Yes for a future version — useful for a reference document.**

---

### Breadcrumbs
**What:** Add breadcrumb navigation (e.g., "Home > Companion Standards > Breach and Restoration") on sub-pages.

**Why it should not go in:** The site has a flat structure — all pages are top-level. Breadcrumbs add visual noise without information value. The sticky navigation already provides clear context.

**Recommendation: No — unnecessary for this site structure.**

---

### Dark/Light Mode Toggle
**What:** Add a toggle button letting users switch between the current dark theme and a light reading theme.

**Why it should go in (maybe):** Long-form reading in dark mode causes eye strain for some users. A constitutional document meant for careful study would benefit from a light option.

**Why it might not:** Adds JavaScript complexity, requires maintaining two color schemes, and the current dark theme with gold accents is a strong brand identity.

**Recommendation: Consider for a future version. Not essential for launch.**

---

## Content Additions

### Changelog / Version History Page
**What:** Create a dedicated page showing the evolution from V1 through V7, including the 41 fixes applied in V7, and major changes between versions.

**Why it should go in (maybe):** Transparency about how the constitution evolved builds trust. Evaluators may want to understand why specific articles were added or changed.

**Why it might not:** The constitution is meant to stand on its own. Version history is available in the git repository. A changelog page could create confusion about which version is current.

**Recommendation: Low priority. The git history serves this purpose. Consider adding a brief "Version History" section to the About/FAQ page instead of a dedicated page.**

---

### RSS / Atom Feed
**What:** Add an RSS or Atom feed so followers can subscribe to updates (new companion standards, FAQ additions, compliance registry entries).

**Why it should go in (maybe):** For a living standard with ongoing updates, a feed helps engaged followers stay current without manually checking the site.

**Why it might not:** The site is largely static once published. Updates are infrequent. The GitHub repository already provides watch/notification features.

**Recommendation: No — too much infrastructure for the update frequency. GitHub notifications are sufficient.**

---

## Summary

| Item | Recommendation | Effort |
|------|---------------|--------|
| OpenGraph meta tags | **Yes** | Low |
| Checklist localStorage fix | **Yes** | Trivial |
| Print stylesheet | **Yes** | Medium |
| Governance timeline visual | **Yes** | Low-Medium |
| Search functionality | Maybe later | Medium-High |
| Back-to-top button | Nice to have | Low |
| Anchor copy-link buttons | Yes (future) | Low |
| Dark/light mode toggle | Maybe later | Medium |
| Breadcrumbs | **No** | N/A |
| Changelog page | Low priority | Medium |
| RSS feed | **No** | Medium |
