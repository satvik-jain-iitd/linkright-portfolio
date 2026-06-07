# CLAUDE.md — Portfolio Conversion Brief

> **For the coding session working in this repo.** This file is the design
> direction for `Portfolio.html`. A separate design/conversion reviewer wrote it.
> Goal of this portfolio: **get Satvik Jain interviews for Senior/Lead PM roles
> at FAANG-tier companies** (Google, Amazon, Meta, Netflix, etc.).
>
> Implement the items below in priority order. Preserve every verifiable fact and
> metric. **Do not** sanitize the authentic voice into generic AI prose — the
> voice is the differentiator. Keep the navy/teal design system, animated
> pipeline, accordion pattern, and scroll-reveal.

## Current state
`Portfolio.html` is currently byte-identical to the original design prototype
(only HTML-entity encoding differs). **Zero conversion improvements applied yet.**
It reads as a well-written resume, not a PM portfolio. The work below fixes that.

## Owner decisions (already locked — do not re-litigate)
- **Artifacts available:** Satvik has real, redact-able product visuals
  (dashboards, Figma frames, roadmaps). Wire them in. He will drop image files
  into `assets/` — reference them; if a file is missing, render a styled
  placeholder, never a broken `<img>`.
- **Father-death beat:** keep it, but move it OUT of the Story opener and trim to
  ~2 sentences as a "why I operate this way" aside in a later chapter.
- **GPA:** remove the `6.43 CGPA` number entirely. IIT Delhi brand stays.

---

## P0 — conversion-critical (do first)

### P0.1 — Reorder sections
New order: `Hero → Logo strip → Work → Story → Credentials → Diary → Contact`.
Move **Work above Story** (proof before memoir). Update nav order + scroll order.
- ✓ Nav links reordered. ✓ Active-nav IntersectionObserver still highlights correctly.

### P0.2 — Add product artifacts to each case card (biggest single lever)
In every expanded `.case-body`, add a `<figure>` with a redacted dashboard /
Figma frame / roadmap + a 1-line `<figcaption>`.
- ✓ All 4 real cases (Qatar, Walmart, AmEx, LinkRight) show ≥1 visual.
- ✓ Images: rounded 8px, 1px border, `loading="lazy"`, capped height, `onerror` placeholder.
- ✓ AutoFlow + Miraya (in-progress) get a simple diagram or stylized "in development" placeholder.

### P0.3 — Cut the GPA line (Chapter: Theory vs. Practice)
Delete: `"I graduated with a 6.43 CGPA in Civil Engineering — not a number I hide."`
Replace the chapter opener with:
> IIT Delhi was academically hard for me. Not because I lack the horsepower —
> because I learn by doing, not from textbooks. I scored 10/10 in every single
> practical lab I ever sat in.
- ✓ No GPA number anywhere in the file. ✓ IIT Delhi retained.

### P0.4 — Reposition the father-death beat
Don't lead the Story with it. Make **Chapter 01 = "The Theory vs. Practice
Problem."** Fold the father paragraph into a later chapter as a brief (≤2 sentence)
"why I operate this way" aside — not a headline.
- ✓ First content in Story is a professional insight, not childhood trauma.
- ✓ The line stays in the file, just repositioned + trimmed.

### P0.5 — Resume download + sticky access
Nav: add a persistent `Résumé ↓` link (sticky, always visible). Hero: add a
secondary CTA `Download résumé (PDF)`. Link `resume.pdf` at repo root
(Satvik will add the PDF). Open in new tab.
- ✓ Résumé reachable without scrolling.

---

## P1 — strong lift

### P1.1 — Scannable hero positioning line
Add ABOVE the existing prose descriptor (keep the prose as secondary):
> I ship product into high-stakes ambiguity — solo PM on a 100M-account risk
> platform, the insight layer on a $32M government deal, ranked #1 product analyst
> globally at Sprinklr.
- ✓ Reads in one glance.

### P1.2 — Reframe the 3 hero stats (outcomes, not output)
Drop `60+ features` (output metric — weak PM signal). Use:
| Number | Label |
|--------|-------|
| `100M+` | accounts on a platform I owned solo |
| `$32M`  | largest deal in Sprinklr history |
| `78→53` | Qatar's national e-gov rank, in months |
- ✓ Every stat is an outcome corroborated elsewhere on the page.

### P1.3 — Logo strip under hero
`Sprinklr · American Express · Walmart · Government of Qatar · IIT Delhi` —
grayscale, low-key, small. Instant credibility before they read prose.

### P1.4 — Add the published-PRD proof
Horizon is a *published* PM document — strong signal. Add an `↗ Published PRD`
link (in the LinkRight card or a small "Selected writing" line):
`https://www.councilonsustainabledevelopment.org/post/horizon-a-gamified-stock-market-app-for-new-retail-investors`

### P1.5 — Trim Build Diary 14 → 6 + "Show more"
Heavy overlap (Gold Medal repeats in hero + Ch03 + Diary). Keep 6: Midnight in
Doha · An Award Before I Shipped · The Week the Strategy Changed · 147 People
Said Yes · pip install linkright · Zero Days Unemployed. Rest behind a toggle.

---

## P2 — polish (hiring managers notice)
- **Contact:** move `AI Songs` to the footer (distracts next to LinkedIn/GitHub).
  Point the GitHub link at the **LinkRight repo specifically**, not the profile.
  Add an availability line: `Based in [CITY] · open to [remote/relocation] · [work-auth]`
  (Satvik to confirm the exact values).
- **Contrast:** bump `--text-muted` from `#475569` → ~`#64748b` (labels too dim on navy).
- **Mobile pipeline:** verify the hero SVG collapses to vertical / 2-col below 768px.
- **GitHub Pages:** ensure the site serves at root — `index.html` already exists;
  confirm it routes to the portfolio.

---

## Definition of done
P0 + P1 = ~90% of the conversion gain. P0.2 (artifacts) is the highest-impact
single change — prioritize wiring those visuals. After implementing, the page
should pass the 3-second test: a skimming recruiter instantly sees **level,
biggest proof, and real product work** — not a wall of personal narrative.
