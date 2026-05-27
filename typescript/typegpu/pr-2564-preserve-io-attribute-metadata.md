# TypeGPU PR #2564: Preserve IO attribute metadata

Focus: IO metadata consistency
Contribution Type: Correctness fix
Technical Area: WebGPU, WGSL IO generation, TypeScript schemas
Ecosystem: typescript
Project: TypeGPU
PR: https://github.com/software-mansion/TypeGPU/pull/2564
Issue: https://github.com/software-mansion/TypeGPU/issues/2543

## Summary

This contribution improved TypeGPU IO generation by preserving attribute metadata through schema transformations used for shader entrypoints.

## Technical Value

- Keeps user-provided IO attributes visible to WGSL generation.
- Protects shader interface correctness across schema-derived types.
- Adds coverage for metadata preservation in generated shader output.

## Implementation Notes

- Adjusted IO metadata handling during schema processing.
- Added snapshot coverage for generated WGSL.
- Preserved explicit attributes rather than replacing them with inferred defaults.

## Key Learnings

- Shader schema systems must preserve both type information and semantic attribute metadata.
- Snapshot tests are useful when the technical contract is the exact WGSL emitted from a typed API.
