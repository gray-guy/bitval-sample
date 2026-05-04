# Bitval — Brand Brief

> **Premium dark fintech for a serious crypto exchange.**
> Coinbase-level clarity · Crypto.com-style polish · Bitval's product-led identity.

A working reference for designers building marketing surfaces, product shells, and ancillary assets across the Bitval ecosystem. This document distills what the live landing page already establishes into a shareable, opinionated system.

---

## 1. Brand Essence

| | |
|---|---|
| **Positioning** | The calmer, more capable crypto exchange. |
| **Promise** | *Turn every trade into a win.* |
| **Personality** | Confident · restrained · precise · modern · trustworthy |
| **Adjectives we want** | premium, refined, exchange-grade, product-led, calm |
| **Adjectives we avoid** | cyberpunk, neon, sci-fi, gamey, template |
| **One-line description** | *Spot, futures, and rewards on a calmer, more capable exchange.* |

**Core narrative arc.** Brand promise → product reveal → trust reinforcement → benefit framing → market activity → conversion. The hero builds the world; the product appears immediately as the first major payoff.

---

## 2. Logo System

### Primary logo

Wordmark `BITVAL` set in a custom geometric form. The leading **B** is the brand mark — rendered in a left-to-right linear gradient:

- `#8180E6` (soft violet-blue) → `#6CE3FF` (electric cyan)
- Gradient runs across the full glyph width (0%–100%, horizontal).
- Remaining wordmark sits in pure white `#FFFFFF` on dark surfaces.

### Construction notes

- Native dimensions: `139 × 24`, aspect-locked.
- Recommended marketing height: **22–28 px** in nav, **28–40 px** in hero contexts.
- Always preserve full clearspace equal to the cap height of the `B` on all sides.
- The B-mark may stand alone as an app icon, favicon, or social avatar — never reduce the wordmark below 18 px height.

### Color treatments

- **Default:** white wordmark + gradient B on dark.
- **Inverse:** ink wordmark `#0B0F19` + gradient B on the light-cream surface (`#F2F1EC`).
- **Single-color emergency only:** all-white or all-ink. Never recolor the B-mark gradient.

### Don't

- Do not stretch, shadow, outline, tilt, or animate the wordmark.
- Do not place the logo over busy product UI or the live shader without a clear glass surface beneath.
- Do not swap the B-mark gradient for a flat color on marketing surfaces.

---

## 3. Color Palette

### Foundation (dark surfaces)

| Token | Hex | Use |
|---|---|---|
| `--bg` | `#09090B` | Master canvas. Near-black with a hint of cool. |
| `--bg-2` | `#0D1017` | Elevated dark / panel base. |
| `--text` | `#FAFAFA` | Primary text on dark. |
| `--text-dim` | `#A1A1AA` | Body / secondary text. |
| `--text-muted` | `#7B8394` | Tertiary, captions, helper text. |

### Accent (the Bitval blue family)

| Token | Hex | Use |
|---|---|---|
| `--accent` | `#4F86FF` | Brand blue. Primary CTA glow, highlights. |
| `--accent-2` | `#7AA8FF` | Brighter blue. Used as gradient mid-tone in headlines. |
| `--accent-cyan` | `#5EE6CC` | Teal accent. Reserved for "rewards", live status, and reflective lighting. |
| `--accent-violet` | `#8C9CFF` | Violet highlight. Used **sparingly** as cool accent in shader / lighting. |

### Hairlines & glass

| Token | Value | Use |
|---|---|---|
| `--hairline` | `rgba(255,255,255,.09)` | Default 1px borders on dark. |
| `--hairline-strong` | `rgba(255,255,255,.16)` | Glass frame edges, badge outlines. |

### Light surface (Markets & "Low Fees" card)

A warm off-cream is used to break the dark rhythm — only on Markets section and one "why card" variant.

| Token | Hex | Use |
|---|---|---|
| `--m-bg` | `#F2F1EC` | Light cream canvas. |
| `--m-panel` | `#F8F7F2` | Elevated panel on cream. |
| `--m-text` | `#0B0F19` | Ink on cream. |
| `--m-text-dim` | `#5A6172` | Body on cream. |
| `--m-text-muted` | `#8A92A6` | Helper on cream. |
| `--m-border` | `rgba(11,15,25,.10)` | Hairline on cream. |

### Market state (always reserved for data, never decoration)

| Use | Dark | Cream |
|---|---|---|
| Up | `#7CE0A6` text, `rgba(124,224,166,.12)` fill | `#118A4E` text, `rgba(17,138,78,.08)` fill |
| Down | `#C8302C` text, `rgba(200,48,44,.08)` fill (inherits) | `#C8302C` text, `rgba(200,48,44,.08)` fill |

### Signature gradients

```css
/* Headline gradient — used on every <em> in section headings */
linear-gradient(180deg, #FFFFFF 0%, #7AA8FF 55%, #4F86FF 100%);

/* B-mark gradient */
linear-gradient(90deg, #8180E6 0.25, #6CE3FF 1.0);

/* Footer top hairline (multi-stop teal/blue) */
linear-gradient(90deg,
  transparent 0%,
  rgba(122,168,255,.35) 30%,
  rgba(94,230,204,.25) 50%,
  rgba(122,168,255,.35) 70%,
  transparent 100%);
```

### Color principles

1. Dark is the default. Cream is a deliberate moment, not a fallback.
2. Blue > teal > violet, in that order of frequency. Violet is a guest, not a host.
3. Green and red exist **only** for market states. Never as decoration.
4. The headline white→blue gradient is reserved for emphasized words inside headlines (`<em>`) and the brand mark — nowhere else.

---

## 4. Typography

### Type families

- **Display + UI:** **Geist** (`300 / 400 / 500 / 600 / 700 / 800`)
- **Mono / metadata:** **Geist Mono** (`400 / 500`)

System fallbacks: `ui-sans-serif, system-ui, sans-serif` for Geist; `ui-monospace, Menlo, monospace` for Geist Mono.

### Voice & weight rules

- **Headlines** — Geist 500 (medium), tight tracking (`-0.02em`), generous line height (`1.05–1.10`). Highlighted words use 600 weight + the white→blue gradient.
- **Body** — Geist 400, neutral tracking, line-height `1.5–1.6`, color `--text-dim`.
- **Buttons / labels** — Geist 600, `14–15px`.
- **Eyebrows / chips / metadata / numerics** — Geist Mono 500–600, uppercase, letter-spacing `0.08em`–`0.16em`. Always use Mono for tickers, prices, percentages, and data labels.

### Type scale (clamped, fluid)

| Role | Min → Max | Notes |
|---|---|---|
| Hero H1 | `36 → 72px` | line-height `1.05`, balance wrap |
| Section H2 | `28 → 48px` | line-height `1.08–1.10` |
| Card H3 | `17 → 28px` | letter-spacing `-0.01em` |
| Body | `15 → 19px` | line-height `1.55` |
| Caption / mono eyebrow | `11–12px` | uppercase, letter-spacing `0.14em` |

### Numerics

Use `font-variant-numeric: tabular-nums` for any column of prices, percentages, or counters. Sparkline labels and price columns are Geist Mono 600.

---

## 5. The Signature Shader

> **The single most identifiable Bitval surface.** A slow, drifting, soft-blue light field that lives behind the hero and re-appears as the closer in the final CTA. It is the brand's "light source" — the calm, ambient atmosphere that everything else floats inside.

### What it looks like

A real-time WebGL field rendered on a near-black canvas. Picture **a stratosphere lit from below**: deep navy at the edges, a slow swell of cool violet-to-blue light pooling near the upper-center, drifting laterally over many seconds. There are no sharp shapes, no sparkles, no orbs — only soft, structured movement, like watching weather build above a city at night.

**Visual anatomy:**

- **Base:** `#09090B` near-black canvas.
- **Cool glow zone:** a soft elliptical wash of `#4F86FF`-tinted blue rising from approximately `50% / -4%` of the frame, peaking at ~`40%` height before dissolving into the background.
- **Cooler highlight:** wisps of `#7AA8FF` and traces of `#8C9CFF` violet, drifting at different speeds — never moving in unison.
- **Tonal floor:** a deep navy `rgba(13,22,40,1)` underlay that stays still while the lighter layers drift.
- **Edges:** masked off completely. The shader never touches the bottom of its container.

**Mask shape (defines the "Bitval halo"):**

```css
mask-image: radial-gradient(ellipse 88% 62% at 50% -4%,
  #000 0%,
  #000 36%,
  rgba(0,0,0,.55) 52%,
  rgba(0,0,0,.2)  68%,
  transparent     78%);
```

This is critical: the shader is **only ever visible as an ellipse anchored above the frame**, fading to nothing before it reaches the content area. The result is a glow that *crowns* the content rather than competing with it.

### Movement

- Cycle length: **slow** — full atmospheric drift over ~12–20 seconds.
- No discrete loop. No sudden hits. No pulses or flares.
- One layer drifts left-to-right, another drifts diagonally, creating gentle parallax inside the field.
- Never pauses, never accelerates, never reacts to scroll or pointer.

### Where it appears

| Surface | Treatment |
|---|---|
| **Hero** | Full shader, anchored under the glass hero frame. The frame's blur softens its top edge. |
| **Final CTA card** | Same shader, contained inside a `28px`-radius rounded card. Re-masked to glow from the top of the card only. |
| **Anywhere else** | Don't. The shader is a *reveal*, not a texture. |

### Designer cheat-sheet

- Think: "premium fintech weather report," not "aurora borealis."
- If you'd describe it as colorful, vibrant, or psychedelic → wrong direction.
- If you'd describe it as quiet, expensive, atmospheric → correct.
- The shader is **always** behind glass (the hero frame, the CTA card). It is **never** the foreground.
- Static fallback: a single `radial-gradient(120% 80% at 50% -20%, rgba(13,22,40,.95) 0%, rgba(9,9,11,.92) 45%, #09090B 72%)` is acceptable when motion is unavailable — but only with the same elliptical mask.

### What kills it

- Saturated cyans, magentas, or pinks added "for energy."
- Visible loop seams.
- Movement faster than ambient drift.
- Removing the mask. (The shader without the mask reads as generic crypto-template aurora — exactly what we are not.)

---

## 6. Surface & Layout System

### Canvas

- Site canvas: `#09090B`. The brand never uses pure `#000`.
- Container: `max-width: 1216px`, side padding `24px` desktop / `16px` mobile.
- Vertical rhythm between sections: `clamp(64px, 9vw, 110px)`.

### The Glass Frame (the hero's hero)

The most important component on the marketing site. A `28px`-radius glass plate that floats above the shader and holds the hero's content.

```css
background:
  radial-gradient(120% 85% at 50% -15%, rgba(79,134,255,.14), transparent 58%),
  linear-gradient(165deg, rgba(255,255,255,.09) 0%, rgba(14,17,26,.38) 42%, rgba(8,10,15,.45) 100%);
border: 1px solid rgba(255,255,255,.14);
border-radius: 28px;
backdrop-filter: blur(32px) saturate(170%);
box-shadow:
  inset 0 1px 0 rgba(255,255,255,.10),    /* top inner highlight */
  inset 0 0 0 1px rgba(255,255,255,.04),  /* hairline inner */
  0 28px 72px -38px rgba(0,0,0,.5);       /* soft drop */
```

The same construction pattern is reused at `22px` radius for the staged product frame in Section 2.

### Background tiers (use sparingly)

1. **Premium dark base** — most sections. Just `--bg`.
2. **Dot field accent** — `1.2px` dots on a `14px` grid, masked to a soft ellipse, max opacity `0.55`. Used behind the framed product reveal.
3. **Localized blue glow** — a single radial of `rgba(79,134,255,.14–.22)`, only behind product UI or under the hero phone stack.
4. **Cream surface** — Markets section only. Same dot system but in `rgba(11,15,25,.16)`.

> Rule of thumb: at most **one** of the above per section, never stacked for "more energy."

---

## 7. Component Language

### Buttons

| Variant | Surface | Text | Notes |
|---|---|---|---|
| **Primary** | `#FFFFFF` | `#09090B` | Glow `0 14px 40px -18px rgba(255,255,255,.55)`. Subtle diagonal sheen on hover. |
| **Ghost (cool)** | `rgba(79,134,255,.12)` | `#EEF1FF` | `1px` border `rgba(122,168,255,.26)`. |
| **Nav login** | `rgba(255,255,255,.08)` | `#FFFFFF` | Border `rgba(255,255,255,.18)`. |
| **Nav signup** | `#FFFFFF` | `#09090B` | Used inline in the nav. |
| **Markets CTA** | `#0B0F19` | `#FFFFFF` | The dark CTA used on the cream Markets surface. |
| **Trade row** | `#F8F7F2` → `#0B0F19` on hover | `#0B0F19` → `#FFFFFF` | Inverts on hover. |

**Geometry:** all buttons are pill-shaped (`border-radius: 999px`). Default height `36px`, large `48px`. Padding `0 16px` / `0 22px`. Weight 600.

**Motion:** `translateY(-2px)` on hover, `scale(.98)` on press. Spring easing `cubic-bezier(.34, 1.56, .64, 1)`.

### Glass cards / float cards

Used for floating data overlays around the hero phone stack (e.g. *Open position +$1,248.32*, *Rewards $1,134.60*).

```css
background: linear-gradient(180deg, rgba(20,24,34,.78), rgba(14,17,26,.82));
border: 1px solid rgba(255,255,255,.10);
border-radius: 14px;
backdrop-filter: blur(18px) saturate(160%);
box-shadow: 0 18px 40px -20px rgba(0,0,0,.7);
```

Internals: a Mono uppercase label, a large numeric value (`18px / 600`), and a chip showing change %. Live status indicated with a pulsing colored dot — blue (`#4F86FF`) for positions, cyan (`#5EE6CC`) for rewards.

### Badges / pills

Mono uppercase, `30px` tall, rounded pill, `1px` hairline border, with an animated 6px dot. Used for `0% Fees`, section labels, etc. Always feels like a "live signal" — never a sticker.

### "Why Bitval" cards

Two variants exist intentionally:

- **Dark card** — `#141414`, white text, `28px` radius, `1px` rgba(255,255,255,.07) border.
- **Cream card** — `#F2F1EC`, ink text. Used to break the dark grid.

Each card carries a top "chip" in mono uppercase (`Built for trust`, `Pay less to trade`, etc.), then a 22–28 px bold title and a body description capped at ~42 characters wide.

### Markets table

The cream-surface data panel is one of the most distinct components.

- Outer panel: `#F8F7F2`, `1px` `rgba(11,15,25,.10)` border, `20px` radius, soft drop `0 24px 60px -40px rgba(11,15,25,.18)`.
- Tabs: pills with active state `#0B0F19` / white text.
- Rows: 6-column grid (icon · symbol · price · change · sparkline · CTA). `1px` hairline rule between rows.
- Token icons: 28 px circles with token-specific gradients (BTC orange, ETH indigo, SOL violet→green, etc.), with a Mono single-letter label inside.
- Sparklines draw in on enter (`stroke-dashoffset 1.1s`).

### Step cards (onboarding)

Three numbered cards (`01 / 02 / 03` in mono), each `18px` radius with a faint dark gradient fill. A tinted blue icon tile sits at the top. Cards are connected by an animated `1px` line that draws on scroll, with a glowing dot at the leading edge — the brand's signature "live circuit" detail.

### Trust strip

Five vertical cells separated by hairlines, each with a `16px` line icon, a Mono uppercase label, and a single short sentence. This is the brand's "scannable proof" pattern.

### Iconography

- Style: **1.5 px stroke**, no fills, rounded caps and joins.
- Geometry: simple, geometric, restrained — closer to Lucide / Phosphor than to filled, branded icon sets.
- Color: inherit from text (`currentColor`), tint blue (`--accent-2`) for active states only.
- Avoid: 3D icons, gradient-filled icons, illustrated icon-pack styles, emojis used as icons.

---

## 8. Motion Principles

The Bitval motion language is **slow, structured, and confident**. Motion is used to reveal information and reinforce hierarchy — never to entertain.

### Timing

| Easing token | Curve | Use |
|---|---|---|
| `--ease-out` | `cubic-bezier(.2,.7,.2,1)` | Default reveal, hover, scroll |
| `--ease-in-out` | `cubic-bezier(.65,.05,.35,1)` | Long state changes |
| `--ease-spring` | `cubic-bezier(.34,1.56,.64,1)` | Buttons, nav toggle bars |

### Patterns

- **Hero copy** stagger-fades up (`fadeUp .9s`) at 100ms increments per element.
- **Section reveals** fade + 28px lift on intersection (`.trade-reveal → .in-view`), 750ms.
- **Step connector lines** draw across `0.8s`, then a glowing dot opacity-pops 250ms later.
- **Markets rows** stagger in at 40ms intervals after the panel intersects.
- **Sparklines** draw in over 1.1s using `stroke-dashoffset`.
- **Headline gradient** drifts left/right over 8s, infinitely (`gradientShift`).
- **Live dot** pulses every 2.4s (`pulseDot`) — always blue, always slow.
- **Trade product frame** has a tiny scroll-linked parallax (`translateY` driven by viewport position) — max 12 px range.
- **Nav** transforms into a floating pill at scroll > 12px, with a `0.35s` choreographed change in radius, padding, max-width, and shadow.

### Reduced motion

All animations collapse to ≤1ms when `prefers-reduced-motion: reduce`. Hero copy, reveals, and parallax must all have static fallbacks.

---

## 9. Photography & Product Imagery

The exchange UI is the brand's hero asset. Always treat it that way.

- **Always staged**, never flat screenshots. Live in glass frames or with localized lighting.
- **Mobile screens** appear in a stacked, slightly rotated arrangement (front phone tilted -3°, back phone tilted +7°). Front phone has a stronger drop shadow, back phone is dimmed slightly (`brightness(.88) saturate(.92)`).
- **Floating data cards** orbit the device imagery — small, precise, never decorative.
- **Desktop trading screens** sit in the same glass frame system as the hero, with the live shader masked off so it doesn't intrude on the UI.
- A faint blue radial halo (`rgba(79,134,255,.18)`) underneath product imagery is allowed; nothing more.

**Forbidden:** floating coins, 3D illustrated mascots, generic crypto stock imagery, exchange "rocketship" metaphors, neon city skylines.

---

## 10. Tone of Voice

### Voice

Direct. Clean. Confident, but never hyped.

- Sentences are short and active.
- Numbers and financial terms are precise (e.g. "spot," "perpetuals," "futures," not "altcoins" or "moonshots").
- We address the reader as "you," and we say what Bitval *does*, not what it *believes*.
- Trader-first, but never insider-only. We explain without dumbing down.

### Voice in practice

| Surface | Example |
|---|---|
| Headline | *Turn every trade into a win.* |
| Sub-headline | *Bitval makes spot and futures trading simple with low fees, referral rewards, and discounts that grow with your volume.* |
| Section title | *Trade Instantly, Grow Consistently* — emphasized word ("Consistently") in the white→blue gradient. |
| Eyebrow | `WHY BITVAL` — Geist Mono, uppercase, letter-spaced. |
| Trust label | `Low Fees` — Mono, uppercase. |
| Trust descriptor | *Trade more efficiently.* — Geist sentence-case, single short line. |
| Step copy | *Sign up with your email and verify it in seconds. No long forms — just a few seconds to get started.* |

### Words we use

`spot`, `futures`, `perpetuals`, `leverage`, `volume`, `rewards`, `referral`, `secure`, `discount`, `markets`, `pair`, `position`.

### Words we avoid

`crypto-native`, `blockchain-powered`, `Web3`, `DeFi`, `to the moon`, `gem`, `degens`, `apes`, hashtags, exclamation marks anywhere in marketing copy, all caps for emphasis.

---

## 11. Application Examples (from the live site)

| Section | Lead component | Surface | Typography highlight |
|---|---|---|---|
| **Hero** | Glass frame on shader | Dark + shader | `Turn every trade into a win` (gradient on *win*) |
| **Trade reveal** | Framed product image | Dark + dot field | `Trade Instantly, Grow Consistently` |
| **Trust strip** | 5-cell hairline grid | Dark, no glow | Mono uppercase labels |
| **Why Bitval** | Mixed dark + cream cards | Dark canvas | One featured + three supporting |
| **Markets** | Cream data panel | Cream + dotfield | Mono prices, color-coded change chips |
| **Get started** | 3 step cards + connectors | Dark | Mono `01 / 02 / 03` |
| **Final CTA** | Rounded card with shader | Dark + contained shader | `Start trading with more control.` |
| **Footer** | Hairline-top, social pills | Dark | Mono col titles |

---

## 12. Do / Don't Cheat Sheet

### Do

- Use restraint. The brand's edge is what we leave out.
- Let the product UI carry visual interest.
- Keep the shader contained, slow, and behind glass.
- Use Geist Mono for anything numeric, ticker-style, or labeled.
- Reserve green/red for live market state only.
- Respect the headline gradient — only on the *emphasized* word.
- Keep CTAs few and decisive: one primary per surface.

### Don't

- No full-bleed aurora backgrounds.
- No purple/violet washes outside the shader's sanctioned role.
- No 3D icon packs, no rocketship metaphors, no illustrated mascots.
- No flat product screenshots — always staged in a glass frame.
- No motion that doesn't reveal information.
- No emojis in marketing copy. No exclamation marks. No all-caps shouting.
- No "Web3 / crypto-native / DeFi" buzzwords.

---

## 13. Quick Reference Tokens

```css
/* Colors */
--bg:#09090B; --bg-2:#0D1017;
--text:#FAFAFA; --text-dim:#A1A1AA; --text-muted:#7B8394;
--accent:#4F86FF; --accent-2:#7AA8FF;
--accent-cyan:#5EE6CC; --accent-violet:#8C9CFF;
--hairline:rgba(255,255,255,.09);
--hairline-strong:rgba(255,255,255,.16);

/* Cream surface */
--m-bg:#F2F1EC; --m-panel:#F8F7F2; --m-text:#0B0F19;
--m-text-dim:#5A6172; --m-text-muted:#8A92A6;
--m-border:rgba(11,15,25,.10);
--m-up:#118A4E; --m-down:#C8302C;

/* Easing */
--ease-out:cubic-bezier(.2,.7,.2,1);
--ease-in-out:cubic-bezier(.65,.05,.35,1);
--ease-spring:cubic-bezier(.34,1.56,.64,1);

/* Type */
font-family: "Geist", ui-sans-serif, system-ui, sans-serif;
font-family: "Geist Mono", ui-monospace, Menlo, monospace;

/* Radii */
button: 999px;
glass-frame: 28px (hero) / 22px (product) / 20px (markets panel) / 18px (step card) / 14px (float card);

/* Container */
max-width: 1216px; padding: 0 clamp(16px, 24px);
```

---

> **One sentence to brief any new asset against:**
> *Premium dark fintech, product-led, with a slow blue light overhead — calm, confident, and unmistakably Bitval.*
