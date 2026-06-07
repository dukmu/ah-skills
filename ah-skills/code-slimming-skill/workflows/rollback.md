# Rollback Workflow

Use when:
- validation fails
- user asks to revert
- patch causes behavior change

Steps:
1. Identify last patch group.
2. Revert only the failing patch group.
3. Re-run validation.
4. If validation passes, stop.
5. If validation still fails, inspect previous patch group.
6. Report rollback result.

Rules:
- Do not continue slimming during rollback.
- Do not introduce new refactors as fixes.
- Prefer exact revert.
- If exact revert is unavailable, perform minimal restoration.

Output:

```md
# Rollback Report

## Reverted Patch Group
- ...

## Reason
- ...

## Validation After Rollback
- ...

## Remaining Issues
- ...
```
