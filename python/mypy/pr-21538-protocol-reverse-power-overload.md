# mypy PR #21538: Allow protocol reverse power overloads with modulo

Focus: Static typing correctness
Contribution Type: Regression fix
Technical Area: Python protocols, operator overloads, type checking
Ecosystem: python
Project: mypy
PR: https://github.com/python/mypy/pull/21538
Issue: https://github.com/python/mypy/issues/10786

## Summary

This contribution relaxed reverse-operator validation for protocols so structural typing can express overloaded __rpow__ signatures that include the ternary modulo variant.

## Technical Value

- Improves protocol expressiveness in Python static typing.
- Keeps concrete-class reverse-operator safeguards intact.
- Adds a focused regression test in the protocol test suite.

## Implementation Notes

- Returned early from reverse-operator signature checks when the definition belongs to a protocol.
- Preserved existing validation paths for non-protocol classes.
- Added a check-protocols test covering overloaded __rpow__ with modulo.

## Key Learnings

- Protocols describe structural contracts and do not always need the same runtime-dispatch restrictions as concrete classes.
- Typing fixes need nearby regression coverage plus broader suites to protect adjacent operator behavior.
