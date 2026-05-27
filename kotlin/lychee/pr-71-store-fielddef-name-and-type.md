# Lychee PR #71: Store FieldDef name and type

Focus: Schema metadata consistency
Contribution Type: Correctness fix
Technical Area: Kotlin data modeling, schema fields, equality semantics
Ecosystem: kotlin
Project: Lychee
PR: https://github.com/Miha-x64/Lychee/pull/71
Issue: https://github.com/Miha-x64/Lychee/issues/65

## Summary

This contribution restored direct `name` and `type` storage on `FieldDef` and aligned equality, hashing, and string output with the richer field metadata.

## Technical Value

- Makes schema field objects more self-descriptive.
- Prevents equality from collapsing fields that share ordinals but differ semantically.
- Improves debugging output for schema-related failures.

## Implementation Notes

- Stored `name` and `type` directly in `FieldDef`.
- Updated `name()`, `type()`, `equals()`, `hashCode()`, and `toString()`.
- Added `SchemaPropsTest` coverage for metadata exposure and equality differences.

## Key Learnings

- Ordinal-only identity can lose meaning when fields belong to different schemas.
- Including structural metadata in equality improves correctness and makes diagnostics more useful.
