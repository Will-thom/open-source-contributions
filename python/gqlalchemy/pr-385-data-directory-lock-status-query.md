# GQLAlchemy PR #385: Add DATA DIRECTORY LOCK STATUS query support

Focus: Query builder API coverage
Contribution Type: Feature addition
Technical Area: Cypher query builder, client API, documentation
Ecosystem: python
Project: GQLAlchemy
PR: https://github.com/memgraph/gqlalchemy/pull/385
Issue: https://github.com/memgraph/gqlalchemy/issues/253

## Summary

This contribution added first-class query-builder support for Memgraph DATA DIRECTORY LOCK STATUS, removing the need for callers to write custom Cypher for that operation.

## Technical Value

- Expands declarative API coverage for an operational Memgraph command.
- Keeps query execution behavior aligned with commands that return rows.
- Adds documentation so the new entrypoint is discoverable.

## Implementation Notes

- Added a DataDirectoryLockStatusPartialQuery implementation.
- Exposed QueryBuilder().data_directory_lock_status() and a top-level helper.
- Added unit tests for query generation and execute_and_fetch behavior.

## Key Learnings

- Query-builder commands that return data need fetch semantics even without a RETURN clause.
- Targeted client-library additions benefit from focused tests that do not require a database process.
