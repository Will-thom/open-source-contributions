# Renovate PR #43613: Add documentation links to config schema

Focus: Configuration developer experience
Contribution Type: Developer experience improvement
Technical Area: JSON Schema generation, configuration docs, TypeScript
Ecosystem: typescript
Project: Renovate
PR: https://github.com/renovatebot/renovate/pull/43613
Issue: https://github.com/renovatebot/renovate/issues/41815

## Summary

This contribution added documentation links to Renovate's generated configuration JSON Schema so editor users can navigate from schema help to the relevant public docs.

## Technical Value

- Brings documentation closer to configuration authoring workflows.
- Preserves plain-text descriptions while adding clickable Markdown descriptions.
- Distinguishes repository configuration docs from self-hosted/global configuration docs.

## Implementation Notes

- Updated the schema generator in `tools/docs/schema.ts`.
- Generated links for repository options and `globalOnly` options using the correct documentation base.
- Preserved the existing anchor convention used by Renovate documentation.

## Key Learnings

- Generated schemas should be improved at the generator layer rather than by editing artifacts.
- Documentation links in editor-facing schema metadata are part of configuration developer experience.
