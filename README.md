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

### Claude Code
Filesystem-based, auto-discovered. Either:

- **As a plugin:** add this repo as a plugin marketplace and install the `copy-review-skills` plugin, **or**
- **Manually:** copy any skill folder into `~/.claude/skills/` (global) or `<project>/.claude/skills/` (project-scoped):
  ```bash
  cp -r skills/ai-written-check ~/.claude/skills/
  cp -r skills/cringe-check     ~/.claude/skills/
  cp -r skills/copy-review      ~/.claude/skills/
  ```

### Claude Desktop / claude.ai
Each skill uploads as its own folder. Zip the folder you want and upload it under **Settings → Capabilities → Skills** (requires code execution; available on Pro, Max, Team, and Enterprise plans):

```bash
cd skills && zip -r ai-written-check.zip ai-written-check
```

Upload each `.zip` separately. Skills do not sync between Claude Code, Desktop, and the API — install on each surface you use.

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
