# Audit Workflow

Use when:
- user asks for analysis
- repo is unfamiliar
- tests are absent
- broad cleanup is requested
- baseline is failing

Steps:
1. Read user constraints.
2. Detect language and project layout.
3. Identify protected surfaces.
4. Identify entrypoints.
5. Run dependency analysis.
6. Find slimming candidates.
7. Classify by risk.
8. Produce report.
9. Do not modify files.

Output:

```md
# Code Slimming Audit

## Scope
- target:
- excluded:
- allowed risk:

## Code Map
- entrypoints:
- core modules:
- boundary modules:
- protected files:

## Candidates

### L1 Safe Cleanup
- ...

### L2 Local Refactor
- ...

### L3 Structural Proposal
- ...

### L4 Behavior/API Change
- ...

## Dependency Findings
- ...

## Validation Plan
- ...

## Recommended Apply Sequence
1. ...
2. ...
3. ...

## Risks
- ...
```
