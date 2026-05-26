# Human Essentials PR #5574: Reset dependent resource selection on type changes

Focus: Admin UI data integrity
Contribution Type: Regression fix
Technical Area: Rails, Stimulus, system tests
Ecosystem: ruby
Project: Human Essentials
PR: https://github.com/rubyforgood/human-essentials/pull/5574
Issue: https://github.com/rubyforgood/human-essentials/issues/5565

## Summary

This contribution fixed an admin user form bug where changing the resource type could preserve an incompatible resource id and create an incorrect role assignment.

## Technical Value

- Protects administrative data integrity in a social-impact Rails application.
- Prevents silent cross-model id collisions from producing wrong associations.
- Adds end-to-end coverage for the user workflow that exposed the bug.

## Implementation Notes

- Cleared the dependent resource select whenever the resource type changes.
- Added a system test for switching from Organization to Partner without choosing a new resource.
- Verified the form reports an error instead of creating a user with stale state.

## Key Learnings

- Dependent selects must invalidate previous values when their data source changes.
- Backend validation remains essential, but the UI should avoid submitting stale incompatible state.
