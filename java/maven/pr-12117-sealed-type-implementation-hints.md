# Maven PR #12117: Harden sealed type implementation hint resolution

Focus: Dependency injection type resolution
Contribution Type: Robustness improvement
Technical Area: Sealed classes, configuration conversion, tests
Ecosystem: java
Project: Apache Maven
PR: https://github.com/apache/maven/pull/12117
Issue: N/A

## Summary

This contribution improved Maven configuration conversion for sealed types by making ambiguous implementation-hint resolution more diagnosable and less fragile.

## Technical Value

- Improves error quality for sealed type resolution.
- Preserves original exception causes for maintainability.
- Reduces test fragility around generated configuration error messages.

## Implementation Notes

- Preserved the cause when reporting ambiguity between sealed subclasses.
- Sorted matches only after handling the empty-list case.
- Added an ambiguous sealed fixture and relaxed assertions to focus on relevant diagnostics.

## Key Learnings

- Name-based resolution over sealed subclasses must treat ambiguity as a first-class error.
- Tests that assert wrapped error messages should avoid overfitting to the full text when context may be added upstream.
