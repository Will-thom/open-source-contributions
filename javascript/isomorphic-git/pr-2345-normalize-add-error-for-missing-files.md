# isomorphic-git PR #2345: Normalize add error for missing files

Focus: Filesystem error handling
Contribution Type: Correctness fix
Technical Area: Git porcelain behavior, filesystem abstraction, JavaScript
Ecosystem: javascript
Project: isomorphic-git
PR: https://github.com/isomorphic-git/isomorphic-git/pull/2345
Issue: https://github.com/isomorphic-git/isomorphic-git/issues/2216

## Summary

This contribution improved the behavior of `git.add` when the target file is missing, aligning the surfaced error with the expected filesystem failure instead of allowing a less useful downstream failure.

## Technical Value

- Improves diagnostics for a common porcelain command.
- Keeps behavior aligned across filesystem adapters.
- Adds regression coverage for a user-facing command path.

## Implementation Notes

- Adjusted the missing-file path in the add flow.
- Added tests that exercise the command through the public API.
- Preserved existing behavior for valid tracked and untracked files.

## Key Learnings

- Git-compatible libraries need useful errors at the porcelain boundary, not only deep adapter failures.
- Public API tests are valuable when the behavior depends on filesystem abstraction details.
