# TypeGPU PR #2566: Add flat interpolation for integer varyings

Focus: WGSL interface correctness
Contribution Type: Compatibility fix
Technical Area: WebGPU, WGSL interpolation, TypeScript shader generation
Ecosystem: typescript
Project: TypeGPU
PR: https://github.com/software-mansion/TypeGPU/pull/2566
Issue: https://github.com/software-mansion/TypeGPU/issues/2147

## Summary

This contribution added automatic `@interpolate(flat)` generation for integer varyings passed between vertex and fragment shader stages.

## Technical Value

- Produces WGSL that satisfies integer varying interpolation rules.
- Preserves explicit interpolation attributes when users provide them.
- Keeps the rule scoped to vertex outputs and fragment inputs where interpolation is valid.

## Implementation Notes

- Added an IO generation option for integer varying interpolation.
- Updated render pipeline snapshots and explicit vertex/fragment tests.
- Avoided changing vertex inputs and fragment outputs where interpolation attributes do not apply.

## Key Learnings

- WGSL generation needs semantic awareness of shader stage boundaries, not only data types.
- Generated shader snapshots document subtle interface contracts and catch regressions in emitted attributes.
