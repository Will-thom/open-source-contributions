# MudBlazor PR #13244: Preserve MudRating intrinsic width on mobile

Focus: Mobile UI consistency
Contribution Type: Regression fix
Technical Area: Blazor components, SCSS layout, responsive behavior
Ecosystem: dotnet
Project: MudBlazor
PR: https://github.com/MudBlazor/MudBlazor/pull/13244
Issue: https://github.com/MudBlazor/MudBlazor/issues/12013

## Summary

This contribution fixed a MudRating layout issue where applying the d-block utility could make the component occupy extra width on mobile when MaxValue was customized.

## Technical Value

- Improves responsive UI consistency for a widely used Blazor component.
- Makes the component more resilient to consumer-provided utility classes.
- Keeps the fix scoped to the rating root style without changing component API.

## Implementation Notes

- Added width: fit-content to .mud-rating-root.
- Added max-width: 100% so the intrinsic sizing cannot exceed the container.
- Validated the normal project build path with the SCSS asset pipeline enabled.

## Key Learnings

- Components that expose a Class parameter need resilience against external utilities overriding structural styles.
- Intrinsic width can preserve layout intent when display is changed by consumer classes.
