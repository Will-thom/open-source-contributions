# Verno Studio Website PR #21: Remove direct execa usage from the CLI package

Focus: Dependency surface reduction
Contribution Type: Maintainability improvement
Technical Area: Bun, Node.js child processes, CLI tooling
Ecosystem: typescript
Project: Verno Studio Website
PR: https://github.com/verno-studio/website/pull/21
Issue: https://github.com/verno-studio/website/issues/20

## Summary

This contribution removed a direct process-execution dependency from the Verno Studio CLI and replaced it with native runtime capabilities.

## Technical Value

- Reduces dependency surface in a project scaffolding CLI.
- Keeps process execution behavior explicit and easier to maintain.
- Improves portability in a Bun-based TypeScript monorepo.

## Implementation Notes

- Replaced execa usage in the CLI with native process execution.
- Kept the package behavior aligned with the existing setup flow.
- Updated the implementation without expanding the public CLI surface.

## Key Learnings

- CLI setup tools benefit from keeping process execution dependencies minimal.
- Runtime-native APIs can be a better fit when the project already standardizes on that runtime.
