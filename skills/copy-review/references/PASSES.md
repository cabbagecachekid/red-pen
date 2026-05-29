# Copy Review — Per-Pass Detail

Reference for `copy-review`. SKILL.md has the process and output rules; this file has the per-pass detail and lets the review run standalone when `ai-written-check` and `cringe-check` aren't installed.

---

## Pass 1 — AI tells (standalone summary)

If `ai-written-check` is installed, use it. Otherwise scan for, in rough priority order:

- **Em dashes** (the #1 tell → periods/colons; keep only as header separators)
- **Triple-list anaphora** (1/page ok, 2+ is a tell)
- **"Not X but Y" pairs** (1/piece ok, more is a tell)
- **Spatial metaphors** for abstract ideas → concrete nouns
- **Cost/economic metaphors** for non-economic things → literal language
- **"Architect" as a verb** → "design"/"build"
- **"Across" overuse**, **"from X to Y to Z" arcs**, **engineered cadence**
- **Voice-register swerves** within a paragraph
- **Builder/startup slang** in formal copy
- **Universal claims** ("everyone", "across the board") → scope to what was observed

Flag with a rule name and a concrete rewrite. Density is the tell, not presence — don't over-correct to a flattened zero.

---

## Pass 2 — Operator vs. academic

The question: does this read as someone who *ships product decisions* or someone who *studies and muses*? Hiring managers and clients buy the former.

The fix pattern: every "research about X" needs a "so that <decision / shipped change>."

> Before: "I ran a study on how people perceive trust signals in checkout."
> After: "I ran a study on trust signals in checkout, so we knew which two badges to keep and which four to cut before the redesign shipped."

Studying is the activity; the unblocked decision is the credential. If a line describes research with no downstream decision, flag it and ask what shipped because of it.

---

## Pass 3 — Honesty / overclaim

Does the copy claim authority the author doesn't have? ("leads," "owns," "decides," "picks the tools.")

### Slop-creep origination sub-check
Raw material often arrives with inflation already baked in. Trigger phrases:
- "built X from scratch"
- "established the operating model"
- "created the function / the practice / the team"
- "set up the system"
- "didn't exist before"

When you see these, STOP and verify: did the author *originate* the thing, or join an existing team/system and improve it? "Joined an existing team and made it measurably better" is a strong, defensible claim. "Built it from scratch" when they joined something existing is an overclaim a single reference check destroys.

> Failure example caught in the wild: "Built scalable research processes from scratch, establishing the operating model for a function that didn't exist before" — when the author actually joined an existing UX research team. The honest, still-strong version credits what they added, not what they founded.

---

## Pass 4 — Tone / positioning (standalone summary)

If `cringe-check` is installed, use it. Otherwise audit for:

- **Solo-hero:** author the only agent; collaborators erased → name them.
- **Positioning-against:** building up by implying unnamed others are deficient → contrast on method, not putdown.
- **Curiosity / live-question:** all answers, no open questions → add one genuine uncertainty (especially for research/AI roles).
- **Generosity:** shared wins credited as shared.
- **JD-mirror:** verbatim lifts of the JD's distinctive verbs/slogans → soft echoes in the author's own words instead.
- **Don't-prescribe (proposals):** don't diagnose the client's reality/risks/priorities; bring craft, market understanding, experience; describe what research surfaces, don't preview conclusions.
- **Don't-undermine-bespoke:** no unsolicited "happy to convert to Figma/Notion" on polished artifacts.
- **Overclaim & scale:** no false parallelism between hobby and enterprise work; keep different scales in different scopes.

---

## Pass 5 — Voice register

Read each paragraph for a register swerve: a grounded, human opening that pivots into abstract industry-speak (or vice versa). A model often can't hold one voice across a paragraph; a human author usually can. Pick the register the human half is in and bring the rest to it.

> Swerve: "I sat with twelve users and watched them struggle. This surfaces a meaningful opportunity to optimize engagement across the conversion surface."
> Fixed: "I sat with twelve users and watched them struggle. The struggle was always the same screen — that's the one to fix."

---

## Pass 6 — Fact verification

For every verifiable historical fact, push for a source instead of trusting recall: dates, conference names, university names, project titles, metrics, technical terminology, employer details.

Real failures this pass has caught:
- A conference cited as "AAA 2014" was actually a different org and year.
- "San Diego University" was the wrong institution name.
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
