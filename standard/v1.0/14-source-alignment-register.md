# 14 — Source Alignment Register

## Purpose

This register records the reconciliation of the EIOS File & Folder Convention against the supplied EIOS-CIM v1.0.0 lineage documents. It exists to prevent the presentation standard from drifting away from canonical semantics.

## Source precedence

Where historical documents differ, the latest corrected RC3 package is used for implementation semantics. Older v1.0.0/RC2 material remains useful for lineage and intent but does not override a later explicit RC3 correction.

This convention does not modify the CIM; it only aligns human-facing projections with it.

## Gap review

| Area reviewed | Gap in initial convention | Resolution in draft.2 |
|---|---|---|
| Information scope | Group/Entity/Opportunity/Project/Contract templates existed, but FUNCTION and EXTERNAL were missing and scope/context rules were implicit | Added seven-scope crosswalk, Function template, External Organization template, and canonical-context rules |
| Organization master | Commercial tree implied separate customer and supplier/partner roots | Replaced with one Organizations master projection plus relationship views; canonical OrganizationRelationship remains authoritative |
| Multi-entity projects | Folder standard did not explicitly protect project/entity participation semantics | Added Project template rules preventing competing project identities and path-derived participation roles |
| Contracts | Party roles, governing-law/status semantics were not explicitly separated from paths | Added canonical party/role/status/governing-law rules to Contract template |
| Information object breadth | Standard was file/document-centric | Added explicit support for messages, datasets, records, media, packages, and provider-native/virtual projections |
| Document/revision model | File naming covered document number/revision but canonical document-vs-revision lifecycle was not explicit | Added document identity/current-revision and canonical revision lifecycle crosswalk |
| Canonical relationships | Nesting/co-location could be misread as a relationship | Explicitly prohibited path-derived relationships; documented relationship semantics |
| Canonical packages | Submission folder existed but package membership semantics were absent | Added CanonicalPackage rule: membership derives from canonical member refs, not folder contents |
| Repository binding | Authoritative/working/published/record-copy/replica/cache/migration roles were absent | Added repository-binding standard, write modes, synchronization/conflicts, and authoritative-copy rule |
| Repository capability | Provider profiles listed only broad capability categories | Expanded mandatory capability matrix for metadata, ACL/sharing, governance, search/events/audit/residency and compensating controls |
| Authorization mapping | No-broadening rule existed generally but was not tied to corrected PermissionBinding behavior | Provider contract now explicitly permits preserve/restrict only; silent broadening prohibited |
| Records | Archive guidance distinguished archive from record but CanonicalRecord declaration model was incomplete | Added record identity/class/declaration/source/digest distinction |
| Retention | Archive was separated from retention, but trigger semantics were missing | Added creation/publication/contract-end/project-end/record-declaration/last-modified/event-based trigger guidance |
| Legal hold / immutability | General prohibition existed but modes/capability relationship were incomplete | Added legal-hold and WORM/compliance/governance-lock distinction and capability requirement |
| Disposition | Archive guidance lacked action range | Added destroy/transfer/review/export-first/permanent-retention separation from folder operations |
| Data residency | Not covered explicitly | Added rule that residency/jurisdiction placement is policy/repository metadata, not a folder label |
| Taxonomy | Seed YAMLs could be mistaken for authority | Added taxonomy authority README, scope/binding crosswalks, and deprecation/supersession rules |
| Portability | No CIM export layout | Added reserved export package structure for manifest, metadata, relationships, permissions, governance, and content binaries |
| Conformance | Initial checks focused mainly on naming/templates | Expanded to 20 semantic separation/provider/portability/taxonomy test classes |

## Non-goals

This reconciliation does not:

- amend EIOS-CIM schemas;
- resolve candidate v1.0.1 CIM errata;
- define provider-specific implementations;
- make folders mandatory for non-file canonical objects;
- turn presentation vocabulary seeds into the canonical EIOS Taxonomy Registry.
