# pandas PR #65709: Keep GroupBy apply return shape consistent

Focus: GroupBy result-shape correctness
Contribution Type: Regression fix
Technical Area: Python dataframes, groupby apply, test coverage
Ecosystem: python
Project: pandas
PR: https://github.com/pandas-dev/pandas/pull/65709
Issue: https://github.com/pandas-dev/pandas/issues/54992

## Summary

This contribution fixed an inconsistency where DataFrameGroupBy.apply could return a Series for multiple groups but a DataFrame for a single group when the applied function returned a Series indexed like the input.

## Technical Value

- Improves correctness for grouped dataframe workflows that depend on stable output shape.
- Protects transform-like apply behavior without breaking reductions indexed by columns.
- Adds regression coverage in a high-traffic pandas API area.

## Implementation Notes

- Adjusted result wrapping in pandas/core/groupby/generic.py to use concatenation for the single-group indexed-like-input case.
- Added an extra guard to avoid treating column-indexed reductions as transform-like results.
- Added a regression test and release note coverage.

## Key Learnings

- Single-group GroupBy.apply cases are ambiguous because there are no multiple group indexes to compare.
- Shape decisions in dataframe libraries need broad regression suites because local fixes can affect many apply modes.
