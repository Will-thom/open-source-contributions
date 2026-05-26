# mloda-registry PR #201: Document the extra parameter hook

Focus: Developer documentation clarity
Contribution Type: Documentation improvement
Technical Area: Python feature hooks, framework integration
Ecosystem: python
Project: mloda-registry
PR: https://github.com/mloda-ai/mloda-registry/pull/201
Issue: https://github.com/mloda-ai/mloda-registry/issues/184

## Summary

This contribution documented the _extra_parameter hook so users can understand how to pass framework-specific behavior through the feature system.

## Technical Value

- Improves onboarding for extension points that were already present but underexplained.
- Makes advanced feature integration easier to discover.
- Reduces reliance on source-code reading for framework-specific customization.

## Implementation Notes

- Added a focused documentation section for the hook.
- Connected the explanation to end-to-end feature usage.
- Kept the change documentation-only and aligned with existing guide structure.

## Key Learnings

- Public hooks need narrative documentation, not only code references.
- Documenting extension points can unlock existing functionality without changing runtime behavior.
