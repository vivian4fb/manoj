---
version: alpha
name: Instrument and Paper
description: The design system for the CIE 9702 vector analysis teaching site — a dark instrument panel that carries the live field, above a light exam paper that carries the working.
colors:
  ground: "#080C16"
  stage: "#0B1020"
  card: "#141C2E"
  ink-dark: "#FFFFFF"
  ink-dark-2: "#C7D2E4"
  ink-dark-3: "#8496B4"
  paper: "#F4F6F9"
  panel: "#FFFFFF"
  ink: "#111925"
  ink-2: "#33415A"
  muted: "#5C6B80"
  rule: "#D2DAE5"
  vec-a: "#1F63CE"
  vec-b: "#A96500"
  vec-r: "#C0166B"
  vec-c: "#0B7A6E"
  vec-a-dark: "#4C9AFF"
  vec-b-dark: "#FFB020"
  vec-r-dark: "#FF5CA8"
  vec-c-dark: "#2EC4B6"
  primary: "{colors.vec-r}"
  on-primary: "{colors.panel}"
  secondary: "{colors.ink}"
  accent: "{colors.vec-a}"
  background: "{colors.paper}"
  foreground: "{colors.ink}"
typography:
  display:
    fontFamily: IBM Plex Sans Condensed
    fontSize: 4rem
    fontWeight: 700
    lineHeight: 1.02
    letterSpacing: -0.02em
  h2:
    fontFamily: IBM Plex Sans Condensed
    fontSize: 1.9rem
    fontWeight: 600
    lineHeight: 1.15
  body:
    fontFamily: IBM Plex Serif
    fontSize: 1.0625rem
    fontWeight: 400
    lineHeight: 1.62
  label-caps:
    fontFamily: IBM Plex Mono
    fontSize: 0.6875rem
    fontWeight: 500
    letterSpacing: 0.12em
  numeral:
    fontFamily: IBM Plex Mono
    fontSize: 1rem
    fontWeight: 500
rounded:
  sm: 4px
  md: 8px
  lg: 14px
spacing:
  xs: 6px
  sm: 12px
  md: 20px
  lg: 36px
  xl: 64px
  xxl: 112px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.sm}"
    padding: 14px
  button-primary-hover:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.background}"
    textColor: "{colors.foreground}"
    rounded: "{rounded.sm}"
    padding: 14px
  film-card:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.foreground}"
    rounded: "{rounded.lg}"
  film-card-index:
    backgroundColor: "{colors.ground}"
    textColor: "{colors.vec-b-dark}"
    typography: "{typography.numeral}"
  section-label:
    backgroundColor: "{colors.background}"
    textColor: "{colors.muted}"
    typography: "{typography.label-caps}"
  rule-divider:
    backgroundColor: "{colors.rule}"
    height: 1px
  legend-chip-a:
    backgroundColor: "{colors.vec-a}"
    textColor: "{colors.panel}"
    rounded: "{rounded.sm}"
  legend-chip-b:
    backgroundColor: "{colors.vec-b}"
    textColor: "{colors.panel}"
    rounded: "{rounded.sm}"
  legend-chip-r:
    backgroundColor: "{colors.vec-r}"
    textColor: "{colors.panel}"
    rounded: "{rounded.sm}"
  legend-chip-c:
    backgroundColor: "{colors.vec-c}"
    textColor: "{colors.panel}"
    rounded: "{rounded.sm}"
  instrument-stage:
    backgroundColor: "{colors.stage}"
    textColor: "{colors.ink-dark}"
  instrument-card:
    backgroundColor: "{colors.card}"
    textColor: "{colors.ink-dark-2}"
    rounded: "{rounded.lg}"
  instrument-meta:
    backgroundColor: "{colors.ground}"
    textColor: "{colors.ink-dark-3}"
    typography: "{typography.label-caps}"
  instrument-vector-a:
    backgroundColor: "{colors.ground}"
    textColor: "{colors.vec-a-dark}"
  instrument-vector-r:
    backgroundColor: "{colors.ground}"
    textColor: "{colors.vec-r-dark}"
  instrument-vector-c:
    backgroundColor: "{colors.ground}"
    textColor: "{colors.vec-c-dark}"
  body-text:
    backgroundColor: "{colors.background}"
    textColor: "{colors.ink-2}"
    typography: "{typography.body}"
---

## Overview

The landing page of a teaching site for Cambridge International AS Level Physics 9702, section
1.4 and 4.2.3. The audience is a seventeen-year-old who has been told vectors are easy and has
just discovered they are not, and the teacher who has to get thirty of them through a paper.

The page is one object with two substrates, and the split is not decorative — it is the subject.
Above the fold is the **instrument**: a dark panel carrying a live vector field, the same black
the eleven films are rendered on. Below it is the **paper**: a light exam sheet carrying the
syllabus mapping, the film index, and the working. The student meets the quantity as a moving
arrow on a screen, then meets it again as a number on a page. The page is the hinge between the
deck (all instrument) and the lesson page (all paper), and it must look like it belongs to both.

The register is a university physics department, not a children's app. Nothing bounces. No
mascot, no confetti, no badge, no streak counter. The page assumes the reader is here on purpose.

## Colors

Four vector roles carry the entire system, and they carry it on two substrates. The same role
keeps the same hue across the whole site — on the page, on a slide, and inside a film. An amber
arrow in a video and an amber label on the page are the same quantity. This is the one rule that
cannot be traded away, and every other colour decision defers to it.

- **Vector A** {colors.vec-a} on paper, {colors.vec-a-dark} on the instrument — the first vector
  of any pair, and the horizontal component when resolving.
- **Vector B** {colors.vec-b} / {colors.vec-b-dark} — the second vector, and the vertical
  component.
- **Resultant** {colors.vec-r} / {colors.vec-r-dark} — the answer. It is also the only
  call-to-action colour on the page, because the resultant is the thing the student is being
  sent to find.
- **Vector C** {colors.vec-c} / {colors.vec-c-dark} — the third vector: the closing side of an
  equilibrium triangle, the current in a river crossing.

The substrates are never pure. **Ground** {colors.ground} is the film black, blue-shifted, so the
video frame dissolves into the panel with no visible seam. **Paper** {colors.paper} is a cool
off-white, never pure white; **panel** {colors.panel} is the true white, and it is reserved for
cards that sit on the paper so they lift without a heavy shadow. **Ink** {colors.ink} is
blue-black and carries all body text; it is never pure black.

The dark quartet is the light quartet lifted for luminance, not a different palette. Measured
against the substrate each sits on:

| Role | On {colors.ground} | On {colors.paper} |
|:--|:--|:--|
| Vector A | 6.9:1 | 5.2:1 |
| Vector B | 10.6:1 | **4.3:1** |
| Resultant | 6.9:1 | 5.4:1 |
| Vector C | 9.0:1 | 4.8:1 |

All four clear 4.5:1 on the instrument. On paper, **Vector B is the exception at 4.3:1** — it
clears the 3:1 bar for graphics and large text but misses AA for body copy. So amber on paper is
restricted to arrows, rules, arrowheads, and numerals set at 1.25rem or larger; it never sets a
line of running text. Darkening it to pass would break the match with the rendered films, and the
films are the fixed point. The restriction is the correct trade, not the colour change.

## Typography

Three IBM Plex cuts, each with one job, no overlap.

- **IBM Plex Sans Condensed** {typography.display} sets every heading. Condensed is the point:
  it is the compression of an exam paper rubric, and it lets a long heading hold one line at
  the width the page actually has.
- **IBM Plex Serif** {typography.body} sets all running prose at {typography.body.fontSize}.
  A serif at reading size signals textbook, not marketing site, and it is the single strongest
  lever the page has for register.
- **IBM Plex Mono** carries every number, every unit, and every answer — {typography.numeral}
  in content, {typography.label-caps} for the small caps labels that mark sections and film
  indices. A figure set in mono is a figure the student can trust is exact. Prose never borrows
  mono for emphasis, and a numeral never appears in serif.

Size differences stay modest. The display is roughly 3.8x body, and section heads
{typography.h2} only about 1.8x. The hierarchy is carried by weight, case and colour before it is
carried by size.

## Layout

A single measure of 66 characters governs all running prose, and the page never exceeds 1200px of
content width regardless of the viewport. The rhythm is the spacing scale and nothing between
its steps: {spacing.xxl} between major bands, {spacing.lg} inside a band, {spacing.sm} between a
label and the thing it labels.

The instrument band is full-bleed and sized by viewport, not by content — it wants to be seen at
a glance and scrolled past. Every band below it is paper, gutter-bounded, and sized by content.
The film index is a responsive grid that collapses 3 to 2 to 1 with no change of card design.

## Elevation & Depth

The instrument has depth; the paper does not. On {colors.ground} the field reads by luminance and
overlap alone. On {colors.paper} elevation is a hairline {colors.rule} border plus a shadow so
faint it registers only as a lift — cards are sheets on a desk, not floating glass. No glass, no
blur, no glow below the fold. The one gradient permitted on the whole site is the vertical fade
that hands the instrument off to the paper.

## Shapes

Corners are {rounded.sm} on controls, {rounded.lg} on cards, and square on anything that is a rule
or a divider. Nothing is a pill, nothing is a circle except a play affordance. Arrowheads in the
SVG and WebGL figures are the only pointed forms on the page and that is deliberate — a triangle
on this site means a vector.

## Components

The film card is the workhorse: a {colors.panel} sheet holding a 16:9 video, a mono index numeral
in {colors.vec-b-dark} over the film's own black, a condensed title, and one serif line of what
the film proves. It never shows a duration, a progress ring, or a completion tick.

The primary button is {colors.vec-r} — the resultant colour, used for the single action that
matters on each band. There is at most one primary button visible at a time. The ghost button
carries everything secondary and is paper with an ink rule.

## Do's and Don'ts

- **Don't** use the education typography match the design-search returns (Baloo 2 + Comic Neue).
  It is tuned for children's apps and is the wrong register for a seventeen-year-old sitting an
  A level. This rejection has now been made twice, deliberately, on this project.
- **Don't** introduce the search tool's education teal as a brand colour. Its teal collides with
  {colors.vec-c}, which already means "third vector" inside eleven rendered films. The films
  cannot be re-rendered to suit a palette; the palette defers to the films.
- **Don't** gamify. No points, no streaks, no badges, no confetti on a correct answer, no
  progress bar implying a course must be completed in order.
- **Don't** put a glow, a glass surface, or a drop shadow below the fold. Depth lives in the
  instrument only.
- **Don't** let the WebGL field become decoration. It must render a real vector field with named,
  inspectable components; if it cannot, it is replaced by the static SVG fallback and nothing is
  lost.
- **Don't** autoplay a film with sound, and don't autoplay more than one at a time.
- **Don't** set body copy in {colors.vec-b} on paper. It measures 4.3:1 and misses AA. Amber on
  paper is for arrows, rules and large numerals only.
- **Do** keep every number in mono. A figure in serif is a bug.
- **Do** give the WebGL hero a static first frame that reads on its own, so a machine with no
  WebGL, a locked-down school laptop, or a reader who prefers reduced motion sees a composed
  page rather than a hole.
- **Do** treat the paper as a printed object. A band that ends two-thirds down the viewport is
  correct, not under-filled.
- **Do** keep the four vector hues doing exactly one job each, everywhere, forever.
