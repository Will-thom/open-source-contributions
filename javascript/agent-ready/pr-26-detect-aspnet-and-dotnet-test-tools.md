# agent-ready PR #26: Detect ASP.NET Core and .NET test tools

Focus: .NET repository detection
Contribution Type: Developer experience improvement
Technical Area: Repository scanning, ASP.NET Core, .NET testing
Ecosystem: javascript
Project: agent-ready
PR: https://github.com/EShener/agent-ready/pull/26
Issue: https://github.com/EShener/agent-ready/issues/22

## Summary

This contribution expanded .NET detection so the scanner can identify ASP.NET Core projects and common .NET test tooling from project manifests and source files.

## Technical Value

- Distinguishes generic .NET projects from web applications.
- Surfaces xUnit, NUnit, MSTest, and Microsoft.NET.Test.Sdk as actionable testing signals.
- Improves generated repository guidance without requiring `dotnet` execution.

## Implementation Notes

- Read selected `.csproj` and `Program.cs` files during profiling.
- Detected `Microsoft.NET.Sdk.Web`, minimal API builder usage, and route mapping patterns.
- Extended .NET fixtures and detector documentation.

## Key Learnings

- Useful framework signals often live inside manifests rather than filenames.
- Selective parsing of targeted project files preserves fast local scanning while improving report quality.
