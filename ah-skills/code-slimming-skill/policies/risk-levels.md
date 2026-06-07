# Risk Levels

## L1: Safe Cleanup

Usually safe to apply automatically.

Examples:
- unused imports
- unused local variables
- unreachable branch proven by constant condition
- dead private helper with no references and no dynamic risk
- duplicate comments
- stale debug print guarded by impossible condition
- formatting-free deletion

Validation:
- syntax check
- tests if available

## L2: Local Refactor

Can apply by default after safety review.

Examples:
- merge duplicate private helpers
- inline single-use wrapper
- simplify local branch
- remove private class used only as unnecessary container
- remove dependency proven unused

Validation:
- tests
- typecheck/build
- smoke tests for affected entrypoints

## L3: Structural Refactor

Proposal only by default.

Examples:
- collapse module boundaries
- merge packages
- remove adapter layer
- redesign config flow
- replace framework integration
- large rename
- change internal architecture

Validation:
- full test suite
- integration tests
- API/CLI/schema checks
- manual approval

## L4: Behavior/API Change

Blocked unless explicitly authorized.

Examples:
- remove public API
- remove CLI flag
- change output format
- change error code
- remove config option
- change default behavior
- remove compatibility path
- change schema/protocol

Validation:
- migration plan
- release note
- compatibility test
- explicit user approval
