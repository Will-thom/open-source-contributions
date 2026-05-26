# Plume PR #21: Internalize the UIKit implementation view

Focus: Public API surface control
Contribution Type: Maintainability improvement
Technical Area: SwiftUI, UIKit bridge, package API design
Ecosystem: ios
Project: Plume
PR: https://github.com/samlupton/Plume/pull/21
Issue: https://github.com/samlupton/Plume/issues/17

## Summary

This contribution narrowed Plume public API by making the UIKit implementation view internal while keeping the SwiftUI PlumeView as the supported public entrypoint.

## Technical Value

- Reduces public API surface in a SwiftUI-focused package.
- Preserves implementation flexibility around the UIKit bridge.
- Aligns documentation with the intended public usage path.

## Implementation Notes

- Moved PlumeUIView to internal package surface.
- Changed the UIViewRepresentable bridge to expose UIView publicly while casting internally for emit behavior.
- Updated documentation to remove direct UIKit usage guidance.

## Key Learnings

- Internalizing a Swift type requires checking every public signature that exposes it.
- SwiftUI/UIKit bridges can hide implementation details by returning a stable supertype.
