# TRT logo - refined version: design report

Files:
- `Logo TRT - Refined.svg` - the refined design (design exploration).
- `Logo TRT - Refined - Comparison.png` - canonical version, refined version and compact variant at 256, 96, 48 and 32 px.
- `Logo TRT - Construction.svg` - the canonical engineering reconstruction. It was not modified.

Scope: the concept is unchanged. It is still two glyphs that form pi, a central double-struck R (the real numbers), and concentric rings. The refined file uses the same five-layer structure as the construction file, so it can be edited the same way.

## Design system used

All values are in the 300 x 300 canvas of the refined file (1 unit = 0.5 mm on the page). The logo centre is (150, 150).

- Hairline unit U = 2.4. It is the stroke of the two thin rings and of every R line.
- Gap unit G = 5.0. It is the space between neighbouring rings and also the gap between the two crossbars.
- Outer ring stroke = 6.0 (2.5 U). Its outer edge is at radius 146, the same footprint as the canonical version.
- Ring centre-line radii: 126.4, 133.8, 143.0, derived from U and G.
- The pi + R group fits inside a circle of radius 115.2. That leaves a clearance of 10 to the inner ring, whose clear radius is 125.2.

## Changes, reasons, benefits, tradeoffs

1. Pi + R group centred in the rings, and scaled by 0.9365.
   - Before: the group was off-centre by (5.8, 4.1) px, and the top-right corner of the right crossbar came within 2.3 px of the inner ring.
   - Now: the group is centred by its minimum enclosing circle and scaled so the clearance is 10. Measured on the render, the clearance is 9.7.
   - Benefit: equal breathing room around the symbol, no near-collision with the ring, and a cleaner look when reproduced.
   - Tradeoff: the symbol is 6.4% smaller inside the same rings. The ink mass centre of the glyphs is still 4.1 px left and 5.7 px above the circle centre, because the crossbars make the pi top-heavy. This is a conscious choice: equal clearance was chosen over mass balance. Both are one scale and move in Layer 2 if you prefer the other.

2. Ring system made rational.
   - Before: the three rings had strokes of 1.78, 1.39 and 5.7 and gaps of 4.25 and 5.9, all fitted to a hand-drawn raster.
   - Now: two equal hairline rings (2.4) and one outer ring (6.0), with equal gaps of 5.0, all on one centre. Every dimension comes from U and G.
   - Benefit: rings that look intentional, and a fixed rule for any resizing. The thinnest stroke is thicker (2.4 against 1.39).
   - Tradeoff: some of the original's hand-made character is gone. It was already treated as raster noise.

3. Crossbar gap set to G.
   - Before: 5.27 px at the old scale.
   - Now: exactly 5.0, the same value as the ring gaps.
   - Benefit: one spacing value across the whole mark.
   - Tradeoff: none that is visible; the change is about 0.07 px.

4. Glyph curves simplified.
   - Before: 18 circular arcs for the pi edges, tolerance 0.55 px.
   - Now: 14 arcs, with every tangent break under 9 degrees. The edges stay within 0.75 px of the approved raster (0.70 px after scaling).
   - Benefit: fewer nodes, smoother curves, easier to edit, lighter file (90 KB against 118 KB).
   - Tradeoff: a slightly looser fit to the raster (0.75 px against 0.55 px), still well below what is visible.

5. Crossbar joints made exact.
   - Before: the serif body and the left crossbar met with a faint hairline seam, up to about 10% lighter in a one-pixel column, visible only at high zoom. The corners between the stems and crossbars also sat about 0.3 px off the crossbar lines.
   - Now: the crossbar overlaps the serif body by 3 px, and all joints sit exactly on the crossbar lines.
   - Benefit: a solid black join at any magnification.
   - Tradeoff: none.

6. R redrawn as nine parametric strokes of width U.
   - Before: a traced 1-px bitmap R with irregular 2-3 px hairlines, built from 45 segments.
   - Now: the same double-struck serif R built from a stem, three slab serifs, a bowl, and a hollow leg. The bowl is two circles of equal radius, with the second moved left by 0.17 of the cap height. Their offset gives the thick-to-thin bowl. Every line is U wide. The baseline is exactly the flat top of the right hook terminal, and the R is centred between the stems. Cap height is the same as in the canonical version, scaled with the symbol.
   - Benefit: a clean, regular R of one consistent weight, matching the thin rings, and an R made of editable primitives (rectangle, lines, two arcs).
   - Tradeoff: this is an interpretation, not a trace. The shapes of the bowl and the leg are idealised, and the hairlines are a uniform 2.4, where the original varied between about 2 and 3 px. It is the part most worth reviewing by eye.

7. Compact variant for small sizes (hidden sub-group of Layer 5).
   - What: a single heavy ring (9.0), the same pi, and a single-stroke R (3.4) in place of the double-struck R.
   - Benefit: at 48 px the canonical version's thin rings render at about 0.22 px wide and blur to grey. The refined full version renders them at about 0.38 px. The compact variant has a ring about 1.4 px wide and a crisp R.
   - Tradeoff: the double-struck R, one of the concepts, is simplified in this variant. Use it only where the full logo cannot be resolved (about 48 px and below). The R is hardly legible below about 32 px in any version.

## What was not changed

- Overall concept, the pi structure, the crossbar relationship and the thick-thin modulation of the pi.
- The outer footprint and ring count.
- No colour, typography or lock-up decisions were made.

## Verification

- Refined render, measured along four axes: ring edges at radii 125.2, 127.6, 132.6, 135.0, 140.0 and 146.0 (within 0.1 of the design on all four sides).
- Farthest glyph ink from the centre: 115.5 (design 115.2).
- The seam test shows 0 pixels lighter than solid black in the join region of the refined file.

## Not done and open points

- Not opened in Inkscape. Renders and checks used MuPDF only.
- No print, CMYK, or minimum-size tests on real media.
- A faint seam remains in the canonical `Logo TRT - Construction.svg` (see change 5). I left it untouched as requested. The same 3 px overlap fixes it if you want it.
- The design judgement is mine and subjective. Items 1 and 6 are the ones most worth a second look.
