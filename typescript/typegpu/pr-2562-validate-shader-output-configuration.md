# TypeGPU PR #2562: Validate shader output configuration

Focus: Shader API correctness
Contribution Type: Correctness fix
Technical Area: WebGPU, WGSL generation, TypeScript validation
Ecosystem: typescript
Project: TypeGPU
PR: https://github.com/software-mansion/TypeGPU/pull/2562
Issue: https://github.com/software-mansion/TypeGPU/issues/2542

## Summary

This contribution tightened TypeGPU validation around shader output configuration so invalid IO definitions fail earlier and more predictably.

## Technical Value

- Prevents invalid shader metadata from reaching generated WGSL.
- Improves diagnostics for users building typed pipeline definitions.
- Keeps validation close to the API boundary that receives IO configuration.

## Implementation Notes

- Added validation for the affected shader output configuration path.
- Covered the behavior with focused tests and generated output checks.
- Preserved valid explicit shader IO definitions.

## Key Learnings

- Typed shader APIs still need runtime validation for metadata that influences generated code.
- Failing before WGSL generation gives users clearer feedback than relying on GPU validation errors.
