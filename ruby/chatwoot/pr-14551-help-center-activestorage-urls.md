# Chatwoot PR #14551: Use Help Center hosts for ActiveStorage URLs

Focus: Custom-domain asset consistency
Contribution Type: Regression fix
Technical Area: Rails, ActiveStorage, Help Center public pages
Ecosystem: ruby
Project: Chatwoot
PR: https://github.com/chatwoot/chatwoot/pull/14551
Issue: https://github.com/chatwoot/chatwoot/issues/14431

## Summary

This contribution fixed Help Center pages on custom domains so ActiveStorage images use the public request host instead of leaking the main Chatwoot instance domain.

## Technical Value

- Improves public Help Center domain consistency.
- Prevents unexpected exposure of the main application host in rendered assets.
- Covers both newly generated URLs and persisted article content with old absolute links.

## Implementation Notes

- Set ActiveStorage::Current.url_options in public Help Center controllers from the current request.
- Rewrote only /rails/active_storage/... URLs in rendered article content to the public host.
- Added request specs for portal logo, author avatar, and article images.

## Key Learnings

- ActiveStorage absolute URLs depend on current URL options outside the default application context.
- Persisted rendered content may need a narrow rewrite path in addition to correct future URL generation.
