# red-pen

Three composable [Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that keep AI-assisted writing **honest and yours** — for resumes, cover letters, portfolio pages, case studies, proposals, and bios.

They came out of a real problem: while refining a resume and portfolio *with* AI, edits crept in that quietly inflated a claim — "solo" (meant as *I did this project myself*) drifted into something like *founded and ran a research program* — alongside generic placeholder headers that weren't the author's voice at all. No one approved those changes; they just accumulated.

So `red-pen` is not about hiding that you used AI. It assumes the healthy case — you're collaborating with Claude to refine, expand, or draft your own writing — and its job is to make sure the result still **says what you meant and claims only what's true.**

## The skills

| Skill | What it does | Invoke it when you say |
|-------|--------------|------------------------|
| **ai-written-check** | Flags the *mechanical* tells that make prose read as machine-written — em dashes, triple-lists, "not X but Y" pairs, spatial/cost metaphors, "architect" as a verb, engineered cadence, register swerves, builder slang, universal claims, and generic placeholder copy. Each flag comes with a concrete rewrite. | "AI-written check", "does this sound like AI?", "make this sound like me" |
| **cringe-check** | Audits *tone and positioning* — solo-hero framing, positioning-against others, parroting the job description, prescribing a client's reality, undermining bespoke work, and overclaiming authority or flattening scale. | "cringe check", "does this sound cocky / try-hard?" |
| **full-review** | The orchestrator. Runs a six-pass review, **delegating** the AI-tells and tone passes to the two checks above and owning the rest: operator-vs-academic, honesty/anti-inflation, voice register, and fact verification. Presents a before/after diff table, lists what it deliberately kept out, and waits for your explicit sign-off before changing anything. Use it at any stage, not just the end. | "review my copy", "do a full review", "polish this for hiring managers" |

The three are independent — install one, two, or all three. `full-review` *delegates* to the other two when they're present (no duplicated rules) and falls back to brief reference notes when they aren't.

## Why "red-pen"

It's the editor's pass: a rigorous second reader that holds your writing to a standard before it goes out. The anti-inflation pass is the heart of it — it **never silently upgrades the scope of a claim.** If an edit makes something bigger than the truth (broader ownership, a larger team, an earlier origin, a founding role you didn't have), it stops and *asks* rather than polishing the inflation into a "fact."

## Design principles

Built to [Anthropic's skill-authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices):

- **Progressive disclosure** — each `SKILL.md` is a lean working checklist; the full catalogs, worked examples, and edge cases live in `references/` and load only when needed.
- **Composition, not duplication** — `full-review` invokes the two checks rather than restating them, so there's a single source of truth for each rule.
- **No scripts** — these are judgment tasks, so guidance is inline instructions, not executable code.
- **Reasoning, not bare rules** — every rule states *why* it matters and gives a fix, so the model can generalize.
- **Density over presence** — most "tells" are fine once; the skills flag the pile-up, not every instance, to avoid over-corrected, flattened prose.

## Install

Skills do **not** sync between Claude Code, Claude Desktop, and the API — install on each surface you use.

### Claude Code

**Option A — as a plugin (recommended, stays updated):**

In Claude Code, add this repo as a plugin marketplace, then install the plugin:

```
/plugin marketplace add cabbagecachekid/red-pen
/plugin install red-pen@red-pen
```

To update later: `/plugin marketplace update red-pen`.

**Option B — manual (clone and copy):**

Copy whichever skill folders you want into `~/.claude/skills/` (global) or `<project>/.claude/skills/` (project-scoped). Claude Code auto-discovers them on next launch.

```bash
git clone https://github.com/cabbagecachekid/red-pen.git
cd red-pen
cp -r skills/ai-written-check ~/.claude/skills/
cp -r skills/cringe-check     ~/.claude/skills/
cp -r skills/full-review      ~/.claude/skills/
```

Verify with `/skills` — the three should appear in the list.

### Claude Desktop / claude.ai

Each skill uploads as its own zipped folder (requires code execution; available on Pro, Max, Team, and Enterprise plans).

1. Clone the repo and zip each skill folder:
   ```bash
   git clone https://github.com/cabbagecachekid/red-pen.git
   cd red-pen/skills
   for s in ai-written-check cringe-check full-review; do zip -r "$s.zip" "$s"; done
   ```
2. In Claude Desktop, go to **Settings → Capabilities → Skills** and upload each `.zip` separately.
3. Start a chat and ask for a "cringe check" or "AI-written check" — the skill triggers automatically.

### Using the skills

Once installed, no special command is needed — just ask in plain language:

- *"Run an AI-written check on this cover letter."*
- *"Cringe check this paragraph — does it sound arrogant?"*
- *"Do a full review of my resume."*

`full-review` will pull in `ai-written-check` and `cringe-check` automatically when all three are installed, and falls back to its own reference notes if they aren't.

## Repository layout

```
.claude-plugin/      plugin.json + marketplace.json (plugin distribution)
skills/
  ai-written-check/  SKILL.md + references/TELLS.md
  cringe-check/      SKILL.md + references/POSITIONING.md
  full-review/       SKILL.md + references/PASSES.md
```

## License

MIT — see [LICENSE](LICENSE).
