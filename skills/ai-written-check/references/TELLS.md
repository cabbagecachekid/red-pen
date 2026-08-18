# AI Tells — Full Catalog

This is the reference catalog for `ai-written-check`. The SKILL.md has the working checklist; this file has the worked examples, edge cases, and reasoning. Load it when a call is ambiguous or when the author wants to understand *why* something reads as generated.

The governing principle: **density, not presence.** A single instance of most of these is how good human writers write. The tell is the pile-up. Count before you flag.

---

## 1. Em dashes

The single most pattern-matched signal of machine authorship in 2025–2026. Models reach for the em dash as a default connective; experienced human writers use it sparingly and deliberately.

- **Body copy:** flag nearly every one. Default replacements: a period (most common), a colon (when the second clause explains the first, used sparingly), or simply a shorter sentence.
- **Headers / titles:** an em dash as a structural separator ("Resume — 2026") is acceptable.
- **Watch the substitution trap:** don't replace every em dash with a semicolon. A wall of semicolons is its own tell.

> Before: "I led the research — and it changed how the team shipped."
> After: "I led the research. It changed how the team shipped."

---

## 2. Triple-list anaphora

Three parallel phrases with a repeated stem, used for rhythm: "about money, about trust, about control." Real writers do this occasionally for emphasis. Models do it reflexively.

- 1 per page: fine, often good.
- 2+ per page: a tell.

> Before: "It's about the user, about the team, about the outcome."
> After: "It's about the outcome for the user and the team."

---

## 3. "Not X, but Y" / "X, not Y" antithetical pairs

The contrast-scaffold sentence. "This isn't a feature, it's a philosophy." One per piece reads as deliberate rhetoric. More than one reads as a template.

> Before: "I'm not a researcher who observes — I'm one who ships."
> After: "I ship. The research is in service of the decision."

---

## 4. Spatial metaphors for abstract concepts

Mapping ideas onto physical space when no space is involved: "corners of their financial lives," "the territory of taxes," "navigating the landscape," "the current frontier."

> Before: "We explored the corners of their financial lives."
> After: "We looked at how they handle budgeting, debt, and savings."

Use the concrete noun the metaphor is gesturing at.

---

## 5. Economic / cost metaphors for non-economic things

"Make rigor the cheap option," "the time tax," "the heavy lift," "pay down the debt of bad onboarding." Fine in genuinely economic contexts; a tell when bolted onto things that aren't transactions.

> Before: "Good defaults make the right choice the cheap option."
> After: "Good defaults make the right choice the easy one."

---

## 6. "Architect" as a verb

"Architected the system," "architecting the experience." Flag each.

> Fix: "designed," "built," "set up."

---

## 7. "Across" overuse

"Across the funnel," "across products," "across teams," "across the org." One is fine; clusters signal filler.

> Before: "I drove alignment across products, across teams, and across the funnel."
> After: "I aligned three product teams on a shared funnel."

---

## 8. "From X to Y to Z" arcs

The escalating triad used to dramatize a career or an idea. "From intern to lead to founder." "From curiosity to conviction to launch." Flag when a plain sentence carries the same information.

> Before: "My path went from design to research to strategy."
> After: "I started in design, moved to research, and now work on strategy."

---

## 9. Engineered sentence cadence

Deliberate alternation of very short and very long sentences to create a beat. "It worked. After eighteen months of interviews, prototypes, and three failed launches, the thing finally clicked into place and the metrics moved." Real prose has rhythm; manufactured rhythm calls attention to itself.

Fix: let sentence length follow the meaning. If two sentences are the same length because the ideas are the same weight, leave them.

---

## 10. Voice-register swerve

A paragraph that opens grounded and human, then pivots into abstract industry-speak — or the reverse. The swerve is the tell; a model often can't hold one voice across a paragraph.

> Before: "I sat with twelve contractors at their job sites and watched them lose an hour a day to paperwork. This represents a significant opportunity to optimize operational throughput across the verticalized construction value chain."
> After: "I sat with twelve contractors and watched them lose an hour a day to paperwork. That hour is the problem worth solving."

Pick the register the human half is in and stay there.

---

## 11. Builder / startup subculture slang

"Vibe coding," "shipping," "hot takes," "cracked at," "in the arena," "building in public." These read as in-group performance in formal application or client copy. (In a casual builder Discord they're native — context matters.)

> Fix: substitute the neutral substance-equivalent. "Shipping fast" → "releasing working versions quickly." "Cracked engineer" → "exceptional engineer."

---

## 12. Unfalsifiable universal claims

"Everyone," "all," "every," "universally," "across the board," "no one," "always." These are the AI-pitch tell: a model smooths a specific observation into a sweeping one because the sweeping version sounds more impressive. The opposite is true — specificity is credible, universality is suspicious.

> Before: "This affects everyone who files taxes."
> After: "Every contractor I interviewed hit this in their first week."

The test: would a domain expert who read the actual data nod, or wince? Universal claims almost always wince.

---

## 13. Sincerity adverbs: "honestly," "quietly"

"Honestly," "quietly," and their kin ("genuinely," "truly," "frankly") as sentence dressing. A model reaches for them to *perform* candor or understatement — "honestly, the best part was…", "a quietly powerful feature", "it quietly does the work." A human who is being honest doesn't announce it; a thing that is quiet doesn't need the adverb.

> Before: "Honestly, this was the part that quietly changed how the team worked."
> After: "This changed how the team worked."

The test: delete the adverb. If the sentence loses nothing, it was a tell.

---

## Calibration notes

- **Don't over-correct.** A document with zero em dashes, zero contrast pairs, and uniformly medium sentences reads as flattened — another kind of tell. The goal is human density, not zero.
- **Quoted material and the author's own verbatim phrasing are exempt.** If the author chose a word, don't "fix" it as a tell; flag it only if they ask.
- **Industry terms are not tells.** "Funnel," "discovery," "wireflow," "design system" are domain vocabulary. Keep them. The tells are rhetorical patterns, not jargon.
