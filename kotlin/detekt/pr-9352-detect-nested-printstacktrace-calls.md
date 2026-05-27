# detekt PR #9352: Detect nested printStackTrace calls

Focus: Static analysis correctness
Contribution Type: Regression fix
Technical Area: Kotlin AST traversal, lint rules, static analysis
Ecosystem: kotlin
Project: detekt
PR: https://github.com/detekt/detekt/pull/9352
Issue: https://github.com/detekt/detekt/issues/9345

## Summary

This contribution fixed a false negative in detekt's `PrintStackTrace` rule when `printStackTrace()` appeared inside nested call expressions.

## Technical Value

- Restores detection coverage for idiomatic nested Kotlin code.
- Prevents a rule implementation detail from skipping parts of the AST.
- Adds regression coverage for a minimal nested-call scenario.

## Implementation Notes

- Ensured overridden visitor methods continue recursive traversal.
- Added a focused `PrintStackTraceSpec` regression case.
- Kept the rule logic targeted to traversal correctness.

## Key Learnings

- Visitor-based lint rules must preserve recursive traversal when overriding visit methods.
- A missing `super.visit...` call can create silent false negatives that focused snippet tests can catch cheaply.
