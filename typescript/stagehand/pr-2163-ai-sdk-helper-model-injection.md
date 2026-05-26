# Stagehand PR #2163: Inject configured models into AI SDK helpers

Focus: AI SDK developer experience
Contribution Type: Developer experience improvement
Technical Area: TypeScript, AI SDK wrappers, client configuration
Ecosystem: typescript
Project: Stagehand
PR: https://github.com/browserbase/stagehand/pull/2163
Issue: https://github.com/browserbase/stagehand/issues/666

## Summary

This contribution made Stagehand AI SDK helpers use the client configured model by default, while still allowing explicit model overrides for advanced callers.

## Technical Value

- Reduces repetitive model plumbing in common Stagehand workflows.
- Preserves escape hatches for callers that need a different model per request.
- Improves API ergonomics without wrapping unrelated multimodal helpers.

## Implementation Notes

- Wrapped generateText, generateObject, streamText, and streamObject to inject getLanguageModel() when model is omitted.
- Preserved explicit model overrides.
- Added unit coverage for injection, override behavior, and legacy-client errors.

## Key Learnings

- DX wrappers should optimize the common path while keeping advanced options intact.
- Making one property optional over inferred external types avoids duplicating complex SDK signatures.
