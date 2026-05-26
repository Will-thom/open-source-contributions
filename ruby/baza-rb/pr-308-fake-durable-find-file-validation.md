# baza.rb PR #308: Align fake durable_find file-name validation

Focus: Fake client parity
Contribution Type: Compatibility fix
Technical Area: Ruby API client, test doubles, durable lookup
Ecosystem: ruby
Project: baza.rb
PR: https://github.com/zerocracy/baza.rb/pull/308
Issue: https://github.com/zerocracy/baza.rb/issues/299

## Summary

This contribution fixed the fake client so durable_find accepts a durable file name like the real client instead of requiring a local file to exist on disk.

## Technical Value

- Improves parity between production and fake client behavior.
- Prevents tests from rejecting inputs that production accepts.
- Clarifies the durable lookup contract as a name-based query.

## Implementation Notes

- Removed local file-existence validation from BazaRb::Fake#durable_find.
- Kept explicit nil and empty-string validation aligned with the real client.
- Updated YARD wording and added a regression test for a non-existing local file name.

## Key Learnings

- Fakes should mirror public contracts, not validations copied from similar but different methods.
- Name-based remote lookups should not be validated as local filesystem reads.
