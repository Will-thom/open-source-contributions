# Hosomaki PR #34: Limit top process data at collection time

Focus: Data normalization boundary
Contribution Type: Maintainability improvement
Technical Area: Go CLI, system collector, prompt input
Ecosystem: go
Project: Hosomaki
PR: https://github.com/rivernova/hosomaki/pull/34
Issue: https://github.com/rivernova/hosomaki/issues/23

## Summary

This contribution moved TopProcesses truncation into the system collector so snapshots are normalized before downstream prompt construction.

## Technical Value

- Reduces internal data volume before prompt generation.
- Keeps the domain limit close to where the data is collected.
- Simplifies downstream prompt code by consuming normalized snapshots.

## Implementation Notes

- Limited TopProcesses to 10 lines immediately after ps collection.
- Removed redundant truncation responsibility from the prompt layer.
- Added unit tests for long, short, and empty process output.

## Key Learnings

- When a limit is part of the collected data contract, applying it at the source reduces coupling.
- Environment-dependent Go CLI tests benefit from isolating pure logic from OS command assumptions.
