# TypeGPU PR #2549: Add linear indexing builtins

Focus: WGSL builtin API coverage
Contribution Type: Feature addition
Technical Area: WebGPU, WGSL extensions, TypeScript types
Ecosystem: typescript
Project: TypeGPU
PR: https://github.com/software-mansion/TypeGPU/pull/2549
Issue: https://github.com/software-mansion/TypeGPU/issues/2277

## Summary

This contribution added TypeGPU support for WGSL linear_indexing builtins, exposing globalInvocationIndex and workgroupIndex through the typed shader API.

## Technical Value

- Expands TypeGPU coverage for compute-shader builtins.
- Preserves type-level access through the public builtin catalog and compute entrypoints.
- Ensures generated WGSL includes the required extension enable directive.

## Implementation Notes

- Added d.builtin.globalInvocationIndex and d.builtin.workgroupIndex.
- Registered both builtin names and extended computeFn accepted builtins.
- Added linear_indexing extension handling and shader snapshot tests.

## Key Learnings

- WGSL builtins can be extension-gated, so API exposure and generated source must evolve together.
- Shader snapshot tests are effective for checking the exact WGSL emitted by a TypeScript DSL.
