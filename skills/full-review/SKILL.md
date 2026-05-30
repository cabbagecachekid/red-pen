---
name: full-review
description: Runs a structured multi-pass review of human-facing professional copy and presents findings as a before/after diff table with reasoning, lists what was deliberately left out, and waits for explicit sign-off before changing anything. The passes are AI tells, operator-vs-academic positioning, honesty and overclaim (catching silently inflated claims), tone and positioning, voice register, and fact verification. Use at any stage of refining or expanding copy with AI — not just at the end — when reviewing or workshopping a resume, cover letter, portfolio page, case study, proposal, or bio, when the user asks to "review my copy", "do a full review", "run the full pass", or polish writing for hiring managers or clients.
---

# Full Review

A disciplined, multi-pass review for high-stakes human-facing copy — resumes, cover letters, portfolio pages, case studies, proposals, bios. This is the orchestrator of the `red-pen` pack: it runs the full process and **delegates** the two focused checks (`ai-written-check`, `cringe-check`) rather than restating them, then adds the passes only it owns.

Use it at **any** stage of refining copy with AI, not only the final pass — any time you've drafted, expanded, or edited something with Claude and want to make sure the result still says what you meant and claims only what's true.

The first draft of any change is the **starting position for a conversation, not the final proposal.** Expect 2–4 iterations per piece.

## The six passes (run in order)

Run every pass explicitly and report under each heading, even if a pass is clean ("Pass 2: no issues").

1. **AI tells** — *delegate to the `ai-written-check` skill.* Apply it directly; do not restate its catalog here. (If it isn't installed, see the 10-second fallback in `references/PASSES.md`.)
2. **Operator vs. academic** — does the copy position the author as someone who *ships* or someone who *observes*? Every "research about X" framing should pair with a "so that &lt;decision shipped&gt;" clause. Studying is not the credential; the decision it unblocked is.
3. **Honesty / overclaim** — does any claim assert authority or scope the author doesn't have? **Never silently upgrade the scope of a claim.** This is the pass that catches inflation that crept in during AI editing — see the anti-inflation rules below.
4. **Tone / positioning** — *delegate to the `cringe-check` skill.* Apply it directly; do not restate its dimensions here.
5. **Voice register** — does each paragraph hold one register, or swerve from concrete-and-human to abstract industry-speak? The swerve is the tell.
6. **Fact verification** — for every verifiable fact (dates, conference and company names, titles, metrics, technical terms), push for a source rather than trusting recall. Memory is unreliable; sources beat memory. Flag any unsourced fact as "verify before sending."

## Anti-inflation rules (Pass 3, the heart of this pack)

These skills exist because AI editing can quietly *amplify* a claim the author never approved. Guard against it:

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

Passes 1 and 4 are the `ai-written-check` and `cringe-check` skills — install all three of `red-pen` together for the complete review. `references/PASSES.md` carries the full detail for the four passes this skill owns (2, 3, 5, 6) plus a brief fallback for 1 and 4 if those skills aren't present, so a review can still run standalone.
