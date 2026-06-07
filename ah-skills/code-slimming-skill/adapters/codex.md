# Codex Adapter

Recommended placement:
- `docs/skills/code-slimming-skill/`
- Reference from `AGENTS.md` if the repo uses one.

Add to `AGENTS.md`:

```md
## Code Slimming

For code slimming tasks, follow:

`docs/skills/code-slimming-skill/SKILL.md`

Rules:
- preserve observable behavior
- audit before apply
- only apply L1/L2 by default
- do not delete tests
- do not edit schemas/migrations/generated code
- treat dynamic references as high risk
- run validation after each patch group
```

Prompt example:

```text
Follow docs/skills/code-slimming-skill/SKILL.md.

Task:
Audit this repo for code slimming opportunities.

Output:
- code map
- dependency analysis
- L1/L2/L3/L4 candidates
- validation plan
- safe apply sequence
```

Apply prompt:

```text
Follow docs/skills/code-slimming-skill/SKILL.md.

Apply only L1 and L2 changes.
Patch in small groups.
Run available validation after each group.
Stop on failure.
```
