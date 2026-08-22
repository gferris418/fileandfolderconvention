# EIOS File & Folder Convention

**Version:** 1.0.0-draft.3  
**Status:** Working Standard — CIM-aligned, purpose-defined  
**Relationship to EIOS:** Human-facing information organization and presentation standard. It does **not** modify EIOS Core Architecture or EIOS-CIM.

## Purpose

This repository defines a provider-neutral convention for organizing enterprise information into logical spaces, folders, business-readable file names, reusable templates, provider projections, and portability-aware views.

The convention is based on strict separation of concerns:

- **Canonical identity** is owned by EIOS.
- **Enterprise document numbering** is a controlled business identifier.
- **File names and folder paths** are human-facing projections and may change without changing canonical identity.
- **Information scope and business context** are canonical metadata, not directory inference.
- **Security, retention, legal hold, records status, data residency, lifecycle, relationships, lineage, authoritative-copy status, and authorization** are governed through canonical metadata and policy.
- **EIOS information is not file-only**: messages, datasets, formal records, media, and packages may remain in provider-native repositories or virtual projections.
- **Provider mappings** translate the logical convention into Microsoft, Google, Oracle, Box, OpenText, S3/blob, or other native structures without changing EIOS semantics.

## Purpose-first rule

> No structural item exists merely because its name sounds useful. Every information space, folder, template node, and controlled view must have a defined business purpose and boundary.

A conforming structural item must answer:

```text
WHY does it exist?
WHAT belongs there?
WHAT does not belong there?
WHICH business context does it support?
WHO governs any local exception/addition?
```

The complete normative definitions are in [`standard/v1.0/15-purpose-register.md`](standard/v1.0/15-purpose-register.md). If two sibling folders cannot be distinguished by materially different purposes, the design should be consolidated or replaced by metadata/views rather than preserved as ambiguous parallel folders.

## Core EIOS separation rule

> Folders organize information for people; they do not define canonical identity, governance, authorization, lifecycle, relationships, or repository authority.

Therefore:

```text
folder path != objectUID
file name   != document identity
folder      != informationScope
folder      != retention/legal hold/record status
folder      != authorization
folder      != repository binding role
folder tree != canonical relationship graph
```

## CIM alignment

The standard explicitly supports all seven EIOS information scopes:

```text
GROUP
ENTITY
OPPORTUNITY
PROJECT
CONTRACT
FUNCTION
EXTERNAL
```

See [`standard/v1.0/README.md`](standard/v1.0/README.md), [`standard/v1.0/11-eios-cim-alignment.md`](standard/v1.0/11-eios-cim-alignment.md), [`standard/v1.0/12-repository-projection-and-bindings.md`](standard/v1.0/12-repository-projection-and-bindings.md), [`standard/v1.0/13-portability-export-structure.md`](standard/v1.0/13-portability-export-structure.md), and [`standard/v1.0/15-purpose-register.md`](standard/v1.0/15-purpose-register.md).

## Repository layout and the purpose of each area

- [`standard/v1.0/`](standard/v1.0/) — **normative rules**: defines what the convention means and the boundaries implementations must preserve.
- [`templates/`](templates/) — **reusable navigation blueprints**: projects the standard into Group, Entity, Opportunity, Project, Contract, Function, and External-Organization workspaces without creating canonical identity.
- [`taxonomy/`](taxonomy/) — **navigation/naming crosswalks**: provides local controlled labels used by this convention; it is **not** the authoritative EIOS Taxonomy Registry.
- [`examples/`](examples/) — **illustrative material**: shows how the rules look in generic scenarios without becoming normative business data.
- [`conformance/`](conformance/) — **verification rules/fixtures**: proves that an implementation preserves purpose, naming, scope, governance, and provider-neutral semantics.
- [`provider-mappings/`](provider-mappings/) — **provider implementation profiles**: describes how the logical convention can be projected into native platforms while remaining subordinate to EIOS policy and repository capability.
- [`CHANGELOG.md`](CHANGELOG.md) — **change provenance**: records substantive changes to the convention over time.
- [`LICENSE`](LICENSE) — **legal reuse terms**: defines the legal conditions under which repository content may be used and redistributed.

## Source alignment precedence

When historical CIM documents differ, this working draft follows the latest corrected EIOS-CIM v1.0.0 RC3 schema package for implementation semantics while preserving the formally frozen EIOS architecture/baseline boundary. This repository does not rewrite or amend the CIM.

## Versioning

This convention is independently versioned from EIOS-CIM. Changes to this repository must never silently modify canonical EIOS semantics.
