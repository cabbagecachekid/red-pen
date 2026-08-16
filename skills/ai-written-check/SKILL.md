---
name: ai-written-check
description: Detects the mechanical tells that make professional prose read as AI-generated — em dashes, triple-list anaphora, "not X but Y" antithetical pairs, spatial and economic metaphors for abstract ideas, "architect" as a verb, engineered sentence cadence, mid-paragraph register swerves, builder/startup slang, sincerity adverbs ("honestly", "quietly"), and unfalsifiable universal claims ("everyone", "across the board"). Use when reviewing or editing a resume, cover letter, portfolio page, case study, proposal, bio, or any human-facing copy, or when the user asks for an "AI-written check", "AI tells", says copy "sounds like AI", or asks to make writing sound less generated.
---

# AI-Written Check

Scan human-facing prose for the mechanical patterns that signal machine authorship, and propose a concrete rewrite for each. This is a *prose* check — it looks at sentence mechanics and word choice, not at tone or positioning (that is the `cringe-check` skill).

**What this is for.** This is not about hiding that AI was involved. It assumes the healthy case: you're collaborating with Claude to refine, expand, or draft your own writing. The job is to keep the result *aligned with your intent and your voice* — so the words still sound like you wrote them, not like a model smoothed them into generic copy. None of these skills are for making AI do the writing for you.

## How to run it

1. Read the copy once for sense.
2. Walk the checklist below. For every hit, output: the **rule name**, the **offending text quoted**, and a **specific rewrite** — not just "this sounds AI."
3. Respect the thresholds. Some patterns are fine once and only become a tell when repeated. Count occurrences before flagging.
4. End with a one-line verdict: clean, light touch-up, or heavy.

Never flag without a rewrite. The point is to fix the prose, not to label it.

## The checklist

| Tell | Threshold | Fix |
|------|-----------|-----|
| **Em dash (—)** | The #1 tell. Flag almost every one in body copy. | Period, colon (sparingly), or a shorter sentence. Acceptable only as a structural separator in a header. |
| **Triple-list anaphora** ("about money, about trust, about control") | 1 per page is fine; 2+ is a tell. | Cut to a single clause or break into separate sentences. |
| **"Not X, but Y" / "X, not Y"** antithetical pairs | 1 per piece is fine; more is a tell. | State the point directly without the contrast scaffold. |
| **Spatial metaphors for abstract concepts** ("corners of their financial lives", "the territory of taxes", "the current frontier") | Flag each. | Use the concrete noun the metaphor is standing in for. |
| **Economic/cost metaphors for non-economic things** ("make rigor the cheap option", "the time tax", "the heavy lift") | Flag each. | Say the literal thing. |
| **"Architect" as a verb** | Flag each. | "Design" or "build." |
| **"Across" overuse** ("across the funnel", "across products", "across teams") | Flag clusters. | Name the specific thing, or drop the word. |
| **"From X to Y to Z" career/idea arcs** | Flag when a plainer sentence works. | Rewrite as a direct sentence. |
| **Engineered sentence cadence** (deliberate alternation of very short and very long sentences) | Flag when the rhythm feels manufactured. | Let sentence length follow meaning, not a beat. |
| **Voice-register swerve** | Flag any paragraph that opens concrete-and-human and pivots to abstract industry-speak. | Stay in one register; the swerve is the tell. |
| **Builder/startup subculture slang** ("vibe coding", "shipping", "hot takes", "cracked at") | Flag each in formal copy. | A neutral substance-equivalent term. |
| **Unfalsifiable universal claims** ("everyone", "all", "every", "universally", "across the board") | Question each. | Scope it to the specific people/context actually observed. "Affects everyone" is itself an AI-pitch tell. |
| **Sincerity adverbs** ("honestly", "quietly", "genuinely", "truly", "frankly" as dressing) | Flag each. | Delete the adverb; if the sentence loses nothing, it was a tell. |
| **Generic placeholder / template copy** (fill-in-the-blank headers, "Welcome to my portfolio", "I'm passionate about X", boilerplate section intros that could belong to anyone) | Flag each. | Replace with something specific and true to the author — their actual words, project, or point of view. Filler that "isn't the vibe" is a tell that the line was generated, not authored. |

## Why these matter

These patterns are how a reader's pattern-matcher flips to "a model wrote this." Most are individually harmless — the damage is *density*. One em dash is invisible; six is a signature. Apply the thresholds rather than nuking every instance, or the rewrite reads as over-corrected.

For the full catalog with worked before/after examples and edge cases, see `references/TELLS.md`.

## What this skill does NOT do

- It does not judge tone, arrogance, or positioning — use `cringe-check`.
- It does not verify facts or claims — that belongs to a full review (`full-review`).
- It does not rewrite wholesale. It flags and proposes; the author decides.

## Register extensions

`references/TELLS.md` is the core catalog for every register. If a register is resolved (see `full-review`: `.red-pen/profile.md` → ask once → default `job-seeker`), also apply the tells under its `## AI-tell extensions` — for `publication` that adds engineered contrast constructions, stock AI vocabulary, false-balance closers, symmetrical paragraph engineering, and restating summary paragraphs. Report core and extension hits under one heading; note which register supplied each extension.
