# Copilot SDK PR #1344: Normalize optional MCP stdio args

Focus: SDK contract consistency
Contribution Type: Technical exploration
Technical Area: TypeScript, Python, Go SDK contracts and MCP stdio configuration
Ecosystem: typescript
Project: Copilot SDK
PR: https://github.com/github/copilot-sdk/pull/1344
Issue: https://github.com/github/copilot-sdk/issues/1231

## Summary

This technical exploration normalized optional MCP stdio args across SDK surfaces so omitted args were represented consistently instead of drifting between undefined, nil, null, and empty arrays.

## Technical Value

- Improves cross-language API consistency for an SDK contract.
- Highlights edge cases in serialization across TypeScript, Python, and Go clients.
- Preserves a useful record of validation across multiple language test suites.

## Implementation Notes

- Made Node MCPStdioServerConfig args optional in the public type.
- Normalized omitted stdio MCP args to empty arrays in Node and Python payload paths.
- Serialized nil Go MCP stdio args as empty arrays instead of null.
- Ran focused tests and checks across Node, Python, Go, formatting, and diff validation.

## Key Learnings

- Multi-language SDKs need consistent wire behavior even when each language models optional values differently.
- Targeted type-contract changes can have broad validation cost across generated payloads and client implementations.
