# red-pen config split — design (2026-08-15)

Status: DRAFT for Caitlin's review. Local only; nothing pushed until fixtures pass.
Origin: feedback + fork from Bird (see ~/Inbox/red-pen-feedback_2026-08-15_Bird.md). Fork is MIT, permission granted in writing.

## Goal
Split red-pen into three layers so the same review mechanism serves any artifact:
1. **Mechanism** (code, the three SKILL.md files) — register-independent.
2. **Register pack** (config, `registers/<name>.md`) — which way AI editing damages this kind of artifact, and the pass rules that follow.
3. **Profile** (config, one page, user-owned) — voice, identity rules, scope guard; names its register.

Non-goal for this release: new registers beyond job-seeker and publication; landing-page reorder.

## Layer 1 — mechanism changes (and only these)
- Contract rule 2: "never inflate" → **"never inflate, never deflate."**
- full-review Pass 3: renamed **anti-distortion**. Direction (inflate / deflate / both) comes from the register. The watchlist comes from the register.
- full-review Pass 2: becomes a **register-supplied pass**. Job-seeker fills it with operator-vs-academic (today's text). Publication fills it with the mechanical house-style pass.
- full-review Pass 6: add a claim category **"needs no source"**, declared by the register (publication: opinion and analytical framing; job-seeker: none).
- cringe-check: its dimensions become **polarity-aware** — the same mechanism reads the register's direction; POSITIONING.md keeps the job-seeker calibration but is loaded through the register, not hard-wired.
- ai-written-check: TELLS.md stays the core; register may **append** tells.
- Unchanged: diff-table-before-any-change, sign-off gate, gaps report, judgment-calls-vs-violations, six-pass order and headings.

## Layer 2 — register file format (`registers/<name>.md`)
Frontmatter: `name`, `polarity` (per pass: inflate | deflate | both), `credit` (optional).
Sections: `## Pass 2 rule`, `## Distortion watchlist`, `## AI-tell extensions`, `## Tone dimensions`, `## Needs-no-source claims`, `## Mechanical style pass` (optional).
Ship: `job-seeker.md` (extracted verbatim from current SKILL.md/POSITIONING.md text — no rewording), `publication.md` (from Bird's fork; credited "Bird, alittlebirdseyeview.com, MIT").

## Layer 3 — profile
`profile.template.md` at repo root. Frontmatter: `register: <name>`. Sections: voice test (real before/after pairs), never-phrases, register per surface, scope guard (what this artifact refuses to be), identity/masthead rules, source list.
Examples: `examples/profile-caitlin.md` (scrubbed from personal caitlin-voice; Caitlin reviews before it leaves personal/), `examples/profile-little-bird.md` (from fork, entity section).

## Loading rule
1. Look for `.red-pen/profile.md` in the working directory. If found, load it and its named register.
2. Else ask once: "Which register / profile?" (offer job-seeker, publication, or a path).
3. If declined: **job-seeker, no profile** — byte-for-byte today's behavior.
Version: minor bump (backwards compatible).

## Testing — break the check first
Fixtures in `tests/fixtures/`:
- `resume-overclaim.md` — one planted scope upgrade ("led the program" where source says "contributed").
- `editorial-softened.md` — one planted hedge ("arguably") + one de-cursed word + one false-balance closer.
Known answers:
- job-seeker on resume → flags the overclaim. job-seeker on editorial → does NOT flag the hedge (wrong polarity).
- publication on editorial → flags all three plants. publication on resume → does NOT flag the overclaim.
- no profile, no register → identical output to current version on the resume fixture (regression).
Pass criterion: all five outcomes observed by running the skills, not by reading them.

## Out of scope / follow-ups
- Grant, founder/investor, academic registers (phase C).
- Landing page: red-pen leads, neon-jetpack accessories.
- MCPMarket listing.
