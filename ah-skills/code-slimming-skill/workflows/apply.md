# Apply Workflow

Use when:
- user explicitly wants changes
- allowed risk is clear
- validation commands are available or smoke tests can be created

Steps:
1. Confirm scope from user message.
2. Load config.
3. Run baseline validation.
4. If baseline fails:
   - stop apply mode
   - produce audit report
5. Generate candidate patch groups.
6. Safety-review patch group.
7. Apply only approved L1/L2 by default.
8. Validate.
9. Continue only if validation passes.
10. Produce final report.

Patch sequence:
```text
L1 unused imports
L1 trivial dead code
L1 comments/debug cleanup
L2 private unused code
L2 duplicate helper consolidation
L2 local branch simplification
L2 dependency removal if strongly proven
L3 proposals only
```

Stop conditions:
- validation failure
- public API diff
- schema diff
- CLI output diff
- dynamic reference uncertainty
- user constraint conflict

Final output:

```md
# Code Slimming Apply Report

## Baseline
...

## Applied Patch Groups
...

## Verification
...

## Metrics
...

## Blocked / Deferred
...

## Remaining Risk
...
```
