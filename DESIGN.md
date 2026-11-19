# DESIGN.md — luxnarayan.com

> Big type on warm paper. One blue circle, one yellow room, one pink button.

The single design reference for the site. Nothing is built from it yet.

**Two rules decide every conflict:**

1. **Brand wins on colours and fonts.** The brand is StreamAlive's: values below were read from the live stylesheet on streamalive.com on 2026-11-16.
2. **The references win on layout and feel.** The five files in `reference sites/` (Bpowell, OFF+BRAND, Stink Studios, Aaron Poe & Co, Karl).

Any choice that is not a straight read from one of those sources is recorded in the [decision log](#decision-log) at the end.

---

## 1. The feel

Four of the five references agree, and that agreement is the core of this system:

- **Type leads, pictures support.** Headlines are very large and tightly set; small wide-tracked labels mark each section. Images are few and each one shows a real thing (see Imagery below). No stock photos, no decorative icons.
- **Flat.** No shadows, no gradients, no boxed cards. Structure comes from hairlines, whitespace and full-bleed changes of surface.
- **Left-pinned and sparse.** One column of text held to the left margin, with generous empty space to the right. A handful of elements per screen.
- **Links, not buttons.** Actions are plain text links with an arrow. There is exactly one filled button, described below.

Karl is the outlier, and supplies the play that suits a founder who also does stand-up: **one flat, saturated, full-bleed colour field** and **one large circle** used as a focal shape.

| Reference | What this site takes from it |
|---|---|
| Bpowell | Oversized left-pinned headlines, tiny tracked section labels, white/black full-bleed alternation, nav items spread across the full width |
| OFF+BRAND | Warm paper canvas, one chromatic object in the hero, hairline-divided grids, ghost links with arrows |
| Stink Studios | A serif reserved for big statements, flat ink sections, interactivity shown by an underline only |
| Aaron Poe & Co | Pill-shaped nav element, narrow reading column for long text, the accent colour used as a whisper |
| Karl | One full-bleed saturated section, the circle as a compositional shape, headline lines stacked tight |

---

## 2. Colours

All values are StreamAlive's own tokens. Contrast ratios are measured; 4.5 or higher passes for body text, 3 or higher for large text.

### Surfaces

| Name | Value | Token | Role |
|---|---|---|---|
| Paper | `#fbf8f3` | `--paper` | Default page canvas |
| Paper 2 | `#f4efe6` | `--paper-2` | Quiet second light surface (StoryMining) |
| Ink | `#0f0f12` | `--ink` | Inverted full-bleed sections; all text on light surfaces |
| Signal Yellow | `#ffea00` | `--yellow` | The one saturated full-bleed section (Comedy) |

### Text and lines

| Name | Value | Token | Role |
|---|---|---|---|
| Ink | `#0f0f12` | `--ink` | Text on Paper, Paper 2 and Yellow (18.1, 16.7 and 15.5 to 1) |
| Paper | `#fbf8f3` | `--paper` | Text on Ink (18.1 to 1) |
| Ink 3 | `#66646c` | `--ink-3` | Muted text on light surfaces (5.5 to 1) |
| Mist | `#a9a8b0` | `--mist` | Muted text on Ink (8.1 to 1) |
| Rule | `#dcd3c4` | `--rule` | 1px hairlines on light surfaces |
| Rule Dark | `#2e2d33` | `--rule-dark` | 1px hairlines on Ink |

### Accents

| Name | Value | Token | Role | Limits |
|---|---|---|---|---|
| Pink | `#ff0064` | `--pink` | Section-label colour on Ink; accent underline on links | Never as a fill behind white text (3.9 to 1) |
| Pink Strong | `#e6005c` | `--pink-strong` | Fill of the newsletter button, white label (4.7 to 1) | Newsletter button only |
| Pink Ink | `#d4004f` | `--pink-ink` | Section-label colour and accent text on Paper (5.1 to 1) | Labels and short accents, never body text |
| Blue | `#0086ff` | `--blue` | The hero circle; keyboard focus ring | Ink text may overlap it (5.3 to 1); white text may not (3.6 to 1) |
| Yellow | `#ffea00` | `--yellow` | The Comedy section canvas; the "Mildly NSFW" tag on Ink | One full-bleed section per page |

### Colour discipline

- Paper and Ink carry the page. Pink, blue and yellow each get **one job** and appear nowhere else.
- No gradients, no tints, no colour on hover. Hover is an underline.
- No automatic dark mode. The page already alternates light and dark sections by design.

---

## 3. Fonts

Both families are StreamAlive's. Both are free on Google Fonts.

| Family | Token | Role |
|---|---|---|
| **Inter** (variable) | `--font-sans` | Headlines, body, nav, labels, links. The workhorse and the display face. |
| **Newsreader** (variable) | `--font-serif` | Statements only: one large serif sentence per section at most, plus italic emphasis and book titles. |

Fallbacks: Inter → `ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, sans-serif`. Newsreader → `ui-serif, Georgia, "Times New Roman", serif`.

### Type scale

| Role | Family | Weight | Size (phone → desktop) | Line height | Tracking | Used for |
|---|---|---|---|---|---|---|
| display | Inter | 600 | 44px → 86px | 1.02 | -0.033em | The main headline (H1) |
| heading | Inter | 600 | 34px → 58px | 1.05 | -0.02em | Section headlines (H2) |
| statement | Newsreader | 400 | 30px → 58px | 1.08 | -0.03em | One serif sentence, such as the values line |
| subheading | Inter | 600 | 22px → 26px | 1.15 | -0.015em | H3, card-less grid titles |
| lead | Inter | 400 | 20px → 26px | 1.3 | -0.01em | Opening lines of a section |
| body | Inter | 400 | 17px → 18px | 1.5 | 0 | Paragraphs |
| small | Inter | 400 | 15px | 1.4 | 0 | Footer, supporting notes |
| label | Inter | 600 | 12px | 1 | +0.069em, uppercase | Section labels, tags |

Rules:

- The scale jumps from 26px straight to 58px. Nothing sits in between; the gap is what makes the headlines land.
- One family per text block. Serif italic may be used for a word or a title inside a sans paragraph, never the reverse.
- Body copy is always left-aligned. Paragraphs never run wider than 680px.

---

## 4. Spacing and shape

**Base unit:** 4px

| Token | Value | Typical use |
|---|---|---|
| `--space-4` | 4px | Gap between stacked headline lines |
| `--space-8` | 8px | Label to its icon-less neighbour, tag padding |
| `--space-16` | 16px | Gap between related elements |
| `--space-24` | 24px | Paragraph group spacing, grid cell padding on phones |
| `--space-32` | 32px | Grid cell padding on desktop |
| `--space-40` | 40px | Page side margin on desktop; label to headline |
| `--space-56` | 56px | Headline to body; section padding on phones |
| `--space-104` | 104px | Section top and bottom padding on desktop |

### Layout

- **Page max-width:** 1400px
- **Side margin:** 40px desktop, 20px phone
- **Section padding:** 104px top and bottom on desktop, 56px on phones
- **Reading column:** 680px maximum, pinned left
- **Sections are full-bleed.** A change of surface is the only divider between them.

### Radius, borders, elevation

| Element | Radius |
|---|---|
| Sections, grid cells, clip row | 0 |
| Newsletter button, nav newsletter pill, tags | 999px (pill) |
| Hero circle | 50% |

- Borders are 1px hairlines in Rule or Rule Dark. Nothing heavier, except a 2px Pink underline on links.
- No shadows anywhere. No blur, no glow.

---

## 5. Components

### LN monogram
The mark is the angular "LN" supplied on 2026-11-16, in two versions: black on white, white on black.
- **Where:** far left of the nav, the browser-tab icon, the footer.
- **Colour:** Ink on light surfaces, Paper on Ink. Never pink, blue or yellow, and never on the yellow section's circle or the hero circle.
- **Size:** 28px tall in the nav, 40px in the footer. Clear space around it equal to the width of the L's stem.
- **Source files (in the project root, 520 × 520 PNG):**
  - `woodmark-lux (2).png`: black mark on a solid white square.
  - `woodmark-lux-black.png`: white mark on a solid black square.
- **Background problem:** both files carry a solid square behind the mark. The page canvas is Paper `#fbf8f3` and Ink `#0f0f12`, not pure white and pure black, so the PNGs would show as a visible box if placed as they are.
- **Site version:** one SVG, `assets/ln-mark.svg`, traced from the PNGs with no background, coloured by the surface it sits on (Ink or Paper). The mark is four straight-edged shapes, so the trace can be exact; it is shown beside the original for approval before it is used. The two PNGs stay untouched as the masters.
- **Browser-tab icon:** the white-on-black PNG, which already works as a square icon.

### Distributed top nav
One slim row across the full width, items pushed apart with space-between: monogram and "Lux Narayan" (Inter 700) at the left, the five section links in the middle (Inter 500, 15px), the newsletter pill at the right. Paper background, a Rule hairline beneath. It stays fixed to the top while scrolling. On phones the section links drop out; the name and the pill remain.

### Section label
Inter 600, 12px, uppercase, +0.069em tracking, for example `02 · STREAMALIVE`. Pink Ink on light surfaces, Pink on Ink, Ink on Yellow. Sits 40px above the headline. No line, no icon.

### Display headline
The H1. Inter 600 at 86px, lines nearly touching, pinned left, at most about 14 characters per line so it stacks into a block.

### Section headline
H2 in the heading size. Pinned left, 20 characters per line or so.

### Statement
A single sentence in Newsreader at statement size, used sparingly: the three values in the story, "StreamAlive makes presentations conversations." No quotation marks, no decoration.

### Reading column
Lead paragraph followed by body paragraphs, 680px wide, left-pinned. Used for the story and the comedy section.

### Ghost link
The default action everywhere. Inter 600, body size, text colour matching its surface, a 2px Pink underline and a trailing →. On hover the underline thickens; the colour does not change.

### Newsletter button
The only filled button in the system. Pink Strong fill, white Inter 600 label, pill-shaped, 48px tall. Used for the newsletter sign-up and nothing else, so it reads the same in the nav, the opening and the closing section. Hover darkens the fill to `#c7004f`.

### Hero circle
One flat Blue circle, about 60% of the viewport height, placed right of centre in the opening section and running off the right edge. The headline may overlap its left side; body copy does not. It appears once on the page. On phones it shrinks and sits behind the top-right corner.

### Hairline grid
Replaces cards. Cells sit side by side, separated by 1px hairlines, with no fill, radius or shadow; a hairline runs above the row. Used for:
- the proof strip under the opening (3 cells),
- StreamAlive proof (3 cells),
- the talk and the book (2 cells),
- the StoryMining steps (4 cells, each with a label-style number above a subheading).

Cells stack into one column on phones, each with a hairline above.

### Clip row
The comedy clip. A full-width row on the yellow section with hairlines above and below: the clip title in Inter 600 at statement size, itself the link to YouTube with a trailing →, and the **Mildly NSFW** tag directly beside it (label style, Ink fill, Yellow text, pill). It is a link, never an embedded player.

### Story timeline
A hairline list beside the story's reading column, filling the right-hand side on desktop and sitting below the text on phones. Each row: the dates in label style (muted) and the place in subheading size. The last row, StreamAlive, takes the label colour. No rail, dots or icons.

### Footer
On Ink. Monogram, one line of small text, three ghost links. A Rule Dark hairline above.

### Imagery
Added 2026-11-16 because the type-only page read as too text-heavy (decision 28). Five images and one set of illustrations, each showing something real:

| Where | Image | File | Treatment |
|---|---|---|---|
| StreamAlive | A frame of the live demo on streamalive.com: chat answers becoming a word cloud | `assets/streamalive-demo.jpg` | Beside the body copy on desktop, above it on phones. 1px Rule Dark hairline. |
| Opening | Lux's portrait | `assets/lux-portrait.jpg` | A circle overlapping the lower left of the blue hero circle. On phones the pair shrinks to 132px and sits above the headline. |
| The talk | Lux on the TED stage, with the red "ED" of the TED letters in frame | `assets/ted-talk.jpg` | Fills the top of its grid cell at 3:2. Links to the talk. |
| The book | The cover of *Name, Place, Animal, Thing* | `assets/book-cover.jpg` | Centred on a Paper 2 panel the same size as the TED still. Links to the book. |
| Comedy | A frame of Lux on stage under the Comedy Cellar sign | `assets/comedy-cellar.jpg` | Beside the intro on desktop, above it on phones, capped at 560px wide because the source is low resolution. 1px Ink hairline. Links to the clip. |
| StoryMining | A blank grid with a few cells marked, echoing the places-by-names grid on storymining.life | inline SVG | Right of the intro on desktop, below it on phones. Hairline grid, Ink dots, no labels. |
| StoryMining steps | Four line drawings: a mapped grid with a pin, a pickaxe and ore, a cut gem, a gem on a plinth | inline SVG | Top right of each step cell. Ink line, 2px, round joins, 64px. |

Rules for every image: square corners, no shadow, no overlay, no caption that is not in COPY.md. Illustrations are Ink line art only; they never use pink, blue or yellow.

### Section surfaces

| Section | Surface | Note |
|---|---|---|
| Opening | Paper | Hero circle lives here |
| My story | Paper | Reading column; ends on a serif statement |
| StreamAlive | Ink | Inverted; pink label |
| Talks and book | Paper | Two-cell hairline grid |
| StoryMining | Paper 2 | Four-cell hairline grid |
| Comedy | Signal Yellow | The one saturated section |
| Newsletter | Ink | The newsletter button's largest appearance |
| Footer | Ink | Continues from the newsletter section |

---

## 6. Do and don't

**Do**
- Let headlines be very large and everything else small. Keep the 26px to 58px gap empty.
- Pin content to the left margin and leave the right side open.
- Change surface to change section. Use a hairline when two neighbouring sections share a surface.
- Keep pink, blue and yellow to their single jobs.

**Don't**
- Add stock photos, decorative icons, logos of other companies, or any image beyond those listed under Imagery.
- Use shadows, gradients, rounded cards or boxed panels.
- Fill any button other than the newsletter button.
- Centre paragraphs, or set them wider than 680px.
- Put white text on Pink or Blue.

---

## 7. CSS tokens

```css
:root {
  /* Surfaces and text */
  --paper: #fbf8f3;
  --paper-2: #f4efe6;
  --ink: #0f0f12;
  --ink-3: #66646c;
  --mist: #a9a8b0;
  --rule: #dcd3c4;
  --rule-dark: #2e2d33;

  /* Accents */
  --pink: #ff0064;
  --pink-strong: #e6005c;
  --pink-press: #c7004f;
  --pink-ink: #d4004f;
  --blue: #0086ff;
  --yellow: #ffea00;

  /* Fonts */
  --font-sans: "Inter Variable", "Inter", ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  --font-serif: "Newsreader Variable", "Newsreader", ui-serif, Georgia, "Times New Roman", serif;

  /* Type scale */
  --text-display: clamp(2.75rem, 1.6rem + 5.2vw, 5.375rem);
  --text-heading: clamp(2.125rem, 1.5rem + 2.9vw, 3.625rem);
  --text-statement: clamp(1.875rem, 1.2rem + 3vw, 3.625rem);
  --text-subheading: clamp(1.375rem, 1.3rem + 0.4vw, 1.625rem);
  --text-lead: clamp(1.25rem, 1.1rem + 0.7vw, 1.625rem);
  --text-body: clamp(1.0625rem, 1.04rem + 0.1vw, 1.125rem);
  --text-small: 0.9375rem;
  --text-label: 0.75rem;

  /* Spacing */
  --space-4: 4px;
  --space-8: 8px;
  --space-16: 16px;
  --space-24: 24px;
  --space-32: 32px;
  --space-40: 40px;
  --space-56: 56px;
  --space-104: 104px;

  /* Layout */
  --page-max: 1400px;
  --page-margin: clamp(20px, 3vw, 40px);
  --section-pad: clamp(56px, 8vw, 104px);
  --measure: 680px;

  /* Shape */
  --radius-none: 0;
  --radius-pill: 999px;
}
```

---

## Decision log

Every design choice is recorded here, newest last. Add a row whenever a choice is made or changed; never edit an old row, supersede it with a new one.

| # | Date | Decision | Why | Source |
|---|---|---|---|---|
| 1 | 2026-11-16 | The site is one long page of full-bleed sections. | Lux chose it over 7 separate pages. | Lux |
| 2 | 2026-11-16 | No photos or images of any kind. | Lux chose "text only" for the story; all five references but Karl are type-only. | Lux, references |
| 3 | 2026-11-16 | Brand wins on colours and fonts; references win on layout and feel. | Lux's rule for merging the sources. | Lux |
| 4 | 2026-11-16 | The brand is StreamAlive's. Colours and fonts are the tokens in streamalive.com's stylesheet. | Lux: "Use the same as streamalive.com." No separate brand kit file exists. | Lux, streamalive.com |
| 5 | 2026-11-16 | The LN monogram is the site's mark, in black and white versions only. | Supplied by Lux. | Lux |
| 6 | 2026-11-16 | Canvas is Paper `#fbf8f3`, not pure white. | Brand wins on colour. It also matches OFF+BRAND's warm parchment. | Brand |
| 7 | 2026-11-16 | Inter is the display face; Newsreader is kept for statements and italics. | Brand supplies both. The references set oversized headlines in a sans and reserve a serif for statements (Stink Studios). | Brand, references |
| 8 | 2026-11-16 | Display size tops out at 86px with -0.033em tracking; scale jumps from 26px to 58px. | Bpowell's scale, which gives the stacked-block headline. OFF+BRAND's 103px was judged too large for sentence-length headlines. | Bpowell |
| 9 | 2026-11-16 | Sections alternate Paper and Ink full-bleed, with no dividers between different surfaces. | Bpowell and Stink Studios. | References |
| 10 | 2026-11-16 | Comedy is the one full-bleed Signal Yellow section. | Karl's saturated canvas, used once. Yellow is a brand colour and suits the section. | Karl, brand |
| 11 | 2026-11-16 | One flat blue circle in the hero, and nowhere else. | OFF+BRAND's single chromatic hero object and Karl's globe. Flat, because the brand has no gradient and the references forbid gradients elsewhere. | OFF+BRAND, Karl |
| 12 | 2026-11-16 | One filled button exists, pink, for the newsletter only. All other actions are ghost links. | The references use no filled buttons; CONTEXT.md makes the newsletter the primary action and brand supplies pink. One exception keeps both. | References, CONTEXT.md |
| 13 | 2026-11-16 | White text sits on Pink Strong `#e6005c`, never on Pink `#ff0064` or Blue. | Measured contrast: 4.7 to 1 against 3.9 and 3.6. | Measurement |
| 14 | 2026-11-16 | Cards are replaced by hairline grids with 0 radius. | Bpowell, OFF+BRAND and Stink Studios all use 0 radius and no boxes. | References |
| 15 | 2026-11-16 | The newsletter button, nav pill and tags are pill-shaped. | The references disagree on button radius (0, 4px, 10px). Aaron Poe's pill nav and StreamAlive's own pill buttons broke the tie. | Aaron Poe, brand |
| 16 | 2026-11-16 | The nav is spread across the full width and stays fixed while scrolling. | Layout from Bpowell. The references do not fix their navs, but CONTEXT.md requires the sign-up to be reachable from every section. | Bpowell, CONTEXT.md |
| 17 | 2026-11-16 | Long text is held to a 680px column, pinned left rather than centred. | Aaron Poe's narrow column for readability; Bpowell's left pin for the feel. | References |
| 18 | 2026-11-16 | No automatic dark mode. | The page alternates light and dark by design; Stink Studios and Aaron Poe each fix a single theme. | References |
| 19 | 2026-11-16 | No shadows, gradients, hover colour changes or motion beyond an underline. | Common to all five references. | References |
| 20 | 2026-11-16 | No monospace font, although Stink Studios uses one for tags. | Brand has no mono, and brand wins on fonts. Labels use tracked uppercase Inter instead. | Brand |
| 21 | 2026-11-16 | The site uses a background-free SVG trace of the LN mark; the supplied PNGs remain the masters and the white-on-black PNG is the tab icon. | Both PNGs have a solid white or black square that would show as a box on Paper and Ink. | Lux's files, inspection |
| 22 | 2026-11-16 | The clip row's title is the link, set at statement size; the separate "Watch on YouTube" link is dropped. Supersedes the first clip-row spec. | Lux's build rule: only copy from COPY.md, which has no such line. The larger title gives the yellow section one loud moment. | Lux, COPY.md |
| 23 | 2026-11-16 | No third-party embeds. The comedy clip and the newsletter are links out, not an embedded player or sign-up form. | Lux's build rule. | Lux |
| 24 | 2026-11-16 | On the yellow section, labels, hairlines and link underlines are Ink, not Pink. | Pink on yellow is hard to read and breaks "one job per colour". | Build review |
| 25 | 2026-11-16 | The hero circle is `min(64vh, 40vw)` wide and the opening copy is held to 52% of the viewport width on desktop. | Review found body copy running under the circle at mid-size screens, which section 5 forbids. | Build review |
| 26 | 2026-11-16 | Inter and Newsreader load from Google Fonts. | Quickest faithful match to streamalive.com. They can be self-hosted later so the page makes no outside requests. | Build |
| 27 | 2026-11-16 | The proof strip sets each line as one sentence, bold lead-in followed by muted text, rather than a stacked figure and caption. | Keeps the copy verbatim, including its comma and colon. | COPY.md |
| 28 | 2026-11-16 | Images are allowed. Supersedes decision 2. | Lux: "I like the site, but it's too text-heavy. Let's add some visuals." | Lux |
| 29 | 2026-11-16 | The StreamAlive image is a still frame of the live demo on streamalive.com, cropped inside the window's rounded corners. | The site has no static product screenshots; the demo is the product. The inset crop keeps the 0-radius rule. | streamalive.com |
| 30 | 2026-11-16 | The talk uses TED's own still; the book uses its published cover. | Lux asked for a frame from the TED video and a book image. | ted.com, Amazon listing |
| 31 | 2026-11-16 | StoryMining gets a label-free marked grid and four step drawings, in Ink line art. | Lux asked for mining illustrations like storymining.life, which uses a places-by-names grid and one line icon per step. Labels are left off because they are not in COPY.md. | Lux, storymining.life |
| 32 | 2026-11-16 | Illustrations use Ink only, not storymining.life's amber, green, purple and red. | Brand wins on colour, and pink, blue and yellow each already have one job. | Decision 3 |
| 33 | 2026-11-16 | Story, Comedy and Newsletter stay without images. | No image was requested or supplied for them; Lux earlier chose text only for the story. | Lux |
| 34 | 2026-11-16 | Lux's portrait sits in the hero as a circle overlapping the blue circle. Amends decision 11: the blue circle stays, now with the portrait in front. | Lux supplied the photo and suggested the circle. The opening is where a visitor checking out the founder first looks. | Lux |
| 35 | 2026-11-16 | The talk uses Lux's supplied TED-stage photo in place of TED's web still. Amends decision 30. | Lux: the "ED" of the TED letters gives credibility. It is also sharper and 3:2. | Lux |
| 36 | 2026-11-16 | Comedy gets the Comedy Cellar frame, shown no wider than 560px. Amends decision 33. | Lux: low resolution, but the Comedy Cellar sign gives credibility. Keeping it small hides the blur. | Lux |
| 37 | 2026-11-16 | The hero figure is anchored to the content column, and on phones it moves above the headline. | A face must never sit behind headline text. | Build review |
| 38 | 2026-11-16 | StreamAlive section rebuilt lighter: full-width demo screenshot, two short lead lines, Lux's three lines as a serif row, two proof cells, platforms as pill tags, one closing line. | Lux: the section was too text-heavy. Only cuts and rearrangement of existing copy; no new words. | Lux |
| 39 | 2026-11-16 | Cut from StreamAlive: "The presenter talks, the audience types into a chat nobody reads, and everyone leaves." and the co-founders sentence. | The co-founders are already named in the story. | Decision 38 |
| 40 | 2026-11-16 | The TED photo carries the credit "Photo: Ryan Lash". | Lux supplied the credit. | Lux |
| 41 | 2026-11-16 | The book image is Lux's Kindle-and-hardcover mockup, blended onto the Paper 2 panel. Replaces the flat cover. | Lux supplied it. Its white background is multiplied into the panel so no white box shows. | Lux |
| 42 | 2026-11-16 | The story gets a timeline of eight places and dates on its right-hand side. Amends the "short narrative only" choice for the story. | The story was the only long section with nothing beside it. A decorative illustration was rejected as filler; the timeline carries real facts from CONTEXT.md and lets a skimmer get the arc. Lux approved it. | Lux |
| 43 | 2026-11-17 | Podcast appearances sit beside "Invite me to speak" as a two-cell hairline grid, linking to Lux's Spotify playlist. No Spotify embed. | Brings over the last item from the Linktree. A link keeps the no-embeds rule and the page's look; the share-tracking part of the URL is dropped. | Lux |

### Open questions

1. **Monogram trace.** The SVG in `assets/ln-mark.svg` was traced from your PNG by measuring its edges. Compare them at `assets/mark-check.html`. If you have the original vector file, add it and I will use that instead.
2. **Hero circle.** It is the boldest borrowed idea here. Say if you would rather the opening be type only.
3. **TED photo credit.** The stage photo was probably taken by TED's photographer. If TED asks for a credit line, tell me the wording and I will add it.
