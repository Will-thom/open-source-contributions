# RuboCop PR #15183: Expose style guide URLs as structured JSON

Focus: Structured formatter metadata
Contribution Type: Developer tooling improvement
Technical Area: Ruby static analysis, JSON formatter, cache serialization
Ecosystem: ruby
Project: RuboCop
PR: https://github.com/rubocop/rubocop/pull/15183
Issue: https://github.com/rubocop/rubocop/issues/7201

## Summary

This contribution added style_guide_url to RuboCop JSON offenses so integrations can consume the URL directly instead of parsing it out of display text.

## Technical Value

- Improves machine readability for editor and tooling integrations.
- Separates semantic metadata from human-facing offense messages.
- Preserves the new field through cache serialization.

## Implementation Notes

- Exposed the style-guide URL separately from MessageAnnotator references.
- Stored the metadata on Offense and emitted it from the JSON formatter.
- Added tests for annotation, JSON output, cache behavior, and changelog coverage.

## Key Learnings

- Structured formatters should expose semantic fields directly when the data already exists internally.
- Changing offense metadata requires considering cache and serialization paths, not only formatter output.
