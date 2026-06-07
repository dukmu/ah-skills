# opencode Adapter

Recommended placement:
- `.opencode/skills/code-slimming-skill/`
- Or `docs/skills/code-slimming-skill/`

Reference instruction:

```md
Use the code slimming skill located at:
docs/skills/code-slimming-skill/SKILL.md

When this task involves removing dead code, reducing complexity, simplifying modules, or removing dependencies:
1. Start in audit mode.
2. Use dependency-analysis-agent before deleting anything.
3. Use safety-review-agent before edits.
4. Use validation-agent after every patch group.
5. Apply only L1/L2 unless explicitly authorized.
```

Prompt example:

```text
Use docs/skills/code-slimming-skill/SKILL.md.

Mode: audit.
Target: app/ and lib/.
Find:
- dead code
- duplicate helpers
- removable dependencies
- over-abstraction
- risky dynamic references

Do not modify files yet.
```

Apply prompt:

```text
Use docs/skills/code-slimming-skill/SKILL.md.

Mode: apply.
Scope: app/
Max risk: L2.
Validation: run project tests/build if available.
Stop immediately on failure.
```
