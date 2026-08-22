# Conformance

A conforming implementation must preserve the distinction between human-facing organization and canonical EIOS semantics.

## Required test classes

1. **Folder naming** — normative template paths conform to the naming rules.
2. **Purpose completeness** — every normative information space, folder, template node, controlled view, and structural local addition has a registered business purpose.
3. **Purpose quality** — each purpose definition states why the item exists, typical contents, and an explicit boundary/exclusion; label-only definitions fail.
4. **Purpose uniqueness** — parallel structural nodes must have materially distinguishable purposes. Overlapping/duplicate-purpose nodes require redesign, consolidation, or a documented governed exception.
5. **File naming** — controlled-document filenames conform to the display convention without becoming canonical identity.
6. **Prohibited naming noise** — reject uncontrolled patterns such as `Final FINAL`, `Copy of Copy`, ambiguous version suffixes, and undefined catch-all folders.
7. **Template completeness** — published templates contain their required normative nodes.
8. **Seven-scope coverage** — implementation supports navigational projections for `GROUP`, `ENTITY`, `OPPORTUNITY`, `PROJECT`, `CONTRACT`, `FUNCTION`, and `EXTERNAL` without treating the path as canonical `informationScope`.
9. **Business-context preservation** — folder placement must not substitute for `owningEntityRef`, `opportunityRef`, `projectRef`, `contractRef`, `functionCode`, or `counterpartyRef` where canonical context is required.
10. **Organization role neutrality** — one Organization may appear in customer/supplier/partner/regulator/etc. views without creating separate canonical identities.
11. **Multi-entity project neutrality** — participating-entity views do not create competing canonical Project identities or redefine project/entity relationship roles.
12. **Non-file object support** — CanonicalMessage, CanonicalDataset, CanonicalRecord, CanonicalMedia, and CanonicalPackage are not required to become physical files or folders when the provider has a more suitable native representation.
13. **Package membership** — physical directory membership must not be treated as authoritative CanonicalPackage membership.
14. **Lifecycle separation** — presentation states such as `ACTIVE`, `CLOSEOUT`, `CLOSED`, and `ARCHIVED` must not automatically change canonical revision states (`DRAFT`, `WORKING`, `REVIEW`, `AUTHORIZED`, `PUBLISHED`, `SUPERSEDED`, `WITHDRAWN`, `RECORD`, `DISPOSED`).
15. **Records/governance separation** — `Archive`, `Records`, `Do_Not_Delete`, `Legal_Hold`, or similar paths must not establish record declaration, retention, legal hold, immutability, disposition, or data-residency status.
16. **Repository-binding separation** — path labels must not establish binding role, write mode, synchronization state, conflict state, or authoritative-copy designation.
17. **Provider capability completeness** — each provider profile declares metadata, versioning, ACL/sharing, retention, legal hold, immutability, classification/DLP, workflow, search, events, audit, and residency capabilities or explicit gaps/compensating controls.
18. **Authorization non-broadening** — provider mappings must never broaden EIOS authorization; permission projections may only preserve or restrict effective access.
19. **Relationship separation** — nesting, co-location, shortcuts, or path ancestry must not create canonical business/information relationships.
20. **Portability structure** — an EIOS export materialization preserves `manifest.json`, `metadata/`, `relationships/`, `permissions/`, `governance/`, and `content/binaries/` without confusing that package with the enterprise business folder hierarchy.
21. **Path-independent identity** — moving or renaming a provider-native projection leaves the canonical `objectUID` unchanged.
22. **Document-number non-reuse** — file/folder operations must never recycle an issued `enterpriseDocumentNo`.
23. **Taxonomy authority** — local YAML/navigation labels cannot create, replace, repurpose, or silently supersede canonical EIOS taxonomy terms.
24. **Local addition registration** — every non-normative structural folder introduced locally records parent, purpose, typical contents, exclusions/boundary, owner/steward, effective date, and review date where temporary.

## Purpose conformance rule

A structural node fails conformance if any of the following are true:

```text
purpose is missing
purpose merely repeats the folder label
no typical contents are defined
no boundary/exclusion is defined
purpose materially duplicates a sibling node without an approved reason
folder is an undefined catch-all (e.g. MISC/GENERAL/TEMP/STUFF)
folder is used to repair missing canonical metadata or relationships
```

The authoritative purpose definitions for the normative v1.0 structure are in `standard/v1.0/15-purpose-register.md`.

## Negative fixtures

Negative tests should explicitly demonstrate that the following inferences are prohibited:

```text
folder path -> canonical identity
folder path -> informationScope/businessContext
folder path -> authorization
folder path -> record declaration
folder path -> retention/legal hold/immutability/disposition
folder path -> data residency
folder path -> authoritative repository binding
folder path -> synchronization state
folder nesting -> canonical relationship
folder contents -> CanonicalPackage membership
undefined folder -> valid business purpose
folder label -> sufficient purpose definition
```

The conformance suite will be expanded into executable tests before this convention is promoted from draft to frozen v1.0.0.
