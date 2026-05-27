# fastify-mysql PR #189: Document pool options

Focus: Integration documentation
Contribution Type: Documentation improvement
Technical Area: Fastify plugins, MySQL pooling, Node.js
Ecosystem: javascript
Project: fastify-mysql
PR: https://github.com/fastify/fastify-mysql/pull/189
Issue: https://github.com/fastify/fastify-mysql/issues/100

## Summary

This contribution documented how to configure MySQL pool options through the Fastify plugin registration options.

## Technical Value

- Makes production-relevant pool configuration easier to discover.
- Clarifies how plugin options map to `mysql2.createPool()`.
- Covers both callback-based and promise-based usage styles.

## Implementation Notes

- Added a `Pool options` section to the README.
- Included examples for `connectionLimit`, `waitForConnections`, and `queueLimit`.
- Documented the boundary where `connectionString` changes the configuration path.

## Key Learnings

- Plugin documentation is strongest when it connects wrapper options to the underlying library contract.
- Operational settings such as pooling deserve explicit examples because they affect concurrency and resource usage.
