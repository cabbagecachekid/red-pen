---
name: publication
description: Opinion journalism, essays, newsletters, any argumentative piece under a house style. Failure mode under AI editing is SOFTENING — hedges, de-cursing, diplomatic padding, false balance. Same mechanism as job-seeker, opposite polarity.
credit: Ported from little-bird-final-pass by Bird (alittlebirdseyeview.com), MIT, shared 2026-08-15. Entity-specific rules (byline, masthead, domain, scope guard) live in examples/profile-little-bird.md, not here.
polarity:
  distortion: deflate      # Pass 3 watches for claims getting smaller / softer than the author's draft
  tone: soften             # cringe-check dimensions inverted: the defect is mush, not swagger
---

# Register: publication

## Pass 2 rule — mechanical house style (hard, zero tolerance)
Flag every instance; these are not judgment calls. Defaults below; a profile may override any line.
- No em dashes (—) or en dashes (–) for stylistic purposes. Replace with commas, semicolons, colons, parentheses, or restructure. Hyphens only for genuine compound modifiers.
- Ranges use "to," never a dash.
- Oxford comma throughout; standard journalistic punctuation only.
- Quotation marks only for actual quoted speech — not emphasis, not scare quotes.
- Italics reserved for publication names, titles of works, and terms of art on first analytical use.

## Distortion watchlist (softening)
- Hedges inserted or retained where the author's claim is direct: "arguably," "perhaps," "it could be said," "some might argue," "might" where the draft said "would."
- Cursing removed, euphemized, or asterisked. De-cursing is a violation, not a fix.
- Compressed phrasing expanded into explainer prose. If a sentence got longer without adding information, it got worse.
- Register formalization: contractions expanded, direct address removed, second person swapped for passive.
- Apology or permission-seeking framing: "This may be controversial, but."
- Any softening of the piece's central accusation or thesis. If the draft says a thing is theft, the edit does not make it "a questionable arrangement."
- **Never inflate either.** Polarity says where to look hardest, not what to ignore: a claim made bigger than the author's draft is still a violation.

## AI-tell extensions
Append to `ai-written-check`'s core catalog:
- Engineered contrast constructions: "It's not X, it's Y." "This isn't about A. It's about B."
- Stock AI vocabulary: delve, landscape, tapestry, navigate (metaphorical), robust, seamless, leverage (verb), foster, crucial, pivotal, multifaceted, nuanced (as filler).
- False-balance closers and both-sides padding appended to an argumentative piece.
- Symmetrical paragraph engineering: every paragraph the same length, every section opened the same way.
- Summary paragraphs that restate what the piece just said.

## Tone dimensions
Run `cringe-check`'s dimensions inverted: instead of asking "does the author claim too much," ask "did the edit make the author claim, feel, or say less than they wrote." Solo-hero and positioning-against still apply as written (an editorial can be cocky too); JD-parroting and undermining-offers do not apply.

## Needs-no-source claims
Opinion, inference, and analytical framing need no source; that is the product. Do not flag the thesis as unsourced. Flag only the load-bearing facts underneath it. In the gaps report distinguish: sourced / needs source / opinion (no source required).

## Mechanical style pass
Yes — it is Pass 2 above.
