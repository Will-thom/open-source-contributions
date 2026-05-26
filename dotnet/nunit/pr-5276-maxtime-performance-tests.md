# NUnit PR #5276: Replace manual timing helper with MaxTime

Focus: Test maintainability
Contribution Type: Developer experience improvement
Technical Area: .NET testing, performance checks
Ecosystem: dotnet
Project: NUnit
PR: https://github.com/nunit/nunit/pull/5276
Issue: https://github.com/nunit/nunit/issues/5271

## Summary

This contribution simplified NUnit collection-equivalence performance tests by replacing custom Stopwatch logic with NUnit own declarative MaxTime attribute.

## Technical Value

- Reduces custom test infrastructure in favor of framework-native behavior.
- Preserves warning and failure thresholds while making test intent clearer.
- Improves maintainability of performance-sensitive tests.

## Implementation Notes

- Replaced the Stopwatch helper with MaxTime and WarningTime.
- Kept the tests focused on executing the constraint and asserting results.
- Applied the style adjustment required by the Release build.

## Key Learnings

- Framework-provided test attributes often communicate intent better than local timing helpers.
- Multi-target .NET OSS projects can expose style and SDK requirements only under specific build configurations.
