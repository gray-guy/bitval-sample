# Bitval — Affiliate page specification

> **Implementation target:** a single new page (e.g. `affiliates.html`) that replaces the old [`affiliates_2.html`](affiliates_2.html) experience. This document is the **source of truth** for content, section order, surfaces, and which [`landing.html`](landing.html) components to reuse. Visual and motion rules are defined in [`bitval-brand-brief.md`](bitval-brand-brief.md).

---

## 1. Brand context and rules of engagement

Bitval is **premium dark fintech**: calm, product-led, restraint over decoration. The affiliate page must use the same **Geist** / **Geist Mono** system, the same **CSS variable tokens** as the live landing, the **signature shader** (Unicorn Studio project `PFh4wQLH62Mb6eAsCFXO`) in **hero** and **final CTA only**, and the **glass frame** pattern for the hero. **Cream** (`#F2F1EC`) appears in **one** dedicated section (Your commission) — not as a default background. **No** gold/warm accent system, **no** purple/violet decorative washes, **no** emojis, **no** exclamation marks in marketing copy, **no** “Web3 / DeFi / to the moon” language. **Green and red** are reserved for market-style data (e.g. +% on a chip) only, not for decorative success/warning states.

**Program positioning (locked):** The Affiliate program is **application-gated and reviewed** (“rolling basis,” approval not guaranteed). The page does **not** compare Affiliate vs. standard Referral and does **not** show an “upgrade from Referral” path.

---

## 2. Reference cross-walk

### 2.1 Adopted from client references (`references/`)

| Reference | Pattern adopted | Bitval interpretation |
|-----------|-----------------|----------------------|
| Nexo | “Your gains” stat-style commission framing | Cream section with 3-up stats (`.markets-stats` typography), **illustrative** headline numbers — no fake dashboard UI |
| Nexo / Crypto.com / Coinbase | 3-step “How it works” | Reuse landing `.steps-stage` (Apply → Reviewed → Earn — partner language) |
| Nexo | Scannable partner benefits | Reuse landing `.why-grid` (4 cards, one cream) |
| Nexo | “Who we’re looking for” segmentation | New 4-cell hairline grid (same visual language as `.trust-strip`) |
| Crypto.com | Bold final CTA band | Reuse landing `.cta-card` + contained shader |
| All three | FAQ accordion | New FAQ block, tokens aligned to landing; **not** copying Crypto.com’s two-column FAQ layout literally — single column max-width OK |

### 2.2 Explicitly not adopted (brand brief conflicts)

| Reference element | Reason |
|--------------------|--------|
| Coinbase flat illustrations | Forbidden: generic illustrated marketing art |
| Crypto.com 3D bubbles / mascots | Forbidden: “no 3D icon packs,” not product UI |
| Nexo lifestyle photography | Forbidden: generic stock imagery |
| Full-page light/cream layouts | Bitval is dark-first; one cream moment only |

### 2.3 Kept from [`affiliates_2.html`](affiliates_2.html) (content / narrative only)

- Application-based partnership; rolling review; not every application approved.
- Pipeline: Apply → partnerships review → commission/terms confirmed → manage inside Bitval (no external portal).
- Audience buckets: Creators, Publishers, Communities, High-volume referrers.
- Commission on **trading fees** from referred users; rates agreed at review; paid in **USDT**.
- Core FAQ themes (expanded from 4 to 6).

### 2.4 Removed from [`affiliates_2.html`](affiliates_2.html)

| Removed | Rationale |
|---------|-----------|
| “Two tracks. One platform” + Referral vs Affiliate columns (`.diff-grid`) | User decision: drop comparison entirely |
| Fake dashboard (`.dash-frame`, link pills, tables, spark charts) | Misleading; references use **stat panels**, not product chrome |
| “Glance card” / duplicate KPI block with same fake numbers | Redundant; single hero float + cream stats sufficient |
| Upgrade-from-Referral CTA and copy | Dropped with comparison |
| Old tokens: `--accent #6172FF`, warm golds, `--success/--warn` for UI decoration | Replaced by brand-brief palette |
| Dynamic V-bars hero background JS | Replaced by landing’s shader + glass hero |

---

## 3. Page structure and section order

| # | Section ID (suggested) | Surface | Primary component source |
|---|------------------------|---------|--------------------------|
| 1 | `nav` | Dark `#09090B` | [`landing.html`](landing.html) — `.nav` |
| 2 | `hero` | Dark + shader + glass | `.hero-stage`, `.hero-bg`, `.hero-shader`, `.wrap.hero`, `.hero-frame`, `.hero-grid` |
| 3 | `trust` | Dark + hairlines | `.trust-strip`, `.trust-strip-row` (5 cells) |
| 4 | `commission` | **Cream** | New **affiliate** stage: cream canvas + copy block + **3-up stats** using `.markets-stats` / `.ms-key` / `.ms-desc` pattern from Markets section |
| 5 | `how` | Dark | `.steps-stage`, `.steps-inner`, `.steps-head`, `.steps-row`, `.step-card`, `.step-link` |
| 6 | `why` | Dark + 1 cream card | `.why-stage`, `.why-head`, `.why-grid`, `.why-card` (+ `--light` variant) |
| 7 | `who` | Dark + hairlines | **New** `.partner-strip` (see §5.7) — same grid/hairline behavior as `.trust-strip` but **4** cells |
| 8 | `faq` | Dark | **New** `.aff-faq` wrapper + `.faq-item` (details/summary), themed to tokens |
| 9 | `cta` | Dark + contained shader | `.cta-stage`, `.cta-card`, `.cta-card-bg`, `.cta-card-shader`, `.cta-card-veil`, `.cta-card-content` |
| 10 | `footer` | Dark | `.site-footer` — mirror landing; column links adjusted (§4.10) |

**Vertical rhythm:** `clamp(64px, 9vw, 110px)` between major sections (same as brand brief).  
**Container:** `.wrap` — `max-width: 1216px`, padding `24px` desktop / `16px` mobile.

---

## 4. Section-by-section blueprint

### 4.1 Navigation

| Property | Value |
|----------|--------|
| **Reuse** | `.nav`, `.nav-inner`, `.brand`, `.brand-logo`, `.nav-links`, `.nav-right`, `.btn-nav-login`, mobile `.nav-toggle`, `.nav-drawer`, `.drawer-cta` |
| **Links (desktop + drawer)** | `Markets` · `Trade` · `Rewards` · `Affiliate` · `About` (align with product IA; `Affiliate` is **current page** — use `.active` or `aria-current="page"` on Affiliate only if landing pattern supports it; affiliates_2 used `active` on Affiliate) |
| **Right CTAs** | `Log in` (`.btn-nav-login`) · **Primary:** `Apply now` (use `.btn-nav-signup` white pill style — same as landing “Sign up” but label **Apply now**) |
| **Behavior** | Sticky nav; add `.scrolled` to `#siteNav` when `scrollY > 12` (same script as landing). Mobile: hide desktop CTAs, show drawer with Log in + Apply now. |
| **Motion** | Match landing: nav transforms to floating pill when scrolled. |

**Exact strings**

- Nav links: `Markets`, `Trade`, `Rewards`, `Affiliate`, `About`
- Buttons: `Log in`, `Apply now`
- `aria-label` on header: `Primary` (or `Primary navigation`)

---

### 4.2 Hero

| Property | Value |
|----------|--------|
| **Structure** | Identical to landing: `.hero-stage` > `.hero-bg` + `.hero-shader` (Unicorn slot) + `.wrap.hero` > `.hero-frame` > `.hero-grid` **two columns**: `.hero-copy` (left) + `.hero-visual` (right). |
| **Left column** | Optional eyebrow: `<span class="badge"><span class="dot"></span>Partner program</span>` (reuse `.hero-frame .badge` from landing). **H1** `.hero-title`: copy below. **Sub** `.hero-sub`. **CTAs** `.hero-cta`: `.btn-primary.btn-lg` “Apply to become an affiliate”, `.btn-ghost.btn-lg` “Log in to your account”. **No** `.hero-stats` in hero (stats move to cream section to avoid duplication with references’ “gains” block). |
| **Right column** | **Single** `.float-card` only (no `.hero-phone-stack`, no phone images). Center card in `.hero-visual`; optional faint `.hero-phone-stack::before`-style **blue radial** under the card only (reuse hero glow pattern scoped to a wrapper). Card classes: `.float-card` + positioning class e.g. `.float-card--solo` (implementation). |
| **Float card content** | Head: `.fc-dot` + `.fc-label` `PARTNER COMMISSION`. `.fc-value` `$8,491` (illustrative). `.fc-meta`: `.fc-chip.up` `+34%` + `.fc-sub` `this month`. |
| **Shader** | Same mask + static fallback as landing `.hero-bg`; same `data-us-project` embed. |
| **Motion** | `.hero-copy > *` fadeUp stagger; `prefers-reduced-motion` collapse per landing. |

**Exact copy**

| Element | Text |
|---------|------|
| Badge (optional) | `Partner program` |
| H1 | `Built for partners with real ` **`<em>reach</em>`** `. |
| Sub | `An application-based partner program for creators, publishers, and communities. Earn ongoing commission in USDT as your audience trades on Bitval.` |
| Primary CTA | `Apply to become an affiliate` |
| Secondary CTA | `Log in to your account` |

**Title gradient:** `<em>` uses `linear-gradient(180deg, #FFFFFF 0%, #7AA8FF 55%, #4F86FF 100%)` + `gradientShift` 8s (same as landing `h1.hero-title em`).

---

### 4.3 Trust strip

| Property | Value |
|----------|--------|
| **Reuse** | `.trust-strip`, `.wrap`, `.trust-strip-row`, `.trust-cell`, `.trust-ico`, `.trust-label`, `.trust-desc` |
| **Grid** | **5** columns desktop; responsive collapse per landing (2-col tablet, 1-col mobile). |
| **Icons** | 1.5px stroke SVGs, same style as landing trust strip (simple geometric). |

**Exact copy (label · descriptor)**

1. **Application-based** · `Partnerships are reviewed for audience fit and distribution quality.`
2. **USDT payouts** · `Commissions accrue in USDT as referred users trade.`
3. **Lifetime attribution** · `Earn on qualifying activity from referred users you bring.`
4. **Transparent tracking** · `Clicks, conversions, and commissions visible in your workspace.`
5. **No external portal** · `Affiliate tools live inside your Bitval account.`

---

### 4.4 Your commission (cream section)

| Property | Value |
|----------|--------|
| **New wrapper** | e.g. `.aff-commission-stage` — **scoped cream tokens** exactly like `.markets-stage` in landing: `--m-bg:#F2F1EC`, `--m-text:#0B0F19`, `--m-text-dim`, `--m-text-muted`, `--m-border`, optional dotfield **only** if landing Markets uses it — **at most one** background accent per section (brand brief). Recommend: **subtle dotfield** matching `.markets-stage::before/::after` pattern OR plain cream — pick one in build. |
| **Layout** | `.wrap` + grid: **copy column** (`.markets-copy`-like) + optional **panel** not required — plan specifies **3-up stat panel** using `.markets-stats` structure. For affiliate, use **single column** layout: centered or left-aligned eyebrow + H2 + sub, then `ul.markets-stats` with **three** `li` items (same structure as landing Markets aside). |
| **Typography** | Eyebrow: `.markets-eyebrow` + `mono` → `COMMISSION`. H2: `.markets-title` with `<em>trades</em>` — on cream, use **ink → blue** gradient for `em` per landing: `linear-gradient(180deg, #0B0F19 0%, #4F86FF 100%)`. Sub: `.markets-sub`. |
| **Stats** | `.markets-stats` > three `li`: each `.ms-key` + `.ms-desc` (mono uppercase descriptions). |

**Exact copy**

| Element | Text |
|---------|------|
| Eyebrow | `COMMISSION` |
| H2 | `Earn as your audience ` **`<em>trades</em>`** `. |
| Sub | `Commission rates are agreed during partnership review — based on trading fees from referred users on qualifying activity. Payouts in USDT.` |
| Stat 1 key | `Up to 50%` |
| Stat 1 desc | `Rev share (at review)` |
| Stat 2 key | `Lifetime` |
| Stat 2 desc | `Referral attribution` |
| Stat 3 key | `USDT` |
| Stat 3 desc | `Commission payouts` |

**Legal tone:** “Up to 50%” is an **aspirational ceiling** for negotiation — keep sub copy tied to **review** and **qualifying activity**. No guaranteed income.

---

### 4.5 How it works

| Property | Value |
|----------|--------|
| **Reuse** | `.steps-stage`, `.steps-inner`, `.steps-head`, `.steps-eyebrow`, `.steps-title`, `.steps-sub`, `.steps-row`, `.step-card`, `.step-num`, `.step-ico`, `.step-link`, `.steps-cta` |
| **Steps** | 3 cards: **01 Apply** · **02 Reviewed** · **03 Earn** (align with gated positioning — not “Promote” as sole middle step; middle step is **review**). |
| **Icons** | Reuse landing step icon pattern (blue tile `.step-ico`, 1.5px stroke). |
| **Connector** | Animated `.step-link` lines + dot on scroll (`.steps-row.in-view`). |
| **Optional CTA row** | Single `.btn-primary.btn-lg` under steps: `Apply to become an affiliate` (matches landing “Create your account” placement). |

**Exact copy**

| Element | Text |
|---------|------|
| Eyebrow | `HOW IT WORKS` |
| H2 | `Apply. Get ` **`<em>reviewed</em>`** `. Earn.` |
| Sub | `Tell us how you reach traders. If approved, your commission structure is confirmed before you start — then you earn in USDT as referred users trade.` |
| Step 1 title | `Submit your application` |
| Step 1 body | `Share your audience, channels, and how you plan to drive qualified sign-ups. Applications are reviewed on a rolling basis.` |
| Step 2 title | `Partnership review` |
| Step 2 body | `We assess audience fit, reach, and content quality. If approved, your rates and terms are set before you go live — not every application is approved.` |
| Step 3 title | `Promote and earn` |
| Step 3 body | `Use your affiliate link inside Bitval. Track performance and commissions in one workspace — no separate portal.` |
| Steps CTA (optional) | `Apply to become an affiliate` |

---

### 4.6 Why partner with Bitval

| Property | Value |
|----------|--------|
| **Reuse** | `.why-stage`, `.why-head`, `.why-eyebrow`, `.why-title`, `.why-sub`, `.why-grid`, `.why-card`, `.why-card--light`, `.why-chip`, `.why-card-title`, `.why-card-desc` |
| **Layout** | Same 8-column grid as landing: featured **dark** card `why-security` span 3 + **cream** `why-fees` span 5 **OR** alternate: row1 dark+cream, row2 two cards — **mirror landing exactly**: `.why-security` (3) `.why-fees` (5) row1; `.why-referral` (4) `.why-flex` (4) row2. Map **content** to affiliate (chips + titles + bodies below). **One** `.why-card--light` (cream) — use for **“Inside Bitval”** or **“Dedicated support”** (pick one cream). |

**Exact copy**

| Card | Chip | Title | Body |
|------|------|-------|------|
| 1 (dark) | `Commission depth` | `Agreed at review` | `Rates are set with your partnerships contact based on audience fit and distribution — tied to trading fees from referred users.` |
| 2 (cream) | `Lifetime attribution` | `Earn as they trade` | `Focus on building your audience. Qualifying commission accrues from referred user activity on Bitval over the partnership term.` |
| 3 (dark) | `Inside Bitval` | `Your partner workspace` | `Links, reporting, and payout visibility live in your account — the same place you already manage trading and rewards.` |
| 4 (dark) | `Dedicated support` | `Partnerships, not tickets` | `Affiliate partners get a structured onboarding path and direct access to the partnerships team when you need help.` |

**Section header**

| Element | Text |
|---------|------|
| Eyebrow | `WHY BITVAL` |
| H2 | `Partner with an exchange built for ` **`<em>volume</em>`** `.` |
| Sub | `Spot, futures, and perpetuals — with fees and rewards aligned to how serious traders actually trade.` |

---

### 4.7 Who we partner with

| Property | Value |
|----------|--------|
| **New component** | `.partner-strip` (suggested): wraps `.trust-strip-row`-like grid with **4** `.trust-cell` children — reuse `.trust-label` + `.trust-desc` or shorter descriptor per cell. **No** icons required OR one minimal icon per cell matching `.trust-ico` size (16px). |
| **Desktop** | `grid-template-columns: repeat(4, 1fr)` with hairlines between cells (same border rules as `.trust-cell`). |
| **Mobile** | Stack or 2x2 per breakpoints similar to trust strip. |

**Section header**

| Element | Text |
|---------|------|
| Eyebrow | `WHO WE PARTNER WITH` |
| H2 | `Creators, publishers, and communities with ` **`<em>reach</em>`** `.` |
| Sub | `If you educate traders, curate markets, or run a community around trading — you may be a fit. High-volume referrers with consistent performance can also apply.` |

**Cells (label · descriptor)**

1. **Creators** · `YouTube · Newsletters · Podcasts`
2. **Publishers** · `Finance media · Comparison sites`
3. **Communities** · `Discord · Telegram · Forums`
4. **High-volume referrers** · `Existing Bitval users with strong referral activity`

---

### 4.8 FAQ

| Property | Value |
|----------|--------|
| **Wrapper** | `.aff-faq` or `.faq-stage` — `padding` matches other sections; `max-width` for accordion e.g. `720px` centered. |
| **Item** | `<details class="faq-item">` + `<summary>` + `.body` — **tokens**: borders `var(--hairline)`, background dark card `rgba`/`#141414`-adjacent consistent with landing cards; **open** state: subtle `--accent` border glow (match old affiliates intent but **#4F86FF** family only). **No** gold chevron. |
| **Interaction** | Chevron rotate + `prefers-reduced-motion`; first item **can** default `open` (optional). |

**Exact Q&A**

1. **Q:** `How is Affiliate different from the standard Referral program?`  
   **A:** `Affiliate is application-based for partners who distribute at scale. Standard Referral is available to all users after sign-up with a public tier structure. Affiliate commission rates and terms are agreed individually during partnership review.`

2. **Q:** `Who qualifies for the Affiliate program?`  
   **A:** `Creators, publishers, newsletter operators, community leads, and media partners with a credible audience and a clear plan to drive qualified sign-ups. High-volume referrers with consistent activity may also qualify. Submit an application and the partnerships team will assess fit.`

3. **Q:** `Is approval instant?`  
   **A:** `No. Applications are reviewed on a rolling basis. You will receive a decision by email. Approval depends on audience fit, reach, and distribution quality — not every application is approved.`

4. **Q:** `How is commission calculated?`  
   **A:** `Commission is calculated on trading fees paid by referred users on qualifying trades. Rates are agreed during your partnership review and are not publicly posted. Commissions accrue in USDT as referred users trade.`

5. **Q:** `When and how am I paid?`  
   **A:** `Payout schedules and thresholds are confirmed in your partnership agreement. You can track balances and payout history in your Bitval affiliate workspace.`

6. **Q:** `What promotional materials do I get?`  
   **A:** `Approved partners receive guidance on positioning and assets suitable for your channels. Request bespoke materials through your partnerships contact when your use case needs them.`

**FAQ header**

| Element | Text |
|---------|------|
| H2 | `Common ` **`<em>questions</em>`** |
| Sub lead | `Still need help? ` **Contact the partnerships team** (link — `#` placeholder). |

---

### 4.9 Final CTA

| Property | Value |
|----------|--------|
| **Reuse** | `.cta-stage`, `.wrap`, `.cta-card`, `.cta-card-bg`, `.cta-card-shader` (same Unicorn project), `.cta-card-veil`, `.cta-card-content`, `.cta-card-title`, `.cta-card-sub`, `.btn-primary.btn-lg`, optional `.cta-card-trust` list |

**Exact copy**

| Element | Text |
|---------|------|
| H2 | `Apply to partner with ` **`<em>Bitval</em>`** `.` |
| Sub | `Application-based. Reviewed on a rolling basis. Approval not guaranteed.` |
| Button | `Apply now` |
| Trust line items (optional, mono pills) | `Spot + Futures` · `USDT commissions` · `Built for partners` |

---

### 4.10 Footer

| Property | Value |
|----------|--------|
| **Reuse** | `.site-footer`, `.footer-inner`, `.footer-top`, `.footer-brand`, `.footer-tagline`, `.footer-social`, `.footer-nav`, `.footer-col`, `.footer-col-title`, `.footer-bottom`, `.footer-copy` |

**Adjustments vs landing**

- **Tagline:** Keep landing line or affiliate-specific: `Spot, futures, and rewards on a calmer, more capable exchange.` (same as landing — preferred for consistency.)
- **Column 1 — Company:** `Home` → link to `landing.html` (or `/`), `About Us`, `Contact`
- **Column 2 — Partners (replace “Support” or merge):** `Affiliate program` (current page anchor `#` or self), `Help & Support`, `FAQ` → anchor `#faq` on same page
- **Column 3 — Legal:** `Terms & Conditions`, `Privacy Policy`, add `Affiliate Terms` if product has it

**Exact footer column titles + links (example)**

| Column | Title | Links |
|--------|-------|-------|
| Company | `COMPANY` | Home, About Us, Contact |
| Partners | `PARTNERS` | Affiliate program (#), Help & Support (#), FAQ (#faq) |
| Legal | `LEGAL` | Terms & Conditions, Privacy Policy, Affiliate Terms |

**Copyright:** `© 2026 Bitval. All rights reserved.`

---

## 5. Component reuse manifest (from [`landing.html`](landing.html))

### 5.1 Reused as-is (class names)

| Class block | Use on affiliate page |
|-------------|----------------------|
| `.nav` … `.nav-drawer` | Header — labels and Apply now wiring only |
| `.hero-stage`, `.hero-bg`, `.hero-shader`, `.wrap.hero`, `.hero-frame`, `.hero-grid`, `.hero-copy`, `.hero-title`, `.hero-sub`, `.hero-cta`, `.btn-primary`, `.btn-ghost`, `.btn-lg`, `.hero-visual`, `.float-card`, `.fc-*`, `.badge`, `.dot` | Hero — minus phones; optional badge |
| `.trust-strip` … `.trust-desc` | Section 3 |
| `.markets-stage` **tokens** / `.markets-eyebrow`, `.markets-title`, `.markets-sub`, `.markets-stats`, `.ms-key`, `.ms-desc` | Section 4 — **new** wrapper class for affiliate commission section that **scopes** cream variables (copy `.markets-stage` cream setup or extract shared `[data-surface="cream"]`) |
| `.steps-stage` … `.step-link` | Section 5 |
| `.why-stage` … `.why-card-desc` | Section 6 |
| `.cta-stage` … `.cta-card-trust` | Section 9 |
| `.site-footer` … `.footer-copy` | Section 10 |

### 5.2 Extended / re-themed

| Source | Extension |
|--------|-----------|
| FAQ from old [`affiliates_2.html`](affiliates_2.html) | New FAQ: **strip** gold/`--accent-warm` pulse; use `--accent` / `--accent-2` only; borders `var(--hairline)` |

### 5.3 Net-new (build)

| Component | Role |
|-----------|------|
| `.aff-commission-stage` (name TBD) | Cream section wrapper + optional dotfield; houses commission copy + `.markets-stats` |
| `.partner-strip` + `.partner-strip-row` OR reuse `.trust-strip-row` with modifier `.trust-strip-row--4` | Who we partner with — **4** columns |
| `.faq-stage` / `.aff-faq` + `.faq-item` | FAQ layout + spacing; **details/summary** accessibility |

---

## 6. Token migration ([`affiliates_2.html`](affiliates_2.html) → brand brief)

| Old token / usage | New |
|-------------------|-----|
| `--accent #6172FF` | `--accent #4F86FF` |
| `--accent-2 #97A8FF` | `--accent-2 #7AA8FF` |
| `--accent-cyan #66D7FF` | `--accent-cyan #5EE6CC` (rewards / cyan dots only) |
| `--accent-warm`, `--accent-warm-2` | **Removed** — no gold badges, no warm pulse dots |
| `--success`, `--warn`, `--danger` for UI chrome | **Removed** for decorative pills; **market chips** only: dark `#7CE0A6` / `#C8302C` per brief |
| `--text-muted #8A93A6` | `--text-muted #7B8394` |
| Ghost button rgba based on old accent | `rgba(79,134,255,.12)` border `rgba(122,168,255,.26)` (landing `.btn-ghost`) |

**Headline `<em>` gradient (dark sections):**  
`linear-gradient(180deg, #FFFFFF 0%, #7AA8FF 55%, #4F86FF 100%)`, `background-size: 200% 200%`, `gradientShift` 8s.

**Cream section `<em>`:** `linear-gradient(180deg, #0B0F19 0%, #4F86FF 100%)` (match `.markets-title em` on landing).

---

## 7. Copy bank (all user-visible strings)

Use this table for legal/marketing review and CMS handoff.

### Nav + chrome

- `Markets` · `Trade` · `Rewards` · `Affiliate` · `About`
- `Log in` · `Apply now`

### Hero

- `Partner program` (badge, optional)
- `Built for partners with real reach.` (em on **reach**)
- `An application-based partner program for creators, publishers, and communities. Earn ongoing commission in USDT as your audience trades on Bitval.`
- `Apply to become an affiliate`
- `Log in to your account`
- Float: `PARTNER COMMISSION` · `$8,491` · `+34%` · `this month`

### Trust strip

- `Application-based` · `Partnerships are reviewed for audience fit and distribution quality.`
- `USDT payouts` · `Commissions accrue in USDT as referred users trade.`
- `Lifetime attribution` · `Earn on qualifying activity from referred users you bring.`
- `Transparent tracking` · `Clicks, conversions, and commissions visible in your workspace.`
- `No external portal` · `Affiliate tools live inside your Bitval account.`

### Commission (cream)

- `COMMISSION`
- `Earn as your audience trades.` (em on **trades**)
- `Commission rates are agreed during partnership review — based on trading fees from referred users on qualifying activity. Payouts in USDT.`
- `Up to 50%` · `Rev share (at review)`
- `Lifetime` · `Referral attribution`
- `USDT` · `Commission payouts`

### How it works

- `HOW IT WORKS`
- `Apply. Get reviewed. Earn.` (em on **reviewed**)
- `Tell us how you reach traders. If approved, your commission structure is confirmed before you start — then you earn in USDT as referred users trade.`
- `Submit your application` / body paragraph (see §4.5)
- `Partnership review` / body
- `Promote and earn` / body
- `Apply to become an affiliate` (repeat CTA)

### Why partner

- `WHY BITVAL`
- `Partner with an exchange built for volume.` (em on **volume**)
- `Spot, futures, and perpetuals — with fees and rewards aligned to how serious traders actually trade.`
- All four card chips, titles, bodies (§4.6)

### Who we partner with

- `WHO WE PARTNER WITH`
- `Creators, publishers, and communities with reach.` (em on **reach**)
- `If you educate traders, curate markets, or run a community around trading — you may be a fit. High-volume referrers with consistent performance can also apply.`
- Four cells (§4.7)

### FAQ

- `Common questions` (em on **questions**)
- `Still need help? Contact the partnerships team.`
- All six Q&A pairs (§4.8)

### Final CTA

- `Apply to partner with Bitval.` (em on **Bitval**)
- `Application-based. Reviewed on a rolling basis. Approval not guaranteed.`
- `Apply now`
- Optional: `Spot + Futures` · `USDT commissions` · `Built for partners`

### Footer

- `Spot, futures, and rewards on a calmer, more capable exchange.`
- Column titles: `COMPANY` · `PARTNERS` · `LEGAL`
- Links as §4.10
- `© 2026 Bitval. All rights reserved.`

---

## 8. Out-of-scope / explicit non-goals

1. **No** full browser-window dashboard mockup, fake tables, or invented “live” metrics beyond one illustrative `.float-card` and static commission stats.
2. **No** dynamic V-bars hero background or competing full-width aurora.
3. **No** Affiliate vs Referral comparison section; **no** “upgrade from Referral” CTA or `referral.html` cross-promotion in body (footer may link to product IA if required later — not in this spec).
4. **No** gold/warm accent system (`--accent-warm`, yellow badges, warm pulse dots).
5. **No** stock photography, 3D mascots, Coinbase-style illustrations, or floating coins.
6. **No** emojis, exclamation marks in marketing copy, or all-caps shouting (mono eyebrows excepted).
7. **No** second shader placement beyond hero + final CTA card.
8. **No** legal promise of income — all commission language conditional on review, eligibility, and qualifying activity.

---

## 9. Implementation notes (non-blocking)

- **Unicorn Studio:** Reuse the same embed as [`landing.html`](landing.html) for hero + CTA card; static fallback if script blocked.
- **Primary actions:** All “Apply” buttons target the same destination (TBD URL); wire consistently.
- **SEO:** `<title>Bitval — Affiliate Partner Program</title>` · meta description one sentence from hero sub.
- **Accessibility:** Landmark order `header` → `main` sections with `aria-labelledby` matching landing patterns; FAQ `details`/`summary` keyboard support.

---

*End of specification.*
