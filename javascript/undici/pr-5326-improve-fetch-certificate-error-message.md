# Undici PR #5326: Improve fetch certificate error message

Focus: TLS diagnostics
Contribution Type: Developer experience improvement
Technical Area: Fetch API, TLS certificates, Node.js
Ecosystem: javascript
Project: Undici
PR: https://github.com/nodejs/undici/pull/5326
Issue: https://github.com/nodejs/undici/issues/2199

## Summary

This contribution improved `fetch()` diagnostics for HTTPS endpoints whose certificate chain fails validation.

## Technical Value

- Keeps the public `TypeError` surface while making the message more actionable.
- Preserves the original TLS failure through `error.cause`.
- Helps diagnose internal CAs, custom certificate chains, and untrusted certificate deployments.

## Implementation Notes

- Added formatting for known TLS certificate verification failures.
- Added a regression test using a local HTTPS server and certificate fixture.
- Preserved existing fetch error wrapping behavior outside the targeted TLS path.

## Key Learnings

- Standard API compatibility and production diagnostics can coexist when low-level causes are preserved.
- Local certificate fixtures are a reliable way to validate TLS behavior without external network dependencies.
