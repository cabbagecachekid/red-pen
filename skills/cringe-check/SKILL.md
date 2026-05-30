---
name: cringe-check
description: Audits professional and application copy for tone and positioning that reads as cocky, parroting, or presumptuous — solo-hero framing where the author is the only agent, positioning-against unnamed others to look smart by contrast, parroting a job description's distinctive phrases verbatim, prescribing a client's reality or priorities in a proposal, undermining a polished deliverable with unsolicited "happy to convert it" offers, and overclaiming authority or flattening hobby and enterprise work into false parallel. Use when reviewing a resume, cover letter, portfolio page, proposal, or pitch, or when the user asks for a "cringe check" or worries their copy sounds arrogant, try-hard, or like it is sucking up.
---

# Cringe Check

Audit copy for the positioning moves that make a smart, qualified author look cocky or try-hard. This is a *tone and stance* check — it looks at how the author positions themselves relative to other people, the reader, and the truth. It does not touch sentence mechanics (that is the `ai-written-check` skill).

The frame to hold: the strongest copy reads as a **generous collaborator who is genuinely good**, not a solo hero or a sage on a mountain. Most cringe comes from the author accidentally instrumentalizing other people or claiming more than they own.

## How to run it

Walk the six dimensions below. For each hit, output: the **dimension name**, the **offending line quoted**, and a **collaborator-voice rewrite**. Be specific — a real rewrite, not "soften this."

## The six dimensions

**1. Solo-hero check.** Does every story use "I" as the only agent? Are partners — PMs, engineers, designers, leadership, participants — instrumentalized or invisible? Fix: name collaborators with their own agency.

**2. Positioning-against check.** Does the copy set up unnamed others (engineers, leadership, "most designers," "stock tools") as deficient so the author looks smart by contrast? Fix: let contrasts come from honest difference, not implicit putdown.

**3. Curiosity check.** Does the copy show *any* open question, uncertainty, or genuine interest in the reader's specific work — or is it all answers and claims? All-answers reads as closed and cocky.

**4. Generosity check.** Are the people in the stories collaborators, or background characters receiving the author's brilliance? Credit shared wins as shared.

**5. Live-question check.** Does the author name something they're still figuring out? (Especially load-bearing for research / AI roles, where admitting a live uncertainty *is* the credential.)

**6. JD-mirror check.** Does the copy lift the job description's most distinctive verbs or slogans verbatim ("kill bad ideas," "ship fast," "strategy-level not feature-level")? Verbatim lifts read as parroting. Soft echoes — same concept, the author's own words — are fine and usually desired.

## Two more, for client / proposal copy

**7. Don't-prescribe.** In a proposal, don't tell the client what *their* reality is — "the highest-risk feature in your product," "the biggest open question is whether users will pay," "if they don't trust it they'll leave." That reads as a stranger diagnosing their business. Bring **craft** (methodology), **relevant market understanding**, and **relevant experience** instead. Describe what the work can *surface*; don't preview its conclusions.

**8. Don't-undermine-bespoke.** When sending a polished, hand-built artifact (a custom deck, a tuned layout), don't tack on "happy to convert this to Figma/Notion/slides if easier." It undercuts the thing you just made and volunteers free work before the engagement is scoped. The format you sent *is* the format. (Format flexibility is fine when the artifact is genuinely rough — a draft doc, a quick recording.)

## Overclaim and scale (runs through all of the above)

- **Authority you don't have:** "leads," "owns," "decides," "built from scratch," "established the function" — only if literally true. Contributor ≠ owner. Early adopter ≠ the person who sets strategy.
- **False parallelism:** do not use matched grammar (parallel verbs, parallel clauses) to imply that a weekend project and a multi-year enterprise effort are the same scale. Parallel grammar implies parallel scope to the reader. Keep different scales in different scopes.
- If asked to make a small thing sound bigger, **decline and surface the scale issue** rather than inflating it.

For worked examples and the reasoning behind each dimension, see `references/POSITIONING.md`.

## What this skill does NOT do

- It does not check sentence mechanics or AI tells — use `ai-written-check`.
- It does not verify facts — that belongs to `full-review`.
- It never inflates. When the honest version is smaller, it says so.
