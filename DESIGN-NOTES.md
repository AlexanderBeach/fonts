# Design notes

Why these fonts, and what the choices behind them were. Written September 2026, after
a series of blind comparisons and letter-by-letter picks. Keep this if the fonts ever
change; the reasoning is the part that is hard to reconstruct.

## Preferences, stated

Two rules were given in words before any letter was judged, and they outrank everything
read off the tests:

- Small serifs.
- Soft, rounded serifs rather than sharp ones. The serif should curve into the stem
  (bracketed) and its corners should be blunted, not cut to a point.

Other stated preferences: Greek letters clearly distinct from their Latin look-alikes;
specimens judged at 10 to 11 pt or larger; a liking, before any testing, for Segoe UI,
Fira Code with ligatures, Source Sans, Palatino for LaTeX (mathpazo) and Intel Clear.

## Preferences, read off the picks

From roughly 160 letter-by-letter picks across Greek, Latin, figures and punctuation,
made against nine to thirteen families scaled to one x-height.

**Weight and contrast.** Sturdy strokes; hairlines are never chosen. Stroke contrast low to
moderate, about 2 to 1: sturdier than a transitional face, but not monoline. Weight is a
floor rather than a target: the lightest families lost even where their shapes were liked.

**Terminals.** Blunt or lightly curved stroke endings, never hooks or ball terminals.
Wherever a row offered a flat-cut ending and a curled one, the flat cut won.

**Apertures and counters.** Open, at every weight. The e, c, a and g were chosen for the
opening staying wide; versions whose terminal curls the counter shut lost every time.

**Curvature in the body, not at the ends.** Full round arches (n's shoulder), bowed legs
(R), curved junctions (k's arm, v's vertex), closed round bowls. Movement belongs in the
middle of the letter; the ends stay plain.

**Two constructions, chosen per letter.** Letters that are a bowl or a set of bars get a
plain, near-monoline stroke. Letters whose identity is a silhouette get a little
calligraphic taper. The same hand switches mode letter by letter, and both modes appear in
every group of picks.

**One mark of difference, then stop.** Where a Greek letter risks reading as its Latin
twin, the chosen form carries exactly one distinguishing device (a hook, a curl, an
asymmetry) and no swash. Where the tradition allows a different skeleton (α not a, ε not e,
ν hooked, χ curved, τ without an ascender) it was taken every time.

**Mild slant.** Italic and maths italic at roughly ten to twelve degrees. Many upright
calligraphic forms were picked for maths Greek, which is why Euler is the Greek
recommendation.

**Figures.** Lining, never old-style, regardless of which family the figures came from.

**Italic.** A true cursive, not a sloped roman, departing from the roman letter by letter:
a stays two-storey, g goes single-storey with an open hook tail.

**Erewhon's own letters** survived wherever a plain round bowl is the whole letter
(o, g, t, the ampersand, Greek θ ε ο υ) and lost wherever an ending tapers, curls or thins
next to a blunter rival.

## Why each font

**Erewhon with Erewhon Math for papers.** The one result that survived every blind test:
unbeaten on body text in a round robin of six finalists, and no composite built on it did
visibly better. Sturdy transitional serif, small bracketed serifs, and a maths font of the
same design so text italic and maths italic match.

**XCharter with XCharter Math as the alternative.** Letter by letter, the picks went to
Charter-family shapes above all others: low contrast, blunt terminals, open apertures,
small soft serifs. It never beat Erewhon in a paragraph test, so it is the alternative,
not the default.

**Euler Math for Greek.** More Greek picks went to Euler than to any other family, and it
is upright and calligraphic by design, so Greek does not read as sloped Latin.

**Fira Sans with Fira Math for slides and screen.** Sans faces lost every prose test, so
they stay off papers. Fira has a proper maths companion in the same design, which is rare
for a sans, and Fira Code was already the code font of choice.

## What lost, and why

- EB Garamond and Palatino won a browser-rendered reading test and then lost badly in
  typeset paragraphs, where their thin strokes go pale. The browser hints and thickens;
  PDF viewers draw the unhinted outlines.
- Computer Modern and Latin Modern took no letter picks at all.
- New Computer Modern was rated highly when its name was shown and lost every blind
  pairing to Erewhon.
- Sans faces (Inter, Source Sans, Fira Sans, Plex) came last for prose.
- Bookman, Concrete and DejaVu Serif failed the serif rules: blunt and heavy, sharp and
  mechanical, or too even.

## Things learnt about the method

- Composites assembled from individually preferred letters read worse than any one of
  their sources. Consistency of one hand matters more than the best version of each
  letter.
- Paragraph A/B tests cannot judge single letters; differences of one glyph are invisible
  at text size. Letter-level questions need a picker that shows one word with only the
  letter in question swapped.
- Isolated letters at large size favour sturdy low-contrast shapes; paragraph texture
  favours Erewhon. Both are real, and the paragraph is what a paper is read as.
- A drawn alphabet was started from these rules (skeletons swept by one elliptical pen,
  small bracketed serifs, contrast about 1.9 to 1) and stopped: the letters were judged
  not good enough, and the recommendation went to existing fonts instead.

## Practical notes

- In LaTeX, taking only the Greek from Euler needs the alphabet form of the range option:
  `range={\mathup/{greek,Greek}, \mathit/{greek,Greek}, \mathbfup/{greek,Greek},
  \mathbfit/{greek,Greek}}`. The shorter `range={greek,Greek}` fails, and `\mathbf` is
  refused in that position.
- In matplotlib (see the hvb style), letters and Greek come from the italic and bold
  faces named for `it` and `bf`, and everything non-alphabetic from `rm`. Setting `rm` to
  the maths font and `it` to the text font's italic gives matching serif maths.
- XCharter Math's spacing collapses if a display line overfills its column, because TeX
  shrinks the operator glue to nothing; give displayed maths room.
