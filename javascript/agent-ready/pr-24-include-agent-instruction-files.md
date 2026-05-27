# agent-ready PR #24: Include agent instruction files

Focus: Repository readiness scoring
Contribution Type: Developer experience improvement
Technical Area: Repository scanning, agent instructions, JavaScript CLI
Ecosystem: javascript
Project: agent-ready
PR: https://github.com/EShener/agent-ready/pull/24
Issue: https://github.com/EShener/agent-ready/issues/23

## Summary

This contribution improved repository readiness analysis by recognizing instruction files used by coding agents and reflecting them in generated readiness output.

## Technical Value

- Expands repository scanning beyond conventional project files.
- Helps teams identify whether agent-specific guidance is present.
- Makes readiness reports more useful for AI-assisted development workflows.

## Implementation Notes

- Added detection for agent instruction files.
- Updated fixtures and output expectations for the scanner.
- Documented the new signal in the detector coverage.

## Key Learnings

- Agent-readiness tooling needs to treat instructions as first-class project metadata.
- Fixture-driven scanners benefit from focused representative repositories that lock down detection behavior.
