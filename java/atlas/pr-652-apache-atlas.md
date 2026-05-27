# Apache Atlas PR #652: Import/export API documentation

Focus: API documentation discoverability
Contribution Type: Documentation
Technical Area: REST API documentation
Ecosystem: java
Project: Apache Atlas
PR: https://github.com/apache/atlas/pull/652
Issue: ATLAS-4828

## Summary

This technical note records a documentation contribution to Apache Atlas, improving navigation from the main REST API documentation page to the Export and Import REST API reference.

## Technical Value

- Improves discoverability for import/export APIs used in metadata migration, backup, and integration workflows.
- Keeps related REST API references connected from the main documentation entry point.
- Reduces friction for contributors and users looking for API coverage beyond the general and legacy REST documentation links.

## Implementation Notes

- Updated `docs/src/documents/RestAPI.md`.
- Added a direct `Export & Import REST API Documentation` link.
- Preserved the existing documentation list structure and linked to the `#/ImportExportAPI` section.

## Key Learnings

- Documentation navigation is part of the technical user experience for data governance platforms.
- API references for operational workflows should be reachable from the primary REST API documentation surface.
- Focused documentation changes can carry portfolio value when they clarify how to find important platform capabilities.
