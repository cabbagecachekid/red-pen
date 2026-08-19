---
name: full-review
description: Runs a structured multi-pass review of human-facing professional copy and presents findings as a before/after diff table with reasoning, lists what was deliberately left out, and waits for explicit sign-off before changing anything. The passes are AI tells, a register-supplied positioning pass, honesty and distortion (catching claims silently inflated OR softened), tone and positioning, voice register, and fact verification. Calibration comes from a register file (job-seeker by default; publication included) and an optional one-page profile, so the same review serves résumés, editorials, or a house style; add a register for anything else. Use at any stage of refining or expanding copy with AI — not just at the end — when reviewing or workshopping a resume, cover letter, portfolio page, case study, proposal, or bio, when the user asks to "review my copy", "do a full review", "run the full pass", or polish writing for hiring managers or clients.
---

# Full Review

A disciplined, multi-pass review for high-stakes human-facing copy — resumes, cover letters, portfolio pages, case studies, proposals, bios. This is the orchestrator of the `red-pen` pack: it runs the full process and **delegates** the two focused checks (`ai-written-check`, `cringe-check`) rather than restating them, then adds the passes only it owns.

Use it at **any** stage of refining copy with AI, not only the final pass — any time you've drafted, expanded, or edited something with Claude and want to make sure the result still says what you meant and claims only what's true.

The first draft of any change is the **starting position for a conversation, not the final proposal.** Expect 2–4 iterations per piece.

## Register and profile (load before any pass)

The mechanism below is register-independent; the *calibration* is not. Resolve it in this order, once per review:

1. If `.red-pen/profile.md` exists in the working directory, load it. Its frontmatter names a `register:`; load `registers/<that>.md` from the pack root (two directories above this skill's folder in the plugin or cloned repo). The profile's voice test, never-phrases, scope guard, and identity rules bind every pass.
2. Otherwise ask once: "Which register — `job-seeker`, `publication`, or a path to a profile?" Do not ask again in the same review.
3. If the author declines or the question can't be asked, run **`job-seeker` with no profile** — the pack's original behavior.
4. If the register file itself cannot be found (this skill was copied standalone, without `registers/`), run the job-seeker rules that are inline below and say so in the first line of the report; do not invent a register.

State the resolved register in the first line of the report. If the profile has a **scope guard** and the draft falls outside it, say so and stop; do not drag the draft into a register it doesn't belong to.

## The six passes (run in order)

Run every pass explicitly and report under each heading, even if a pass is clean ("Pass 2: no issues").

1. **AI tells** — *delegate to the `ai-written-check` skill.* Apply it directly; do not restate its catalog here. (If it isn't installed, see the 10-second fallback in `references/PASSES.md`.)
2. **Register pass** — *supplied by the register file's `## Pass 2 rule`.* For `job-seeker` this is operator-vs-academic (ships vs. observes; every "research about X" pairs with a "so that &lt;decision shipped&gt;"). For `publication` it is the mechanical house-style pass. Report it under the name the register gives it.
3. **Honesty / distortion** — does any claim now say more, or less, than the author's record? **Never silently change the scope of a claim in either direction.** The register's `polarity.distortion` says which direction AI editing damages this artifact (inflate for job-seeker, deflate for publication) and its `## Distortion watchlist` lists the tells — see the anti-distortion rules below.
4. **Tone / positioning** — *delegate to the `cringe-check` skill.* Apply it directly; do not restate its dimensions here.
5. **Voice register** — does each paragraph hold one register, or swerve from concrete-and-human to abstract industry-speak? The swerve is the tell.
6. **Fact verification** — for every verifiable fact (dates, conference and company names, titles, metrics, technical terms), push for a source rather than trusting recall. Memory is unreliable; sources beat memory. Flag any unsourced fact as "verify before sending." Claims the register lists under `## Needs-no-source claims` (opinion and analytical framing, for publication) are reported as *opinion — no source required*, not as gaps.

## Anti-distortion rules (Pass 3, the heart of this pack)

These skills exist because AI editing can quietly *change the size* of a claim the author never approved — amplify it in application copy, soften it in argument. **Never inflate, never deflate.** **Polarity is emphasis, not exclusion.** Changing the size of a factual claim against the author's record is a violation in every register, in either direction; the register only says which direction to look hardest and supplies the style-level tells (softening, swagger) that are register-specific. The rules below are the job-seeker (inflation) form and remain in force under every register:

- **Never silently upgrade scope.** If an edit makes a claim bigger than the source — broader ownership, larger team, more authority, an earlier origin — STOP, flag it, and ASK. Do not inflate unprompted.
- **Scope-amplifier watchlist:** "solo," "founded," "created," "established," "built from scratch," "ran/led the program," "owned," "didn't exist before," "the entire." Each one is a claim that must match what actually happened.
- **Read "solo" conservatively.** "Solo" usually means *individual contribution on a specific project*, not *sole founder of a function or program*. Never expand it past per-project scope without explicit confirmation.
- **Match the record, not the memory.** When raw material already sounds inflated, treat that as a question to verify, not a fact to polish.

## Output format (non-negotiable)

- **Before/after diff table** with three columns: *Before* · *After* · *Why*. Every proposed change is a row. No silent edits.
- **What was kept out.** List what you deliberately did NOT include or change, and why — especially anything disclosure-sensitive you withheld. As important as what you put in.
- **Options get a recommendation.** When you offer choices, present them as options *and* state your recommendation with honest reasoning (name the trade-off, not just the upside). A bare list makes the author decide cold.
- **Use the author's own words.** If they gave you a phrase, use it verbatim. Don't paraphrase their voice into yours. Keep industry vocabulary intact.

## The sign-off rule

**Never change the file until the author explicitly says "land it" (or equivalent).** Review proposes; the author disposes. Draft and iterate in a working/scratch location; only move locked or near-locked text into the live/published location.

If the author pushes back with feedback you think weakens the writing, say so and explain why — honest disagreement over reflexive agreement. If they're right and you missed something, own it directly ("I missed this; my earlier pass failed because…"). Don't soften, defend, or bury the miss.

## Composition

Passes 1 and 4 are the `ai-written-check` and `cringe-check` skills — install all three of `red-pen` together for the complete review; both read the same resolved register. `references/PASSES.md` carries the full detail for the four passes this skill owns (2, 3, 5, 6) plus a brief fallback for 1 and 4 if those skills aren't present, so a review can still run standalone. Registers live in `registers/`; the profile template and examples in `profile.template.md` and `examples/`.
