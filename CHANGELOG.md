# Changelog

All notable changes to the EIOS File & Folder Convention are recorded here.

## [1.0.0-draft.2] - 2026-08-22

### Added
- Explicit alignment to all seven EIOS information scopes: Group, Entity, Opportunity, Project, Contract, Function, and External.
- Function and External-Organization templates.
- EIOS-CIM alignment guidance covering business context, non-file information objects, canonical document/revision semantics, relationships, and packages.
- Repository projection/binding guidance covering binding roles, write modes, synchronization/conflicts, authoritative-copy behavior, and provider capability declarations.
- EIOS portability/export directory structure and separation from business folders.
- Taxonomy authority guidance plus information-scope and repository-binding crosswalks.
- Expanded conformance catalogue covering scope, governance, repository, relationship, non-file-object, taxonomy, and portability separation.

### Changed
- Commercial navigation now uses one `ORGANIZATIONS` root plus relationship views rather than separate customer/supplier master roots.
- Principles expanded to explicitly prohibit inference of information scope, lifecycle, relationships, repository authority, and non-file semantics from paths.
- Project and Contract templates now preserve canonical relationship/party semantics.
- Records/archive guidance now covers CanonicalRecord declaration, retention triggers, legal hold, immutability, disposition, and data residency.
- Provider mapping contract now requires capability honesty and enforces the no-authorization-broadening invariant.
- Presentation lifecycle crosswalk now lists the canonical revision lifecycle states without treating them as folder states.

## [1.0.0-draft] - 2026-08-22

### Added
- Core principles and separation between canonical identity and storage projection.
- Logical enterprise information spaces.
- Folder naming and file naming rules.
- Enterprise document numbering guidance.
- Project, opportunity/tender, governance, finance, and archive structures.
- Group, entity, opportunity, project, and contract templates.
- Initial controlled vocabularies.
- Generic provider-mapping contract plus Microsoft, Google, and Oracle placeholders.
- Initial conformance rules and examples.
