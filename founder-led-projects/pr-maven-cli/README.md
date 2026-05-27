# PR Maven CLI

Role: Founder / Maintainer
Contribution Type: Founder-Led Project
Technical Area: Maven diagnostics, CI tooling, developer experience
Ecosystem: Go / Java / Maven
Project: PR Maven CLI
Repository: https://github.com/Will-thom/pr-maven-cli

## Summary

PR Maven CLI is an original open source CLI and Go library for turning Maven build artifacts into actionable PR and CI context. It discovers Maven modules, parses reports and logs, maps failures to modules, and emits human-readable and JSON output for developers, CI jobs, and coding agents.

## Technical Value

- Provides local-first diagnostics for Maven pull request workflows.
- Converts Surefire, Failsafe, SpotBugs, Maven Enforcer, and JaCoCo evidence into structured output.
- Establishes a foundation for agent-friendly CI triage without requiring hosted services.

## Implementation Notes

- Stage 2 expanded parser coverage through PRs #48 to #53.
- Added fixture-driven parsers for SpotBugs XML, Maven Enforcer failures, and JaCoCo thresholds.
- Introduced an internal parser registry, nested module fixture coverage, and Windows/POSIX path normalization tests.

## Key Learnings

- Founder-led OSS work should be labeled separately from external contributions to keep portfolio context transparent.
- Maven triage tooling benefits from treating XML reports and plugin logs as deterministic evidence sources.
- A focused internal registry can reduce coupling without overcommitting to a plugin architecture too early.
