# Maven PR #12069: Isolate synthetic reactor artifacts during site builds

Focus: Reactor dependency resolution
Contribution Type: Correctness and isolation fix
Technical Area: Maven reactor, site lifecycle, artifact resolution
Ecosystem: java
Project: Apache Maven
PR: https://github.com/apache/maven/pull/12069
Issue: N/A

## Summary

This contribution adjusted Maven reactor resolution during site builds so consumers can inspect module dependencies before packaging without polluting the project-local repository.

## Technical Value

- Improves lifecycle behavior for reactor builds that run site reports before producer modules are packaged.
- Prevents synthetic empty artifacts from contaminating later resolution paths.
- Keeps the workaround isolated from normal package/build outputs.

## Implementation Notes

- Detected site execution from the session goals rather than late producer lifecycle state.
- Moved synthetic jars to a separate reactor-empty-artifacts directory.
- Cached generated paths with computeIfAbsent and reinforced the integration test.

## Key Learnings

- Consumer dependency resolution can happen before producer lifecycle state reflects the global build intent.
- Auxiliary build artifacts should stay outside normal repository paths to avoid leaking into later phases.
