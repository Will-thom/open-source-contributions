# Indicator PR #380: Add Rate of Change Slope indicator

Focus: Technical analysis indicator coverage
Contribution Type: Feature addition
Technical Area: Go generics, channel pipelines, financial indicators
Ecosystem: go
Project: Indicator
PR: https://github.com/cinar/indicator/pull/380
Issue: https://github.com/cinar/indicator/issues/363

## Summary

This contribution implemented the Rate of Change Slope indicator in the trend package, following the library existing Compute, IdlePeriod, and String conventions.

## Technical Value

- Adds an isolated technical-analysis primitive with low architectural risk.
- Keeps indicator behavior consistent with existing channel-based patterns.
- Provides tests for calculation, defaults, idle period, and string output.

## Implementation Notes

- Added trend.Slope with a default period of 14 and fallback for invalid periods.
- Used helper.NewRing to access historical values during streaming computation.
- Aligned public output through IdlePeriod and helper.Skip behavior.

## Key Learnings

- Windowed channel indicators often emit warm-up values internally and align public output afterward.
- Choosing isolated package work can maximize contribution ROI by avoiding dependency-cycle risk.
