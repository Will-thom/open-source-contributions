# Benchee PR #483: Prevent mixing inputs and input functions

Focus: Benchmark configuration correctness
Contribution Type: Correctness fix
Technical Area: Elixir benchmarking, input validation, developer experience
Ecosystem: elixir
Project: Benchee
PR: https://github.com/bencheeorg/benchee/pull/483
Issue: https://github.com/bencheeorg/benchee/issues/480

## Summary

This contribution tightened Benchee's benchmark configuration validation so callers cannot combine static inputs with input functions in a way that creates ambiguous benchmark setup semantics.

## Technical Value

- Prevents invalid benchmark definitions from reaching execution.
- Makes configuration errors easier to diagnose before measurements start.
- Preserves a clearer contract between benchmark inputs and generated inputs.

## Implementation Notes

- Added validation for mutually exclusive input configuration paths.
- Covered the behavior with focused tests around benchmark suite construction.
- Kept the fix local to configuration validation rather than changing benchmark execution.

## Key Learnings

- Benchmark tools need strict setup contracts because ambiguous inputs can invalidate measurements.
- Failing early in configuration gives users a better debugging path than surfacing errors during timed execution.
