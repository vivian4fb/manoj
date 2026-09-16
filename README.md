# Vector Analysis for CIE 9702

Teaching material for **Cambridge International AS & A Level Physics 9702**, covering
scalars and vectors (1.4) and the equilibrium vector triangle (4.2.3).

Eleven rendered films, eleven worked lessons, a projection deck, and a course home page.

## Pages

| File | What it is |
|:--|:--|
| `index.html` | Course home. Dark instrument panel with a live WebGL vector field, then the film index on paper. |
| `lesson.html` | The lesson: 11 lessons, 3 interactive SVG figures, 10 self-marking questions, a summary sheet and teacher notes. |
| `deck.html` | The projection deck: 17 slides on a locked 16:9 surface, films autoplay on slide entry, keyboard / swipe / fullscreen. |
| `videos/` | 11 films, 1080p30, 19.4–22.1 s each, 223.4 s total, 6.9 MB. Shared by all three pages. |
| `DESIGN.md` | The design system, in [DESIGN.md](https://github.com/google/design.md) format. Lints clean. |

## The design system

`DESIGN.md` is the source of truth for how this site looks. It is a real DESIGN.md
document — tokens in YAML front matter, rationale in prose — and it validates against the
spec:

```bash
npx -p "@google/design.md" designmd lint DESIGN.md
# => { "errors": 0, "warnings": 0 }
```

The system is called **Instrument and Paper**: a dark panel carrying a live vector field
above a light exam sheet carrying the working. Four hues carry four vector roles, and they
carry the same roles in the films, on the slides, in the page figures and in the WebGL
field — an amber arrow always means the same quantity.

Two recommendations from the design search were deliberately refused, and the reasons are
recorded in the `Do's and Don'ts` section of `DESIGN.md`:

- **Baloo 2 + Comic Neue** for "education" — tuned for children's apps, wrong register for a
  seventeen-year-old sitting an A level. The site is set in IBM Plex instead.
- **Education teal as a brand colour** — it collides with the hue that already means "third
  vector" inside eleven rendered films. The films cannot be re-rendered, so the palette
  defers to them.

One accessibility trade is recorded rather than hidden: amber measures **4.3:1** on paper,
so it is restricted to arrows, rules and large numerals and never sets body copy.

## The WebGL field

The arrows on the home page are a genuine divergence-free vector field, not a particle
effect. The potential is a sum of terms `a·sin(k·p + φ + ωt)`, so the curl is exact and
analytic — `∇×Ψ = Σ cos(k·p + φ + ωt)(k × a)` — with no noise, no finite differences and no
`Math.random` anywhere in the file.

Colour is the one visual rule, and it is the site's own meaning:

| Arrow | Role |
|:--|:--|
| mostly horizontal | first vector / horizontal component |
| mostly vertical | second vector / vertical component |
| fastest | resultant |
| slowest | third vector |

Inspect it from the console:

```js
__field.debug('speed')        // or 'verticality', 'depth', 'role'
__field.params                // parameters grouped by perceptual role
```

It pauses when scrolled out of view or when the tab is hidden, caps device pixel ratio at
1.75, honours `prefers-reduced-motion`, and falls back to the drawn 3–4–5 triangle if WebGL
is unavailable or the context is lost.

## Rebuilding the films

The films are rendered with Manim Community v0.21.0 from the scene sources kept alongside
this site in the authoring workspace:

```powershell
cd manim
./render_vectors.ps1                # all 11, 1080p30
./render_vectors.ps1 -Quality l     # 480p draft
```

No number in any scene is typed by hand. Every figure is computed from the vector
components and checked against a hand-worked value; a drift aborts the render.

## Local preview

```bash
python -m http.server 8000
# then open http://localhost:8000/
```

A plain file:// open also works, except that the ES module import map for three.js needs an
HTTP origin — over file:// the page falls back to the static triangle, which is the intended
degradation.
