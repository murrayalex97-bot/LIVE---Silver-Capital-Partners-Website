# Silver Capital Partners — Design System

Silver Capital Partners is an independent advisory firm serving lower middle market
companies. It offers a single **Advisory** practice spanning five capabilities: growth
capital, growth strategy, debt, recapitalization, and ownership transition. It is a small,
principal-led firm — the design has to read as institutional and unhurried without
pretending to be a bulge-bracket bank.

## Sources this system was built from

Everything here was derived from artifacts produced inside this project — there was no
external brand book, Figma file, or codebase to import. **Every token value is taken from a
shipped artifact.** If a value isn't used somewhere real, it doesn't belong in `tokens/`.

| Source | Where |
| --- | --- |
| The deployed site — one scroll: hero → capabilities → how we work → contact → footer | `index.html` (this repo) |
| Business cards, email signature, Excel standard | the design project / the claude.ai Skill |

**No logo file was supplied.** The mark used throughout is a plain square rotated 45°
(a CSS `transform: rotate(45deg)`) set beside the wordmark. It is a placeholder-grade
device, not a delivered logo — see *Iconography*.

**M&A is not offered.** It was removed from the practice list deliberately, to avoid
regulatory and semantic overlap. Do not reintroduce it in copy.

---

## Content fundamentals

**Voice: plain, declarative, unadorned.** The firm sells judgement, so the copy never
oversells. Sentences are short and end in periods. No exclamation marks, no emoji, no
jargon that a business owner wouldn't use out loud.

**Person.** "We" for the firm, "you" for the client. Never "our team is passionate about."

**Headlines are statements, not slogans.** They read as if spoken across a table:

> Advice for raising capital, restructuring it, or planning what's next.
> Independent by design.
> What clients come to us for.
> Start a conversation.

**Say the unflattering thing.** The differentiators are all restraint —
"A clear read on your options, including the option to do nothing." /
"No fee, no obligation." / "No product to sell, no balance sheet to feed."
Copy that admits a limit is more on-brand than copy that claims a strength.

**Casing.** Sentence case for everything a human reads as a sentence. UPPERCASE with wide
tracking *only* for eyebrows, nav, and metadata labels — never for headlines or buttons.

**Numbers.** Spelled out below ten in prose ("five capabilities"). Phone numbers in US
format with parentheses: `(214) 886-4699`.

**Ampersands** are avoided in running prose.

---

## Visual foundations

**The whole system is: ink, paper, one silver accent, hairlines, and a diamond.
Nothing else.**

### Color
Three surfaces — `--paper` `#F4F3EF` (warm off-white, the default page), `--paper-white`
`#FFFFFF` (the lifted band, used for the Capabilities section and print pieces), and
`--ink-900` `#0B0D0F` (near-black, used full-bleed for the hero, "How we work", and the
footer). Sections alternate cream → white → ink → cream so the page reads as bands, not
cards.

One accent: silver. It is **two values, not one**, because no single grey passes contrast
on both surfaces — `--silver-500` `#4C6570` on cream (5.3:1), `--silver-300` `#8FA3AB` on
ink (7:1). The same split applies to muted text: `--ink-500` `#676A65` on cream,
`--ink-400` `#8FA3AB` on ink. Picking one and using it everywhere is the mistake this
system exists to prevent. There are no semantic success/warning/error colors.

### Type — one stack, everywhere
**Georgia and Aptos. Nothing else, on any surface.** Both ship with Windows and Office, so
the live site, the business cards, the email signature, Word memos, PowerPoint decks, and
Excel models all render identically on any firm machine with nothing to install and nothing
to load.

- *Georgia* (serif) for every heading, the wordmark, and person names. Always weight 400 —
  never bold. Always negative tracking (`-0.01em` to `-0.02em`).
- *Aptos* (falls back to Calibri, then Segoe UI) for body copy, buttons, and all uppercase
  eyebrows and labels — weight 500, tracking `0.16em`–`0.42em`.
- *Aptos Narrow* is the spreadsheet cut (see `excel/`).

**No webfonts. No Google Fonts link. No monospace.** Early drafts used Newsreader, Inter,
and JetBrains Mono; the deployed site never did, and they have been removed. A monospace
face read as tech, not finance. Do not reintroduce one.

### Shape, borders, shadows
**Radius is 0 everywhere. Shadows do not exist.** Structure comes entirely from 1px
hairlines: `rgba(11,13,15,0.2)` on light, `rgba(255,255,255,0.22)` on ink. Lists are rows
divided by rules, not cards. The capability grid is separated by hairline gutters, not
borders around boxes.

### Layout
Full-bleed sections with a fluid gutter (`clamp(24px, 6vw, 88px)`) — content is left-aligned
against that gutter and never centered. Vertical rhythm is `clamp(64px, 9vw, 116px)` per
section. Measures are capped in `ch`: `--measure-hero` 30ch, `--measure-heading` 22ch,
`--measure-body` 56ch, `--measure-fine` 66ch (legal fine print).

### The diamond
A square rotated 45°, in four sizes (5/9/15/30px). It appears as: the logo mark, the
bullet on capability headings, and — at 200–360px with a 1px hairline border at 9–13%
opacity — as the footer's background motif. It is always a rotated `<div>`, never an SVG
or glyph.

### Motion, hover, focus
Restrained: 160–180ms `ease` on color and border only. No transforms, no bounces, no
scroll animation, no fades on load.
- Links / nav: grey → white (on ink) or ink → silver `#4C6570` (on paper).
- Solid button: paper background on ink.
- Ghost button: border 28% → 100% opacity.
- Inputs: bottom rule only; it turns silver on focus.
There are no pressed states and no disabled styling defined yet.

### Imagery
There is none today, deliberately. No stock photography, no illustration. If imagery is
added it should be black and white, architectural or documentary, never a handshake. Team
headshots, when supplied, are the one planned exception.

---

## Iconography

**The system has no icon set and does not need one.** Two devices do all the work:

1. **The diamond** (rotated div) — logo mark and list bullet.
2. **A right arrow, `→`** (the Unicode character) — appended to text links.

No icon font, no Lucide/Heroicons/Feather, no SVG sprite. If a future surface genuinely
needs icons, use a hairline stroke set at 1px to match the rule weight — and add it here
first. Emoji are never used.

---

## What's in here

- `README.md` — this file. The rules.
- `styles.css` — the entry point; `@import`s every token file.
- `tokens/` — `colors.css`, `typography.css`, `spacing.css`, `lines.css`, `motion.css`
- `guidelines/` — foundation specimen cards. Open any of them in a browser to see a value.

This is a **trimmed copy** for the website repo: the rules and the values, nothing else.
The full system — React components, business card and email signature kits, the Excel
formatting standard — lives in the Silver Capital design project and is uploaded to
claude.ai as a Skill. Reach for that when making a card, a deck, a memo, or a model.

## Caveats

- **No real logo.** Wordmark + rotated square is a stand-in. Supply a mark and it should be
  swapped everywhere.
- **Fonts are Office-native** (Georgia, Aptos/Calibri) — chosen for consistency across web,
  Word, PowerPoint, and Excel rather than for typographic distinction. If the firm ever
  licenses a display serif, it should replace Georgia in `--font-display` only.
- **No dark/light theming** — ink and paper are compositional choices per section, not a mode.
- **No Team page yet.** Bios and photos for Tan Parker and Brett Gilbert are the largest
  remaining gap in the boutique pitch.
