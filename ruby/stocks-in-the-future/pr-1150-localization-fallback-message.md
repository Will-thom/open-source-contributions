# Stocks in the Future PR #1150: Use localized messaging consistently

Focus: Localization consistency
Contribution Type: UI consistency fix
Technical Area: Rails, I18n, user-facing messages
Ecosystem: ruby
Project: Stocks in the Future
PR: https://github.com/rubyforgood/stocks-in-the-future/pull/1150
Issue: https://github.com/rubyforgood/stocks-in-the-future/issues/1143

## Summary

This contribution removed a local message override so the application could rely on its shared localization flow for the affected user-facing message.

## Technical Value

- Improves consistency of user-facing copy.
- Reduces duplicated message logic in the view layer.
- Aligns the behavior with Rails I18n expectations.

## Implementation Notes

- Removed the local message block that bypassed the shared translation path.
- Kept the UI behavior aligned with existing localized messages.
- Validated the change with the relevant Rails test path.

## Key Learnings

- Localized applications should avoid one-off message paths when a shared translation key exists.
- Small UI text fixes can still carry value when they reduce inconsistency across workflows.
