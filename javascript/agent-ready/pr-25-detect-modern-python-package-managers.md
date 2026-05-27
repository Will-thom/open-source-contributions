# agent-ready PR #25: Detect modern Python package managers

Focus: Python tooling detection
Contribution Type: Developer experience improvement
Technical Area: Repository scanning, Python package managers, JavaScript CLI
Ecosystem: javascript
Project: agent-ready
PR: https://github.com/EShener/agent-ready/pull/25
Issue: https://github.com/EShener/agent-ready/issues/21

## Summary

This contribution added detection for Poetry, PDM, and uv so Python repositories are reported with package-manager-specific install and test commands instead of generic pip assumptions.

## Technical Value

- Improves command suggestions for modern Python projects.
- Uses lockfiles and `pyproject.toml` tool sections as deterministic signals.
- Keeps detection local-first and independent of running external Python tools.

## Implementation Notes

- Added detection for `poetry.lock`, `pdm.lock`, `uv.lock`, and related `pyproject.toml` sections.
- Generated commands such as `poetry install`, `pdm install`, `uv sync`, and corresponding test invocations.
- Added fixtures and documentation for the new coverage.

## Key Learnings

- `pyproject.toml` alone is not enough to infer Python workflow semantics.
- Lockfiles are strong package-manager signals and make scanner behavior stable without executing the package manager.
