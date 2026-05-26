# CodeIgniter4 PR #10233: Handle null PHP ini values in phpini check

Focus: PHP runtime compatibility
Contribution Type: Compatibility fix
Technical Area: PHP CLI command, ini_get_all, test stability
Ecosystem: php
Project: CodeIgniter4
PR: https://github.com/codeigniter4/CodeIgniter4/pull/10233
Issue: https://github.com/codeigniter4/CodeIgniter4/issues/9968

## Summary

This contribution fixed the phpini:check command so newer PHP runtimes that return null for existing ini directive values do not break CLI table rendering.

## Technical Value

- Improves compatibility with newer PHP runtime behavior.
- Makes the Commands test component more resilient under randomized execution.
- Keeps the fix scoped to data normalization before CLI rendering.

## Implementation Notes

- Normalized global_value and local_value from ini_get_all() to strings.
- Prevented null values from reaching CLI::color().
- Kept the change localized in system/Security/CheckPhpIni.php.

## Key Learnings

- Runtime metadata APIs can return null even for directives that exist.
- CLI renderers should receive normalized display values rather than raw runtime metadata.
