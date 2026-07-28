# Silver Capital Partners — marketing site

This repo is the live Silver Capital Partners marketing site (silvercapitalpartners.com),
deployed via Netlify. It is one hand-written static `index.html` — no build step, no
framework, no dependencies. Keep it that way.

## Before changing any UI

Read `design-system/README.md`. Never introduce a color, font, radius, or shadow that
isn't already defined in the `:root` block of `index.html`.

**The site's own `:root` variables are the operative values.** Use them; don't retype
hexes. Note the site names the accent `--slate-500` / `--slate-300`; the design system
calls the same two values `--silver-500` / `--silver-300`. Same colors, different label.

| Purpose | Value |
| --- | --- |
| Ink (hero, "how we work", footer) | `#0B0D0F` |
| Paper (page, contact) | `#F4F3EF` |
| White lift (capabilities band) | `#FFFFFF` |
| Accent on light | `#4C6570` |
| Accent on dark | `#8FA3AB` |
| Body copy | `#43464A` |
| Muted copy | `#676A65` |

That is the entire palette. There are no success/warning/error colors.

**Type: Georgia and Aptos only.** Georgia for headings, the wordmark, and person names —
always weight 400, always negative tracking. Aptos (falling back to Calibri, then Segoe UI)
for body copy, buttons, and uppercase eyebrows and labels at weight 500 with wide tracking.
Both ship with Windows and Office, so the site, the business cards, Word, PowerPoint, and
Excel all render identically with nothing to install. **Do not add a webfont, a Google
Fonts link, or a monospace face.**

**Structure.** Radius is 0 everywhere and shadows do not exist. Structure comes from 1px
hairlines: `rgba(11,13,15,0.2)` on light, `rgba(255,255,255,0.22)` on ink. Sections are
full-bleed, left-aligned against `--gutter`, never centered, never cards.

**Motion.** 180ms ease on color and border only. No transforms, no scroll animation, no
fades on load.

## Content rules

The firm offers one **Advisory** practice across five capabilities: growth capital, growth
strategy, senior & mezzanine debt, recapitalization, ownership transition.

**It does not offer M&A — do not add it to any copy.** There is no Approach page, no Team
page yet, and no site nav; the lockup sits inside the hero.

Copy is plain and declarative: short sentences ending in periods, sentence case, no emoji,
no jargon a business owner wouldn't say out loud. Uppercase with wide tracking is only for
eyebrows and labels, never headlines or buttons.

## Site structure

One scroll, in order: hero (ink) → capabilities (white) → how we work (ink) → contact
(cream) → footer (ink). The contact form posts to Netlify Forms.

## When the brand changes

`design-system/` is a snapshot copied from the Omelette design project, not a live link.
If you change a brand value here, say so in your summary so the source project and the
uploaded Claude Skill can be updated to match — otherwise they drift apart.
