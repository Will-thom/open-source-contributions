# TypeGPU PR #2548: Streamline the CLI prompt flow

Focus: CLI onboarding flow
Contribution Type: Developer experience improvement
Technical Area: TypeScript CLI, prompts, project scaffolding
Ecosystem: typescript
Project: TypeGPU
PR: https://github.com/software-mansion/TypeGPU/pull/2548
Issue: https://github.com/software-mansion/TypeGPU/issues/2543

## Summary

This contribution reduced the number of prompts in the TypeGPU CLI setup flow, making project initialization more direct while preserving the initial setup intent.

## Technical Value

- Improves developer onboarding for a WebGPU TypeScript toolkit.
- Reduces friction in project scaffolding without adding configuration complexity.
- Keeps the CLI flow aligned with the user first-run path.

## Implementation Notes

- Replaced separate prompts with a more consolidated prompt flow.
- Updated the CLI behavior while keeping the generated setup consistent.
- Added regression coverage for the new prompt path.

## Key Learnings

- Scaffolding CLIs should minimize decisions that do not change meaningful output.
- Prompt design is part of developer experience, especially in first-contact workflows.
