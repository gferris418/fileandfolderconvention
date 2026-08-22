# 11 — EIOS-CIM Alignment

## 1. Purpose

This convention is a human-facing projection of EIOS information. It does not replace the EIOS Canonical Information Model (CIM). Where this standard refers to scope, identity, lifecycle, relationship, classification, repository placement, or governance, the canonical EIOS object remains authoritative.

## 2. Seven information scopes

EIOS information objects may be managed at seven scopes. A conforming file/folder implementation must be capable of presenting all seven without inventing new canonical semantics.

| EIOS informationScope | Required canonical context | Recommended human projection |
|---|---|---|
| `GROUP` | Group-level context | Group template / enterprise root |
| `ENTITY` | `owningEntityRef` | Entity template |
| `OPPORTUNITY` | `opportunityRef` | Opportunity/tender template |
| `PROJECT` | `projectRef` | Project template |
| `CONTRACT` | `contractRef` | Contract template |
| `FUNCTION` | `functionCode` | Function template |
| `EXTERNAL` | `counterpartyRef` | External-organization template |

A path can suggest a convenient scope to users, but it never establishes `informationScope` or satisfies a missing canonical business context.

## 3. Business objects are not folder identities

The CIM distinguishes internal `Entity` objects from third-party `Organization` objects. A third-party organization can have multiple contextual roles through `OrganizationRelationship`; it must not be duplicated into separate canonical customer, supplier, partner, regulator, or subcontractor masters merely because different navigational views are useful.

Likewise, participation of multiple entities in a project is represented by canonical project/entity relationships. Folder names must not become the authoritative statement of owning, billing, execution, procurement, receiving, sponsorship, or other participation roles.

Contract parties, roles, governing law, effective dates, project ownership, customer relationships, and opportunity status remain canonical metadata.

## 4. Information is broader than files

The CIM manages multiple information-object forms:

- `CanonicalDocument` — logical document identity;
- `CanonicalRevision` — immutable document revision/content state;
- `CanonicalMessage` — email, chat, or other communication;
- `CanonicalDataset` — structured data collection or feed;
- `CanonicalRecord` — formal record declaration;
- `CanonicalMedia` — image, video, audio, or other rich media;
- `CanonicalPackage` — composite deliverable/submission package.

Not every canonical object needs a physical folder or file. Messages may remain in messaging systems, datasets in databases or data platforms, media in object/content stores, and packages may be virtual compositions. The file/folder convention applies only where a provider exposes a navigable projection.

## 5. Document semantics

For controlled documents:

```text
objectUID              canonical machine identity
enterpriseDocumentNo   immutable human business identifier (when issued)
documentTypeCode       taxonomy-controlled document semantics
disciplineCode         taxonomy-controlled discipline
currentRevisionRef      canonical current revision relationship
filename                mutable human-facing display projection
```

The filename must not become the source of truth for document type, discipline, current revision, or identity.

## 6. Revision lifecycle

Canonical revision lifecycle states are:

```text
DRAFT
WORKING
REVIEW
AUTHORIZED
PUBLISHED
SUPERSEDED
WITHDRAWN
RECORD
DISPOSED
```

Folder states such as `ACTIVE`, `CLOSEOUT`, `CLOSED`, or `ARCHIVED` are presentation states only. A folder move must not directly rewrite canonical revision lifecycle state.

## 7. Relationships and packages

Canonical relationships connect objects independently of directory proximity. Folder co-location must not be interpreted as `BELONGS-TO`, `REFERENCES`, `DERIVED-FROM`, `SUPERSEDES`, `DELIVERABLE-OF`, `GOVERNED-BY`, or another relationship unless the relationship is represented canonically.

A `CanonicalPackage` may be displayed as a submission/deliverable folder, but package membership is defined by canonical member references, not by whichever files happen to be physically present in that folder.

## 8. Taxonomy authority

The YAML files in this repository are navigation and naming seeds. They are not the enterprise taxonomy authority. Controlled EIOS terms are registry-managed and may include document type, discipline, handling classification, data category, jurisdiction, country, currency, relationship type, record class, retention class, and other governed taxonomies.

A local short code such as `ENG` or `DRG` must map unambiguously to an approved canonical taxonomy term when used as controlled metadata.
