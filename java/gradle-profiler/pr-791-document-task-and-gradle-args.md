# Gradle Profiler PR #791: Document task and Gradle args

Focus: Build tooling documentation
Contribution Type: Documentation improvement
Technical Area: Gradle profiling, scenario configuration, JVM build tooling
Ecosystem: java
Project: Gradle Profiler
PR: https://github.com/gradle/gradle-profiler/pull/791
Issue: https://github.com/gradle/gradle-profiler/issues/381

## Summary

This contribution clarified how to pass task-specific arguments and global Gradle arguments in Gradle Profiler scenario files.

## Technical Value

- Prevents users from accidentally passing a task and its arguments as one task name.
- Clarifies the boundary between `tasks` and `gradle-args`.
- Improves configuration examples for repeatable profiling scenarios.

## Implementation Notes

- Added README examples for task arguments as separate array items.
- Added a separate example for global Gradle arguments such as `--continue`.
- Kept the change documentation-focused and aligned with maintainer guidance.

## Key Learnings

- Profiling configuration is part of the measurement contract because parsing differences change what is benchmarked.
- Clear examples reduce setup ambiguity in tools where command-line semantics are encoded in configuration files.
