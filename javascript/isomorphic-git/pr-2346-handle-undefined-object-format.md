# isomorphic-git PR #2346: Handle undefined object format

Focus: Object writer compatibility
Contribution Type: Compatibility fix
Technical Area: Git object storage, JavaScript, repository metadata
Ecosystem: javascript
Project: isomorphic-git
PR: https://github.com/isomorphic-git/isomorphic-git/pull/2346
Issue: https://github.com/isomorphic-git/isomorphic-git/issues/800

## Summary

This contribution made object writing resilient when repository format metadata does not define an object format explicitly.

## Technical Value

- Improves compatibility with repositories using default object format assumptions.
- Avoids unnecessary failures when metadata is incomplete but still valid.
- Protects a low-level storage path used by multiple commands.

## Implementation Notes

- Added a fallback for undefined object format handling.
- Covered the behavior with a focused regression test.
- Kept the change constrained to object format resolution.

## Key Learnings

- Git metadata often relies on defaults, so storage code must distinguish absent configuration from unsupported configuration.
- Small compatibility fixes in object writing can have broad effects across higher-level commands.
