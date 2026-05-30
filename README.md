# copy-review-skills

Three composable [Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) for reviewing human-facing professional copy — resumes, cover letters, portfolio pages, case studies, proposals, and bios.

They started as a recurring habit ("do a cringe check and an AI-written check on this") and were turned into reusable skills so the review is consistent every time instead of re-derived from scratch.

## The skills

| Skill | What it does | Invoke it when you say |
|-------|--------------|------------------------|
| **ai-written-check** | Flags the *mechanical* tells that make prose read as machine-written — em dashes, triple-lists, "not X but Y" pairs, spatial/cost metaphors, "architect" as a verb, engineered cadence, register swerves, builder slang, universal claims. Each flag comes with a concrete rewrite. | "AI-written check", "does this sound like AI?", "make this less generated" |
| **cringe-check** | Audits *tone and positioning* — solo-hero framing, positioning-against others, parroting the job description, prescribing a client's reality, undermining bespoke work, and overclaiming authority or flattening scale. | "cringe check", "does this sound cocky / try-hard?" |
| **copy-review** | The orchestrator. Runs a six-pass review (AI tells, operator-vs-academic, honesty/overclaim, tone, voice register, fact verification), then presents a before/after diff table, lists what was deliberately kept out, and waits for explicit sign-off before changing anything. Composes the other two skills. | "review my copy", "do a full review", "polish this for hiring managers" |

The three are independent — install one, two, or all three. `copy-review` uses the other two when present and degrades gracefully to its own reference notes when they aren't.

## Design principles

Built to [Anthropic's skill-authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices):

- **Progressive disclosure** — each `SKILL.md` is a lean working checklist; the full catalogs, worked examples, and edge cases live in `references/` and load only when needed.
- **No scripts** — these are judgment tasks, so guidance is inline instructions, not executable code.
- **Reasoning, not bare rules** — every rule states *why* it matters and gives a fix, so the model can generalize.
- **Density over presence** — most "tells" are fine once; the skills flag the pile-up, not every instance, to avoid over-corrected, flattened prose.

## Install

Skills do **not** sync between Claude Code, Claude Desktop, and the API — install on each surface you use.

### Claude Code

**Option A — as a plugin (recommended, stays updated):**

In Claude Code, add this repo as a plugin marketplace, then install the plugin:

```
/plugin marketplace add cabbagecachekid/copy-review-skills
/plugin install copy-review-skills@copy-review-skills
```

To update later: `/plugin marketplace update copy-review-skills`.

**Option B — manual (clone and copy):**

Copy whichever skill folders you want into `~/.claude/skills/` (global) or `<project>/.claude/skills/` (project-scoped). Claude Code auto-discovers them on next launch.

```bash
git clone https://github.com/cabbagecachekid/copy-review-skills.git
cd copy-review-skills
cp -r skills/ai-written-check ~/.claude/skills/
cp -r skills/cringe-check     ~/.claude/skills/
cp -r skills/copy-review      ~/.claude/skills/
```

Verify with `/skills` — the three should appear in the list.

### Claude Desktop / claude.ai

Each skill uploads as its own zipped folder (requires code execution; available on Pro, Max, Team, and Enterprise plans).

1. Clone the repo and zip each skill folder:
   ```bash
   git clone https://github.com/cabbagecachekid/copy-review-skills.git
   cd copy-review-skills/skills
   for s in ai-written-check cringe-check copy-review; do zip -r "$s.zip" "$s"; done
   ```
2. In Claude Desktop, go to **Settings → Capabilities → Skills** and upload each `.zip` separately.
3. Start a chat and ask for a "cringe check" or "AI-written check" — the skill triggers automatically.

### Using the skills

Once installed, no special command is needed — just ask in plain language:

- *"Run an AI-written check on this cover letter."*
- *"Cringe check this paragraph — does it sound arrogant?"*
- *"Do a full copy review of my resume."*

`copy-review` will pull in `ai-written-check` and `cringe-check` automatically when all three are installed, and falls back to its own reference notes if they aren't.

## Repository layout

```
.claude-plugin/      plugin.json + marketplace.json (plugin distribution)
skills/
  ai-written-check/  SKILL.md + references/TELLS.md
  cringe-check/      SKILL.md + references/POSITIONING.md
  copy-review/       SKILL.md + references/PASSES.md
```

## License

MIT — see [LICENSE](LICENSE).
