# Claude Code Adapter

Recommended placement:
- Put this skill directory under `.claude/skills/code-slimming-skill/`
- Or keep it in `docs/skills/code-slimming-skill/` and reference it from `CLAUDE.md`.

Add to `CLAUDE.md`:

```md
## Code Slimming Skill

When asked to slim, reduce, simplify, de-bloat, remove dead code, or reduce dependencies, use:

`docs/skills/code-slimming-skill/SKILL.md`

Default mode:
- audit first
- apply only L1/L2
- preserve behavior
- run validation after every patch group

Required sub-agents:
- dependency-analysis-agent
- validation-agent
- safety-review-agent
- slimming-agent
```

Prompt example:

```text
Use the code-slimming skill.

Mode: audit first.
Target: src/
Do not modify public APIs, CLI flags, config keys, schemas, migrations, generated code, or tests.
Find dead code, duplicated helpers, unnecessary abstractions, and removable dependencies.
Return a risk-classified plan.
```

Apply example:

```text
Use the code-slimming skill in apply mode.
Apply only L1 and L2 changes.
Run tests after each patch group.
Stop on failure.
Produce a final slimming report.
```
