# Symfony PR #64359: Support SVG dimensions with explicit units

Focus: Image validation correctness
Contribution Type: Compatibility fix
Technical Area: SVG parsing, validator component
Ecosystem: php
Project: Symfony
PR: https://github.com/symfony/symfony/pull/64359
Issue: https://github.com/symfony/symfony/issues/64350

## Summary

This contribution fixed Symfony image validation for SVG dimensions that include explicit units, keeping validation aligned with common SVG authoring patterns.

## Technical Value

- Improves compatibility for valid SVG files that specify dimensions with units.
- Keeps image validation behavior focused on semantic dimensions rather than raw attribute shape.
- Adds regression coverage to protect the parser behavior.

## Implementation Notes

- Expanded SVG dimension parsing in the ImageValidator path.
- Handled unit-suffixed width and height values.
- Added tests covering SVG dimensions with explicit units.

## Key Learnings

- Validators often need to understand common file-format variants rather than only the simplest attribute form.
- SVG metadata can look textual but still represents structured numeric constraints.
