# Conformance

A conforming implementation must preserve the distinction between human-facing organization and canonical EIOS semantics.

## Required test classes

1. **Folder naming** — normative template paths conform to the naming rules.
2. **File naming** — controlled-document filenames conform to the display convention without becoming canonical identity.
3. **Prohibited naming noise** — reject uncontrolled patterns such as `Final FINAL`, `Copy of Copy`, and ambiguous version suffixes.
4. **Template completeness** — published templates contain their required normative nodes.
5. **Seven-scope coverage** — implementation supports navigational projections for `GROUP`, `ENTITY`, `OPPORTUNITY`, `PROJECT`, `CONTRACT`, `FUNCTION`, and `EXTERNAL` without treating the path as canonical `informationScope`.
6. **Business-context preservation** — folder placement must not substitute for `owningEntityRef`, `opportunityRef`, `projectRef`, `contractRef`, `functionCode`, or `counterpartyRef` where canonical context is required.
7. **Organization role neutrality** — one Organization may appear in customer/supplier/partner/regulator/etc. views without creating separate canonical identities.
8. **Multi-entity project neutrality** — participating-entity views do not create competing canonical Project identities or redefine project/entity relationship roles.
9. **Non-file object support** — CanonicalMessage, CanonicalDataset, CanonicalRecord, CanonicalMedia, and CanonicalPackage are not required to become physical files or folders when the provider has a more suitable native representation.
10. **Package membership** — physical directory membership must not be treated as authoritative CanonicalPackage membership.
11. **Lifecycle separation** — presentation states such as `ACTIVE`, `CLOSEOUT`, `CLOSED`, and `ARCHIVED` must not automatically change canonical revision states (`DRAFT`, `WORKING`, `REVIEW`, `AUTHORIZED`, `PUBLISHED`, `SUPERSEDED`, `WITHDRAWN`, `RECORD`, `DISPOSED`).
12. **Records/governance separation** — `Archive`, `Records`, `Do_Not_Delete`, `Legal_Hold`, or similar paths must not establish record declaration, retention, legal hold, immutability, disposition, or data-residency status.
13. **Repository-binding separation** — path labels must not establish binding role, write mode, synchronization state, conflict state, or authoritative-copy designation.
14. **Provider capability completeness** — each provider profile declares metadata, versioning, ACL/sharing, retention, legal hold, immutability, classification/DLP, workflow, search, events, audit, and residency capabilities or explicit gaps/compensating controls.
15. **Authorization non-broadening** — provider mappings must never broaden EIOS authorization; permission projections may only preserve or restrict effective access.
16. **Relationship separation** — nesting, co-location, shortcuts, or path ancestry must not create canonical business/information relationships.
17. **Portability structure** — an EIOS export materialization preserves `manifest.json`, `metadata/`, `relationships/`, `permissions/`, `governance/`, and `content/binaries/` without confusing that package with the enterprise business folder hierarchy.
18. **Path-independent identity** — moving or renaming a provider-native projection leaves the canonical `objectUID` unchanged.
19. **Document-number non-reuse** — file/folder operations must never recycle an issued `enterpriseDocumentNo`.
20. **Taxonomy authority** — local YAML/navigation labels cannot create, replace, repurpose, or silently supersede canonical EIOS taxonomy terms.

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
```

The conformance suite will be expanded into executable tests before this convention is promoted from draft to frozen v1.0.0.
