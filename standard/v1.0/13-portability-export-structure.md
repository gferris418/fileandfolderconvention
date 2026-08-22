# 13 — Portability and Export Structure

## 1. Purpose

The everyday file/folder convention and the EIOS portability package serve different purposes. Human-facing business folders may vary by provider, but an EIOS export must preserve canonical information, relationships, permissions, governance evidence, and content independently of the source repository.

## 2. Canonical export package projection

Where an EIOS export package is materialized as directories, the reserved structure is:

```text
export-package/
├── manifest.json
├── metadata/
├── relationships/
├── permissions/
├── governance/
└── content/
    └── binaries/
```

These names are portability-package structures, not enterprise business folders.

## 3. Separation from business folders

A provider must not flatten an export into a business folder tree in a way that loses canonical metadata or relationships. The export package must be capable of carrying:

- manifest and package identity;
- canonical metadata;
- relationships;
- authorization/permission evidence;
- governance/policy evidence;
- binary content;
- integrity digests.

## 4. Source repository independence

The export package is a portability artifact. Provider-native IDs and paths may be recorded as evidence, but restoration or migration must not depend on the original provider continuing to exist.

## 5. Archive distinction

An export package is not automatically an archive, legal record, backup, or authoritative repository binding. Those statuses remain governed by EIOS policy and repository metadata.
