# mloda-registry PR #200: Add diff_N and pct_change_N offset features

Focus: Feature engineering correctness
Contribution Type: Feature addition
Technical Area: Python data features, grouped offsets
Ecosystem: python
Project: mloda-registry
PR: https://github.com/mloda-ai/mloda-registry/pull/200
Issue: https://github.com/mloda-ai/mloda-registry/issues/197

## Summary

This contribution implemented offset-derived feature variants so grouped time-based feature engineering can express differences and percentage changes directly.

## Technical Value

- Expands reusable feature engineering primitives.
- Improves expressiveness for grouped and time-aware datasets.
- Keeps behavior consistent with existing offset feature patterns.

## Implementation Notes

- Implemented diff_N and pct_change_N feature behavior.
- Integrated the new variants into the registry feature flow.
- Added tests covering grouped offset semantics.

## Key Learnings

- Feature registries need consistent naming and partition semantics across related operations.
- Small feature additions are strongest when they follow the existing registry contract closely.
