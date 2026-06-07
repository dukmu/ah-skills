# Code Slimming Skill

Purpose:
Reduce code size, complexity, dependency surface, and maintenance burden while preserving observable behavior.

This skill supports:
- audit-only mode
- apply mode
- dependency analysis
- dead code detection
- duplicate logic consolidation
- abstraction collapse proposals
- validation before and after changes
- safety review for public APIs, schemas, CLI, config, migrations, dynamic entrypoints

Default behavior:
- Conservative.
- No public behavior changes unless explicitly authorized.
- No deletion of tests.
- No deletion of schemas, migrations, generated code, or public API surfaces.
- Dynamic references are high-risk by default.

Recommended audit prompt:

```text
Use code-slimming-skill in audit mode on this repository.
Target: src/
Do not modify public APIs, CLI behavior, config schema, database schema, or tests.
Validation commands:
- pytest
- npm test
- cargo test
- go test ./...
Use whatever applies to this repo.
```

Recommended apply prompt:

```text
Use code-slimming-skill in apply mode.
Only apply L1 and L2 changes.
Run validation after each patch group.
Stop if validation fails.
Produce a final slimming report.
```
