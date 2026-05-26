# API Platform PR #8190: Correct JSON:API collection schema generation

Focus: OpenAPI schema correctness
Contribution Type: Compatibility fix
Technical Area: JSON:API, OpenAPI, Symfony
Ecosystem: php
Project: API Platform
PR: https://github.com/api-platform/core/pull/8190
Issue: N/A

## Summary

This contribution corrected the OpenAPI schema generated for JSON:API collection documents with included resources, keeping the generated contract aligned with the expected collection shape.

## Technical Value

- Improves schema accuracy for consumers of generated API documentation.
- Keeps JSON:API collection metadata consistent without expanding the behavioral surface.
- Highlights the importance of targeting the correct maintenance branch in split-package projects.

## Implementation Notes

- Simplified JSON:API schema handling by mutating the data properties directly.
- Rebuilt the branch on the correct 4.3 base after CI exposed branch-matrix incompatibility.
- Kept the change focused on schema generation behavior.

## Key Learnings

- In framework projects with maintenance branches, the PR base is part of the technical contract.
- CI failures can reflect branch dependency mismatch rather than a regression in the patch itself.
