# Full Review — Per-Pass Detail

Reference for `full-review`. SKILL.md has the process and output rules; this file has the full detail for the four passes this skill **owns** (2, 3, 5, 6). Passes 1 and 4 are delegated to the `ai-written-check` and `cringe-check` skills — they are not restated here, only pointed to.

---

## Pass 1 — AI tells (delegated)

**Apply the `ai-written-check` skill.** Its `references/TELLS.md` is the catalog; don't duplicate it.

*Fallback only if that skill isn't installed* (10-second version — then recommend installing it): scan for em dashes, triple-list anaphora, "not X but Y" pairs, spatial/cost metaphors, "architect" as a verb, "across" overuse, engineered cadence, register swerves, builder slang, and universal claims ("everyone"). Flag with a rule name and a concrete rewrite. Density is the tell, not presence.

---

## Pass 2 — Operator vs. academic (owned)

The question: does this read as someone who *ships product decisions* or someone who *studies and muses*? Hiring managers and clients buy the former.

The fix pattern: every "research about X" needs a "so that &lt;decision / shipped change&gt;."

> Before: "I ran a study on how people perceive trust signals in checkout."
> After: "I ran a study on trust signals in checkout, so we knew which two badges to keep and which four to cut before the redesign shipped."

Studying is the activity; the unblocked decision is the credential. If a line describes research with no downstream decision, flag it and ask what shipped because of it.

---

## Pass 3 — Honesty / overclaim (owned) — the anti-inflation pass

This is the reason the pack exists: AI editing can quietly *amplify* a claim the author never approved. The job here is to catch any claim that asserts more authority, scope, or origin than the source supports — and to **surface and ask rather than inflate.**

### Never silently upgrade scope
If an edit makes a claim bigger than the raw material — broader ownership, a larger team, more authority, an earlier origin, a founding role — STOP, flag the gap, and ask. Do not polish an inflated claim into a "fact."

### Scope-amplifier watchlist
Trigger words that demand a match against what actually happened:
- "solo," "single-handedly," "the entire"
- "founded," "created," "established," "built from scratch," "set up the function"
- "ran / led / owned the program"
- "didn't exist before," "first ever"

### Read "solo" conservatively
"Solo" almost always means *individual contribution on a specific project* — not *sole founder of a function or program*. Never expand "solo" past per-project scope without explicit confirmation from the author.

> Real failure this pass exists to prevent: "solo" (meant as *I did this project by myself*) got edited into "founded and ran the research program" at a first UX job — an origination claim the author never made and a single reference check would destroy. The honest, still-strong version credits the specific project work, not a founding role.

### Match the record, not the memory
When raw material already sounds inflated ("built scalable processes from scratch," "established the operating model"), treat it as a question to verify, not a fact to keep. Did the author *originate* the thing, or join an existing team/system and improve it? "Joined an existing team and made it measurably better" is a strong, defensible claim.

---

## Pass 4 — Tone / positioning (delegated)

**Apply the `cringe-check` skill.** Its `references/POSITIONING.md` is the catalog; don't duplicate it.

*Fallback only if that skill isn't installed* (10-second version — then recommend installing it): audit for solo-hero framing, positioning-against unnamed others, parroting the JD's distinctive phrases, prescribing a client's reality in proposals, undermining bespoke work with "happy to convert" offers, and false-parallelism that flattens hobby and enterprise scope.

---

## Pass 5 — Voice register (owned)

Read each paragraph for a register swerve: a grounded, human opening that pivots into abstract industry-speak (or vice versa). A model often can't hold one voice across a paragraph; a human author usually can. Pick the register the human half is in and bring the rest to it.

> Swerve: "I sat with twelve users and watched them struggle. This surfaces a meaningful opportunity to optimize engagement across the conversion surface."
> Fixed: "I sat with twelve users and watched them struggle. The struggle was always the same screen — that's the one to fix."

---

## Pass 6 — Fact verification (owned)

For every verifiable historical fact, push for a source instead of trusting recall: dates, conference names, university names, project titles, metrics, technical terminology, employer details.

Real failures this pass has caught:
- A conference cited as one org/year was actually a different org and year.
- A university name was wrong (wrong institution entirely).
- A "50% reduction" was the *target*; the *achieved* number was 41%.
- A product/tool name was misremembered.
- A launch year was off by one.

Flag every unsourced verifiable fact as **"verify before sending."** Don't let a confident-sounding number through on memory alone. Sources beat memory, every time.

---

## Output & process reminders (from SKILL.md, repeated for standalone runs)

- Before/after diff table with a **Why** column. No silent edits.
- List **what was kept out** and why.
- Pair options with an explicit, honest **recommendation**.
- Use the **author's own words** verbatim when given.
- **Never land** without explicit sign-off. Draft in scratch, land in published.
- Push back when feedback weakens the writing; own misses directly when you're wrong.
