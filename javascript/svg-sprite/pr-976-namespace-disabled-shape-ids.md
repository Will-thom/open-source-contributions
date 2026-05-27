# svg-sprite PR #976: Restore basename IDs when namespaceIDs is disabled

Focus: SVG build output compatibility
Contribution Type: Regression fix
Technical Area: Node.js build tooling, SVG symbols, namespace options
Ecosystem: javascript
Project: svg-sprite
PR: https://github.com/svg-sprite/svg-sprite/pull/976
Issue: https://github.com/svg-sprite/svg-sprite/issues/763

## Summary

This contribution fixed a CLI regression where symbol IDs included relative directory paths even when SVG namespace IDs were explicitly disabled.

## Technical Value

- Restores compatibility for builds that rely on filename-based symbol IDs.
- Keeps default namespaced behavior intact for users who want directory-derived uniqueness.
- Adds targeted regression coverage at the shape-construction layer.

## Implementation Notes

- Changed SVGShape to use the file basename when namespaceIDs is false.
- Preserved directory-derived names when namespace behavior remains enabled.
- Added a unit test for files in subdirectories with namespaceIDs disabled.

## Key Learnings

- A visible symbol-id regression can originate in lower-level file-name normalization.
- Comparing adjacent release tags is a fast way to identify where behavior changed.
