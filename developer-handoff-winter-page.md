# Developer Handoff — Winter Landing Page (Villa Adela / Sol Privado)

**What this is:** a complete, production-ready landing page (design, copy and SEO finished). Implementation is porting it into the live WordPress site — not a design or content build. It has been delivered this way deliberately, to keep implementation time to a minimum.

- **Live preview:** https://pouste.github.io/solprivado-lowseason-concept/
- **Source:** GitHub repo `PouSte/solprivado-lowseason-concept` (`index.html` + images)
- **Brand:** navy `#1E3A52` · terracotta `#C0561E` · gold `#BFA07D` · cream `#FBE7DB` · Playfair Display + Lato

---

## A. Already built to spec (no work needed)

These are done and verified — please preserve them when porting:

- **Semantic structure:** `<header>` (hero) → `<main>` → `<section>`s; single `<h1>` with a correct heading hierarchy.
- **FAQ schema:** valid JSON-LD `FAQPage` whose text matches the visible FAQ 1:1 (Google requirement for rich results).
- **Accessible FAQ:** native `<details>/<summary>` accordion — keyboard-operable, `focus-visible` styling, no JavaScript dependency.
- **Images:** every `<img>` has descriptive `alt`, plus `loading="lazy"`, `decoding="async"` and intrinsic `width/height` (CLS-safe).
- **Motion:** `prefers-reduced-motion` respected on all animations.
- **Responsive:** breakpoints at 880 px and 520 px; mobile-first grids collapse cleanly.
- **Contrast:** text labels meet WCAG AA on light backgrounds (a dedicated `--gold-ink` token is used for small gold text).
- **Social preview:** Open Graph + Twitter Card meta and `theme-color` set.
- **Content consistency:** pool/jacuzzi, occupancy and cancellation wording are internally consistent and aligned with the FAQ.

---

## B. To complete on the live build (checklist)

1. **Remove the `noindex` tag.** It is intentionally set on the GitHub concept so it does not compete with solprivado.com. On live it **must** be removed, or Google will ignore the page and the FAQ schema.
2. **Set the final URL** — recommended `solprivado.com/winter` (clean, SEO-friendly). Then update `canonical`, `og:url` and `og:image` to the live domain. (See the `DEV NOTE` comment at the top of `index.html`.)
3. **Optimise images:** convert the `.jpeg`s to WebP and compress to **< 300 KB each**. This is the single biggest performance gain; filenames are referenced relatively, so keep them in the same directory.
4. **Add a favicon** (none is referenced yet).
5. **Deep-link the CTA buttons.** "Check availability" currently points to the homepage (`solprivado.com`); link both buttons to the live booking/availability module.
6. **(Optional) Merge CSS tokens.** The FAQ block carries its own scoped `.va-faq` styles so it could be dropped in safely. On the live build these may be merged into the global stylesheet — this is a deliberate choice, not duplication.
7. **Check image filename case** on the live host (case-sensitive). Repo uses all-lowercase names.

---

## C. Please do not change (locked content)

The following copy is finalised and approved — if edited, it can create guest disputes or break the schema:

- **Pool/jacuzzi policy:** pool is unheated as standard, heating is a paid extra booked in advance; both jacuzzis are heated and included. Do not advertise the pool as "heated/included".
- **Occupancy:** maximum 8 guests, licence-backed; no extra beds.
- **Cancellation policy** wording (30% non-refundable deposit, balance schedule, etc.).
- **FAQ:** if any FAQ answer text is changed, the matching JSON-LD `Answer.text` must be updated identically — the two must stay byte-for-byte aligned.

---

**Net effect:** design, copy, SEO structure and accessibility are complete. The remaining work is configuration and asset optimisation. Estimated effort is implementation, not creation.
