# Hosomaki PR #33: Validate export destination paths before report generation

Focus: CLI input validation
Contribution Type: Correctness fix
Technical Area: Go CLI, export command, filesystem paths
Ecosystem: go
Project: Hosomaki
PR: https://github.com/rivernova/hosomaki/pull/33
Issue: https://github.com/rivernova/hosomaki/issues/20

## Summary

This contribution added earlier validation to the Hosomaki export command so invalid output paths fail before expensive report generation work begins.

## Technical Value

- Improves CLI feedback for invalid destination paths.
- Avoids wasted report-generation work when export cannot succeed.
- Keeps filesystem validation close to the command boundary.

## Implementation Notes

- Added validation around the export output path.
- Kept report generation from running when the destination is invalid.
- Added focused coverage for the validation path.

## Key Learnings

- CLI commands should fail fast on invalid filesystem inputs.
- Path validation belongs near the command boundary when later stages assume writable destinations.
