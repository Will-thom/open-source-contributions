# baza.rb PR #311: Add input guards before enter computation

Focus: Client contract consistency
Contribution Type: Correctness fix
Technical Area: Ruby API client, fake parity, input validation
Ecosystem: ruby
Project: baza.rb
PR: https://github.com/zerocracy/baza.rb/pull/311
Issue: https://github.com/zerocracy/baza.rb/issues/298

## Summary

This contribution aligned BazaRb#enter with the fake client by rejecting invalid arguments before executing the caller-provided computation block.

## Technical Value

- Prevents wasted expensive work when input is invalid.
- Aligns production-client behavior with the fake used in tests.
- Makes the method contract clearer around required and optional values.

## Implementation Notes

- Added early guards for pname, badge, why, and positive integer job values.
- Kept job optional while validating it when provided.
- Added edge tests proving invalid inputs do not execute the block.

## Key Learnings

- Methods accepting blocks should validate arguments before yielding.
- A fake that behaves more sensibly than production can reveal a real contract gap worth closing.
