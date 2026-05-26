# Yuedu-reader PR #26: Add a localized RSS article 403 message

Focus: Reader-mode error experience
Contribution Type: UX consistency fix
Technical Area: Swift, SwiftUI, localization, RSS reader
Ecosystem: ios
Project: Yuedu-reader
PR: https://github.com/CHANG-JUI-LIN/Yuedu-reader/pull/26
Issue: https://github.com/CHANG-JUI-LIN/Yuedu-reader/issues/18

## Summary

This contribution added a friendly localized message for HTTP 403 failures during RSS full-text extraction, replacing a technical status display with clearer user guidance.

## Technical Value

- Improves user experience when a site blocks full-article extraction.
- Keeps reader-mode error handling aligned with localized app behavior.
- Maintains language parity across the supported localization files.

## Implementation Notes

- Added specific handling for RSSArticleContentLoaderError.httpStatus(403).
- Displayed the 403 message directly while keeping generic wrappers for other extraction errors.
- Updated English, Traditional Chinese, and Simplified Chinese strings plus regression coverage.

## Key Learnings

- Reader-mode apps need to separate expected access denial from technical app failure.
- Localized UX changes require updating all relevant lproj resources to avoid language drift.
