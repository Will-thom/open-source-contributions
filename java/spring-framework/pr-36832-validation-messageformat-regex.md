# Spring Framework PR #36832: Preserve validation messages with regex attributes

Focus: Validation message rendering correctness
Contribution Type: Regression fix
Technical Area: Bean Validation, MessageFormat, serialization
Ecosystem: java
Project: Spring Framework
PR: https://github.com/spring-projects/spring-framework/pull/36832
Issue: https://github.com/spring-projects/spring-framework/issues/21750

## Summary

This contribution fixed validation messages that mixed Spring-style placeholders with Bean Validation attributes containing regular-expression braces. The change keeps message interpolation predictable when constraint attributes are rendered through MessageFormat.

## Technical Value

- Improves correctness for applications using localized validation messages with @Pattern constraints.
- Protects a subtle two-step rendering path where provider interpolation and Spring MessageSource formatting overlap.
- Preserves behavior after validation errors are serialized.

## Implementation Notes

- Escaped constraint attribute values before they are exposed to MessageFormat rendering.
- Stored the render-default-message decision in the serializable error state.
- Added regression coverage for regex quantifiers and serialized FieldError rendering.

## Key Learnings

- Validation frameworks can compose multiple formatting syntaxes in one error message path.
- Serializable error objects need to carry enough rendering metadata after transient validation objects disappear.
