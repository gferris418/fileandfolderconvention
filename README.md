# EIOS File & Folder Convention

**Version:** 1.0.0-draft.2  
**Status:** Working Standard — CIM-aligned  
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

## Core rule

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

The standard now explicitly supports all seven EIOS information scopes:

```text
GROUP
ENTITY
OPPORTUNITY
PROJECT
CONTRACT
FUNCTION
EXTERNAL
```

See [`standard/v1.0/11-eios-cim-alignment.md`](standard/v1.0/11-eios-cim-alignment.md), [`standard/v1.0/12-repository-projection-and-bindings.md`](standard/v1.0/12-repository-projection-and-bindings.md), and [`standard/v1.0/13-portability-export-structure.md`](standard/v1.0/13-portability-export-structure.md).

## Repository layout

- [`standard/v1.0/`](standard/v1.0/) — normative logical convention.
- [`templates/`](templates/) — Group, Entity, Opportunity, Project, Contract, Function, and External-Organization projections.
- [`taxonomy/`](taxonomy/) — naming/navigation crosswalks; **not** the authoritative EIOS Taxonomy Registry.
- [`examples/`](examples/) — generic examples.
- [`conformance/`](conformance/) — required positive/negative conformance classes.
- [`provider-mappings/`](provider-mappings/) — provider-specific implementation profiles that remain subordinate to EIOS policy and repository capability.

## Source alignment precedence

When historical CIM documents differ, this working draft follows the latest corrected EIOS-CIM v1.0.0 RC3 schema package for implementation semantics while preserving the formally frozen EIOS architecture/baseline boundary. This repository does not rewrite or amend the CIM.

## Versioning

This convention is independently versioned from EIOS-CIM. Changes to this repository must never silently modify canonical EIOS semantics.
