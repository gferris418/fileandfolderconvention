# Changelog

All notable changes to the EIOS File & Folder Convention are recorded here.

## [1.0.0-draft.3] - 2026-08-22

### Added
- Normative `15-purpose-register.md` defining **purpose, typical contents, and boundary/exclusions for every current structural node**.
- Purpose-first principle requiring every information space, folder, template node, controlled view, and local structural addition to have a documented business reason.
- Standard index explaining the purpose of every normative specification document.
- Template catalogue explaining the purpose of all seven information-scope templates.
- Examples index explaining why each example exists and its non-normative boundary.
- Valid and invalid conformance fixtures for local purpose registration.
- Purpose and boundary definitions for every information-scope crosswalk, repository-binding role, presentation/canonical lifecycle state, document type, discipline, and business-function code.

### Changed
- Logical information spaces now state the purpose of each enterprise domain and direct users to full boundary definitions.
- Project, Opportunity/Tender, Governance, and Finance/Treasury standards now describe why every folder exists, what belongs there, and what should be routed elsewhere.
- Group, Entity, Project, Opportunity, Contract, Function, and External-Organization templates are now self-describing rather than label-only folder trees.
- Folder naming rules now reject structural folders that lack a registered purpose/boundary and explicitly discourage undefined catch-all categories.
- File naming and enterprise document numbering now explain the purpose of every naming/numbering segment.
- Taxonomy crosswalk rules now require semantic purpose/usage definitions rather than code + label alone.
- Provider-mapping declaration items now each state why the capability/behavior must be documented.
- Microsoft, Google, and Oracle placeholder profiles now state their implementation purpose and the questions each future mapping must answer.
- Exception governance now requires purpose evidence for every local structural addition.
- Conformance expanded with purpose completeness, purpose quality, sibling-purpose uniqueness, and local-addition registration tests.

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
