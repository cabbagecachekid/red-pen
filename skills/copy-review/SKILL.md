---
name: copy-review
description: Runs a structured multi-pass review of human-facing professional copy and presents findings as a before/after diff table with reasoning, lists what was deliberately left out, and waits for explicit sign-off before changing anything. The passes are AI tells, operator-vs-academic positioning, honesty and overclaim, tone and positioning, voice register, and fact verification. Use when reviewing or workshopping a resume, cover letter, portfolio page, case study, proposal, or bio, when the user asks to "review my copy", "do a full review", polish writing for hiring managers or clients, or run both an AI-written check and a cringe check together.
---

# Copy Review

A disciplined, multi-pass review for high-stakes human-facing copy — resumes, cover letters, portfolio pages, case studies, proposals, bios. This is the orchestrator: it runs the full process and composes the focused `ai-written-check` and `cringe-check` skills into a single review with a consistent output format and a hard sign-off rule.

The first draft of any change is the **starting position for a conversation, not the final proposal.** Expect 2–4 iterations per piece.

## The six passes (run in order)

Run every pass explicitly and report under each heading, even if a pass is clean ("Pass 2: no issues").

1. **AI tells** — mechanical patterns that read as machine-written. Apply the `ai-written-check` skill if available; otherwise use `references/PASSES.md`.
2. **Operator vs. academic** — does the copy position the author as someone who *ships* or someone who *observes*? Every "research about X" framing should pair with a "so that <decision shipped>" clause. Studying is not the credential; the decision it unblocked is.
3. **Honesty / overclaim** — does any claim assert authority the author doesn't have? Includes the **slop-creep origination sub-check**: when raw material says "built from scratch," "established," "created the function," "didn't exist before," STOP and verify whether the author actually originated the thing or joined something existing.
4. **Tone / positioning** — cocky, parroting, presumptuous? Apply the `cringe-check` skill if available; otherwise use `references/PASSES.md`.
5. **Voice register** — does each paragraph hold one register, or swerve from concrete-and-human to abstract industry-speak? The swerve is the tell.
6. **Fact verification** — for every verifiable fact (dates, conference and company names, titles, metrics, technical terms), push for a source rather than trusting recall. Memory is unreliable; sources beat memory. Flag any unsourced fact as "verify before sending."

## Output format (non-negotiable)

- **Before/after diff table** with three columns: *Before* · *After* · *Why*. Every proposed change is a row. No silent edits.
- **What was kept out.** List what you deliberately did NOT include or change, and why — especially anything disclosure-sensitive you withheld. This is as important as what you put in.
- **Options get a recommendation.** When you offer the author choices, present them as options *and* state your recommendation with honest reasoning (name the trade-off, not just the upside). A bare list of options makes the author do all the deciding cold.
- **Use the author's own words.** If they gave you a phrase, use it verbatim. Don't paraphrase their voice into yours. Keep industry vocabulary intact.

## The sign-off rule

**Never change the file until the author explicitly says "land it" (or equivalent).** Review proposes; the author disposes. Draft and iterate in a working/scratch location; only move locked or near-locked text into the live/published location.

If the author pushes back with feedback you think weakens the writing, say so and explain why — honest disagreement over reflexive agreement. If they're right and you missed something, own it directly ("I missed this; my earlier pass failed because…"). Don't soften, defend, or bury the miss.

## Composition & standalone use

If `ai-written-check` and `cringe-check` are installed, invoke them for passes 1 and 4 to get the full catalogs. If they are not installed, `references/PASSES.md` carries enough of each to run the review standalone — it degrades gracefully.

For the full per-pass detail (the operator "so that" rewrite pattern, the slop-creep examples, disclosure handling, and the fact-verification failure log), see `references/PASSES.md`.
