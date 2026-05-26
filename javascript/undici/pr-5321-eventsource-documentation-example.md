# Undici PR #5321: Add an EventSource documentation example

Focus: API documentation clarity
Contribution Type: Documentation improvement
Technical Area: Node.js, EventSource, Server-Sent Events
Ecosystem: javascript
Project: Undici
PR: https://github.com/nodejs/undici/pull/5321
Issue: https://github.com/nodejs/undici/issues/536

## Summary

This contribution added a practical Server-Sent Events example to Undici EventSource documentation, showing both named events and default message handling.

## Technical Value

- Improves discoverability of EventSource usage in a core Node.js HTTP library.
- Shows the relationship between named SSE events and default message events.
- Provides documentation value without expanding runtime scope.

## Implementation Notes

- Added a self-contained HTTP server emitting text/event-stream data.
- Demonstrated addEventListener, onmessage, error handling, and connection closing.
- Adjusted surrounding API text for clarity.

## Key Learnings

- Documentation examples should be close enough to real usage that readers can mentally execute them.
- SSE defaults matter: unnamed events arrive through message, while named events require listeners.
