# 00 — Principles

## 1. Scope

This standard governs the human-facing organization of enterprise information: logical information spaces, folder structures, file names, and reusable organizational templates.

It does not define canonical object identity, repository bindings, security policy, legal hold, retention, records disposition, or provider-native permissions. Those remain EIOS concerns.

## 2. Normative principles

### P01 — Canonical identity is path-independent
A document or information object retains the same EIOS `objectUID` regardless of folder, repository, provider, file name, or native object identifier.

### P02 — Business identifiers are separate from canonical identifiers
An enterprise document number, project code, contract number, tender number, or other business code is not the primary canonical identity.

### P03 — Paths are projections
A folder path is a navigational projection for users. Moving information between folders must not imply creation of a new canonical object.

### P04 — Governance is metadata-driven
Classification, data category, legal hold, retention, disposition, authoritative-copy status, and authorization must not be inferred solely from folder location.

### P05 — Provider neutrality
The logical convention is defined independently of SharePoint, OneDrive, Google Drive, Oracle Content Management, Box, OpenText, S3, local file systems, or any other provider.

### P06 — Stable top-level information spaces
Top-level spaces are intentionally few, business-readable, and slow-changing. Project- or provider-specific variation belongs lower in the hierarchy or in provider mappings.

### P07 — Numbered folders are for navigation, not identity
Numeric prefixes such as `01_`, `02_`, and `99_` provide stable sorting and user orientation. They have no canonical semantic meaning unless separately represented in controlled metadata.

### P08 — File names remain readable
File names should assist users but must not carry the entire metadata model. If a required business attribute is already canonical metadata, it does not need to be duplicated in every path segment.

### P09 — Closed information is retained according to policy
`99_ARCHIVE` and `99_CLOSED` are organizational destinations, not retention or legal-record declarations.

### P10 — Exceptions are governed
Exceptions must be documented, approved, scoped, and time-bounded where practical. Provider limitations must be captured in provider mappings rather than silently altering the normative standard.

## 3. Identity layers

```text
CANONICAL IDENTITY
DOC-01J...
        |
        | immutable machine identity
        v
ENTERPRISE DOCUMENT NUMBER
[ENTITY]-[PROJECT]-[DISCIPLINE]-[DOCTYPE]-[SEQUENCE]
        |
        | controlled business identity
        v
DISPLAY FILE NAME
[EnterpriseDocumentNo]_[Revision]_[ShortTitle].[ext]
```

Renaming or moving the display file must not change the canonical identity or reuse an enterprise document number.
