# 12 — Repository Projection and Binding Semantics

## 1. Purpose

A folder hierarchy is not a repository-binding model. EIOS may bind the same canonical information object to multiple provider-native locations while preserving one canonical identity.

## 2. Binding roles

Provider mappings must recognize the EIOS repository-binding roles:

```text
AUTHORITATIVE
WORKING
PUBLISHED
RECORD_COPY
REPLICA
CACHE
MIGRATION_SOURCE
MIGRATION_TARGET
```

A folder name such as `Published`, `Archive`, or `Working` does not itself establish the corresponding binding role. Binding role is canonical metadata.

## 3. Write modes

Repository bindings may use:

```text
READ_WRITE
READ_ONLY
IMMUTABLE
SYSTEM_MANAGED
```

Provider mappings must state how native permissions, locks, records functions, or storage controls implement the required write mode. A human-facing folder name is insufficient evidence.

## 4. Synchronization and conflicts

A physical projection can be:

```text
CURRENT
BEHIND
AHEAD
PENDING
CONFLICT
ERROR
```

Conflict types can include content, metadata, permission, or state conflicts. The visible directory tree must never be assumed to prove synchronization state.

## 5. Provider resolution

The provider of a binding is resolved through the canonical repository relationship. The convention must not duplicate provider identity in folder paths merely to make bindings work.

## 6. Authoritative copy rule

Where a provider exposes multiple copies or views, the mapping must identify which native location corresponds to the canonical `AUTHORITATIVE` binding, if any. Additional `WORKING`, `PUBLISHED`, `RECORD_COPY`, `REPLICA`, or cache locations remain secondary projections.

Moving or copying a file in a provider does not silently transfer authoritative status. EIOS policy/placement decisions govern authoritative-copy changes.

## 7. Provider capability declaration

Each provider mapping must document whether the selected native construct supports or requires compensating controls for:

- metadata;
- versioning;
- native ACLs and role/group permissions;
- external sharing;
- retention and event-based retention;
- legal hold;
- immutable/WORM storage;
- classification and DLP;
- workflow;
- full-text and semantic search;
- webhooks/change events;
- audit logging;
- data-residency controls.

Logical folders must not promise a capability that the native repository cannot provide.
