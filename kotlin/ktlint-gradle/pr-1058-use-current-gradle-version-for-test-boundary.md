# ktlint-gradle PR #1058: Use current Gradle version for test boundary

Focus: Test infrastructure maintainability
Contribution Type: Maintainability improvement
Technical Area: Gradle plugin testing, compatibility matrix, Kotlin
Ecosystem: kotlin
Project: ktlint-gradle
PR: https://github.com/JLLeitschuh/ktlint-gradle/pull/1058
Issue: https://github.com/JLLeitschuh/ktlint-gradle/issues/556

## Summary

This contribution removed a hardcoded maximum supported Gradle version from the test DSL and tied it to the Gradle version currently executing the build.

## Technical Value

- Reduces maintenance drift during Gradle upgrades.
- Keeps compatibility tests aligned with the wrapper/build runtime.
- Adds a direct unit test for the version boundary contract.

## Implementation Notes

- Changed `TestVersions.maxSupportedGradleVersion` to use `GradleVersion.current().version`.
- Added coverage in `TestVersionsTest`.
- Preserved the existing compatibility DSL shape.

## Key Learnings

- Build plugin test matrices should derive runtime boundaries from the build environment when possible.
- Direct tests around version helpers prevent silent drift in compatibility infrastructure.
