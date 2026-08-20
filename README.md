# red-pen

Three composable [Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that keep AI-assisted writing **honest and yours**: for resumes, cover letters, portfolio pages, case studies, proposals, and bios.

They came out of a real problem: while refining a resume and portfolio *with* AI, edits crept in that silently inflated a claim. "Solo" (meant as *I did this project myself*) drifted into something like *founded and ran a research program*, alongside generic placeholder headers that weren't the author's voice at all. No one approved those changes; they just accumulated.

`red-pen` does not hide that you used AI. It assumes the healthy case: you're collaborating with Claude to refine, expand, or draft your own writing. Its job is to make sure the result still **says what you meant and claims only what's true.**

## The skills

| Skill | What it does | Invoke it when you say |
|-------|--------------|------------------------|
| **ai-written-check** | Flags the *mechanical* tells that make prose read as machine-written: em dashes, triple-lists, "not X but Y" pairs, spatial/cost metaphors, "architect" as a verb, engineered cadence, register swerves, builder slang, universal claims, and generic placeholder copy. Each flag comes with a concrete rewrite. | "AI-written check", "does this sound like AI?", "make this sound like me" |
| **cringe-check** | Audits *tone and positioning*: solo-hero framing, positioning-against others, parroting the job description, prescribing a client's reality, undermining bespoke work, and overclaiming authority or flattening scale. | "cringe check", "does this sound cocky / try-hard?" |
| **full-review** | The orchestrator. Runs a six-pass review, **delegating** the AI-tells and tone passes to the two checks above and owning the rest: the register pass, honesty and distortion (a claim made bigger or smaller than the record), voice register, and fact verification. Presents a before/after diff table, lists what it deliberately kept out, and waits for your explicit sign-off before changing anything. Use it at any stage, from first expansion to final pass. | "review my copy", "do a full review", "polish this for hiring managers" |

The three are independent. Install one, two, or all three. `full-review` *delegates* to the other two when they're present (no duplicated rules) and falls back to brief reference notes when they aren't.

## Why "red-pen"

It's the editor's pass: a rigorous second reader that holds your writing to a standard before it goes out. The record-fidelity pass is the heart of it. It **never silently changes the size of a claim.** If an edit makes something bigger than the truth (broader ownership, a larger team, an earlier origin, a founding role you didn't have), or smaller than it, it stops and *asks* rather than polishing the distortion into a "fact."

## Design principles

Built to [Anthropic's skill-authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices):

- **Progressive disclosure.** Each `SKILL.md` is a lean working checklist; the full catalogs, worked examples, and edge cases live in `references/` and load only when needed.
- **Composition over duplication.** `full-review` invokes the two checks rather than restating them, so each rule has a single source of truth.
- **No scripts.** These are judgment tasks, so the guidance is inline instructions rather than executable code.
- **Reasoning with every rule.** Every rule states *why* it matters and gives a fix, so the model can generalize.
- **Density over presence.** Most "tells" are fine once; the skills flag the pile-up rather than every instance, to avoid over-corrected, flattened prose.

## Install

Skills do **not** sync between Claude Code, Claude Desktop, and the API. Install on each surface you use.

### Claude Code

**Option A: as a plugin (recommended, stays updated)**

In Claude Code, add this repo as a plugin marketplace, then install the plugin:

```
/plugin marketplace add cabbagecachekid/red-pen
/plugin install red-pen@red-pen
```

To update later: `/plugin marketplace update red-pen`.

**Option B: manual (clone and copy)**

Copy whichever skill folders you want into `~/.claude/skills/` (global) or `<project>/.claude/skills/` (project-scoped). Claude Code auto-discovers them on next launch.

```bash
git clone https://github.com/cabbagecachekid/red-pen.git
cd red-pen
cp -r skills/ai-written-check ~/.claude/skills/
cp -r skills/cringe-check     ~/.claude/skills/
cp -r skills/full-review      ~/.claude/skills/
```

Verify with `/skills`; the three should appear in the list.

Standalone copies run the `job-seeker` register (the v0.1 behaviour). Registers and profiles need the plugin install or the cloned repo.

### Claude Desktop / claude.ai

Each skill uploads as its own zipped folder. Works on every plan, including Free; it just needs code execution turned on (Settings, then Capabilities, then "Code execution and file creation").

1. Clone the repo and zip each skill folder:
   ```bash
   git clone https://github.com/cabbagecachekid/red-pen.git
   cd red-pen/skills
   for s in ai-written-check cringe-check full-review; do zip -r "$s.zip" "$s"; done
   ```
2. In Claude Desktop, go to **Settings → Capabilities → Skills** and upload each `.zip` separately.
3. Start a chat and ask for a "cringe check" or "AI-written check". The skill triggers automatically.

Standalone copies run the `job-seeker` register (the v0.1 behaviour). Registers and profiles need the plugin install or the cloned repo.

### Using the skills

Once installed, no special command is needed. Just ask in plain language:

- *"Run an AI-written check on this cover letter."*
- *"Cringe check this paragraph. Does it sound arrogant?"*
- *"Do a full review of my resume."*

`full-review` will pull in `ai-written-check` and `cringe-check` automatically when all three are installed, and falls back to its own reference notes if they aren't.

## Registers and profiles (v0.2)

The three skills are one **mechanism** (sign-off first, never inflate *or deflate*, preserve voice, report the gaps), and the mechanism is register-independent. What differs per kind of artifact is the **calibration**: which way AI editing damages it. Résumés inflate. Editorials soften. So the calibration lives in config, not code:

| Layer | File | Who writes it |
|---|---|---|
| Mechanism | the three `SKILL.md` files | the pack |
| Register pack | `registers/<name>.md`: polarity per pass, watchlist, tell extensions, needs-no-source claims | the pack ships `job-seeker` and `publication`; add your own |
| Profile | `.red-pen/profile.md` in your writing folder, from `profile.template.md`: voice test, never-phrases, scope guard, identity rules; names its register | you |

No profile, no answer to "which register?" → `job-seeker`, exactly the original behavior.

The `publication` register and `examples/profile-little-bird.md` are adapted from **little-bird-final-pass** by Bird ([alittlebirdseyeview.com](https://www.alittlebirdseyeview.com)), MIT. That fork is what showed the split was real: same passes, opposite polarity.

## Repository layout

```
.claude-plugin/      plugin.json + marketplace.json (plugin distribution)
skills/
  ai-written-check/  SKILL.md + references/TELLS.md
  cringe-check/      SKILL.md + references/POSITIONING.md
  full-review/       SKILL.md + references/PASSES.md
registers/           job-seeker.md, publication.md: calibration per artifact type
profile.template.md  copy to .red-pen/profile.md where you write
examples/            profile-little-bird.md: a worked publication profile
tests/               fixtures + KNOWN-ANSWERS.md: the polarity-flip proof
```

## License

MIT. See [LICENSE](LICENSE).
