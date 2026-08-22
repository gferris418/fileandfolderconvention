# EIOS File & Folder Convention v1.0 — Standard Index

## Purpose

This index explains why every normative document in `standard/v1.0/` exists. The documents are intentionally separated so naming, business structure, governance boundaries, CIM alignment, provider projection, portability, source traceability, and purpose definitions can evolve through controlled review without becoming one unmanageable document.

| Document | Purpose |
|---|---|
| `00-principles.md` | Defines the non-negotiable principles of the convention, including provider neutrality, path-independent identity, metadata-driven governance, explicit relationships, and the requirement that every structural item has a defined purpose/boundary. |
| `01-logical-information-spaces.md` | Defines the stable enterprise-level logical spaces and explains what business domain each space exists to support. |
| `02-folder-naming-standard.md` | Defines structural folder naming syntax, dynamic business-root naming, depth/character rules, prohibited catch-all patterns, and mandatory purpose registration for new folders. |
| `03-file-naming-standard.md` | Defines human-readable file-display conventions while preserving the separation between filenames, enterprise document numbers, revisions, and canonical identity. |
| `04-document-numbering.md` | Defines the purpose and structure of controlled enterprise document numbers, including immutability and non-reuse rules. |
| `05-project-structure.md` | Defines the Project navigation template and the purpose, typical contents, and boundary of every project folder. |
| `06-opportunity-tender-structure.md` | Defines the Opportunity/Tender navigation template from source receipt through submission, clarification, award transition, and closure. |
| `07-governance-structure.md` | Defines Governance subspaces and separates strategy, corporate secretarial, legal, risk/compliance, policy, internal audit, and board-management purposes. |
| `08-finance-structure.md` | Defines Finance & Treasury subspaces and separates accounting, receivables, payables, project finance, tax, treasury, banking instruments, audit, and reporting purposes. |
| `09-records-archive-structure.md` | Defines the boundary between human-facing closeout/archive navigation and canonical records, retention, legal hold, immutability, and disposition governance. |
| `10-exceptions-and-governance.md` | Defines how deviations/local additions are proposed, approved, documented, reviewed, and prevented from overriding EIOS semantics. |
| `11-eios-cim-alignment.md` | Crosswalks the file/folder convention to EIOS-CIM concepts including information scopes, canonical information-object types, business objects, lifecycle, relationships, and non-file representations. |
| `12-repository-projection-and-bindings.md` | Defines how logical folders/views relate to Repository, RepositoryBinding, binding role, write mode, synchronization, conflict, provider capability, and authorization semantics. |
| `13-portability-export-structure.md` | Defines the purpose and layout of an EIOS portability/export materialization and prevents export-package structure from being confused with business-navigation structure. |
| `14-source-alignment-register.md` | Records which supplied CIM source materials informed each convention addition/correction and why the convention adopted the newer corrected semantics where historical documents differed. |
| `15-purpose-register.md` | Provides the normative purpose, typical contents, and boundary/exclusion definition for every current information space, folder, template node, and local-addition requirement. |

## Reading order

For implementation, use this sequence:

```text
00 Principles
    ↓
01 Logical Spaces
    ↓
15 Purpose Register
    ↓
02–04 Naming / Numbering
    ↓
05–10 Business Structures / Governance
    ↓
11–14 CIM / Repository / Portability / Source Alignment
```

A conforming implementation must not copy a folder tree without also adopting the associated purpose and boundary definitions.
