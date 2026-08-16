# HANDOFF — red-pen config split (branch `config-split`)

Written 2026-08-16. Read this first if picking up cold.

## State in one sentence
The three-layer split (mechanism / register / profile) is built and committed on local branch `config-split` (9 commits ahead of main); 4 of 5 known-answer tests pass, the 5th was mis-specified and the decision to fix the spec (not the code) is made; **nothing is pushed to GitHub** — Caitlin's rule: no push, no PR until she has reviewed and says "open it."

## Where things are
- Repo: `~/Projects/skills/public/red-pen/`, branch `config-split`. Main is untouched at `c5c6e22`.
- Spec: `docs/superpowers/specs/2026-08-15-config-split-design.md`
- Tests: `tests/fixtures/{resume-overclaim,editorial-softened}.md`, `tests/KNOWN-ANSWERS.md` (baseline + post-split results recorded)
- Registers: `registers/job-seeker.md`, `registers/publication.md`
- Profile: `profile.template.md`, `examples/profile-little-bird.md`
- Source feedback + decisions: `~/Inbox/red-pen-feedback_2026-08-15_Bird.md`
- Task: `~/Documents/Obsedian/Obsidian/Vault-1/My notes/_workspace/build.md` line 11

## Decisions made by Caitlin (do not re-open)
- Scope A first (config split only); more registers (grant, founder, academic) later.
- Bundle Bird's fork as the publication example, credited, MIT — permission already given in writing.
- Ship a scrubbed caitlin-voice as an example profile — DEFERRED to after this round (she must review the scrub).
- Home/name undecided; stays in red-pen for now, version 0.2.0.
- **Polarity is EMPHASIS, not exclusion** (2026-08-16): record distortion is caught in every register both directions; softening/swagger tells are register-specific. Principle now stated in full-review SKILL.md.
- Added ai-written-check tell #13: sincerity adverbs ("honestly", "quietly").
- Work in tiny turns; she is watching usage.

## Remaining steps (tiny, in order)
1. `tests/KNOWN-ANSWERS.md`: rewrite row 4 expected → "flags the inflation (base rules)"; delete the OPEN section, note it was resolved = emphasis.
2. Spec: same one-line fix to row 4 in the Testing section.
3. Optional one-liner: job-seeker watchlist gets a deflation bullet (résumé that under-claims the record) — Caitlin hasn't ruled; ask.
4. Caitlin reviews the diff (`git diff main..config-split --stat`, then the SKILL.md files).
5. Only on her word: push branch, open PR. Then landing page reorder (red-pen leads) as a separate task.

## Evidence it works
Three subagent runs on 2026-08-16 against the new files (recorded in KNOWN-ANSWERS.md): default resolves to job-seeker with identical findings to pre-split; publication + Little Bird profile flags hedge, de-cursing, and false-balance closer and exempts the thesis from sourcing; publication without profile still catches the résumé inflation via base rules (the emphasis behavior). Pre-split baseline confirmed the editorial softenings were previously invisible.
