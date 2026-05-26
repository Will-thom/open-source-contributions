# Maven PR #12016: Update dependency diagram for JLine migration

Focus: Architecture documentation
Contribution Type: Technical exploration
Technical Area: Java build tooling, architecture documentation, dependency diagrams
Ecosystem: java
Project: Apache Maven
PR: https://github.com/apache/maven/pull/12016
Issue: https://github.com/apache/maven/pull/11874

## Summary

This technical exploration updated Maven architecture documentation to reflect the move from JAnsi to JLine in the CLI and console layer.

## Technical Value

- Improves architecture documentation around Maven console dependencies.
- Shows contribution work beyond code by keeping diagrams aligned with dependency changes.
- Keeps the exploration traceable to the official Maven PR discussion.

## Implementation Notes

- Replaced the JAnsi node with JLine in the CLI and console layer.
- Updated the dependency representation accordingly.
- Regenerated the SVG diagram from the updated source document.

## Key Learnings

- Architecture diagrams become stale unless dependency shifts are reflected in both source and rendered artifacts.
- Documentation artifacts can require tool-specific regeneration and review even without runtime code changes.
