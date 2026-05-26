# scikit-learn PR #34081: Clarify fixed vocabulary behavior with n-grams

Focus: Documentation correctness
Contribution Type: Technical exploration
Technical Area: Machine learning documentation, feature extraction, vectorizer tests
Ecosystem: python
Project: scikit-learn
PR: https://github.com/scikit-learn/scikit-learn/pull/34081
Issue: https://github.com/scikit-learn/scikit-learn/issues/16017

## Summary

This technical exploration clarified how fixed vocabularies interact with n-gram ranges in CountVectorizer and TfidfVectorizer, documenting that vocabulary entries are interpreted as final feature terms.

## Technical Value

- Improves conceptual clarity around text feature extraction.
- Connects documentation wording with regression-oriented test coverage.
- Records a focused investigation in a mature machine learning library.

## Implementation Notes

- Clarified vocabulary parameter documentation for n-gram usage.
- Added regression coverage for fixed vocabularies with character bigrams.
- Validated the targeted feature extraction tests in an isolated Docker environment.

## Key Learnings

- Documentation and tests can reinforce each other when an API behavior is easy to misunderstand.
- Feature extraction APIs need precise language because token and feature vocabulary are not always the same thing.
