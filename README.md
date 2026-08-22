# EIOS File & Folder Convention

**Version:** 1.0.0-draft  
**Status:** Working Standard  
**Relationship to EIOS:** Human-facing information organization and presentation standard. It does **not** modify EIOS Core Architecture or EIOS-CIM.

## Purpose

This repository defines a provider-neutral convention for organizing enterprise information into logical spaces, folders, business-readable file names, and reusable templates.

The convention is based on a strict separation of concerns:

- **Canonical identity** is owned by EIOS.
- **Enterprise document numbering** is a controlled business identifier.
- **File names and folder paths** are human-facing projections and may change without changing canonical identity.
- **Security, retention, legal hold, records status, lineage, and authorization** are governed through canonical metadata and policy, not inferred from a folder path.
- **Provider mappings** translate the logical convention into Microsoft, Google, Oracle, Box, OpenText, S3, or other native structures without changing the standard.

## Core rule

> Folders organize information for people; they do not define canonical identity, governance, or authorization.

Therefore:

```text
folder path != objectUID
file name   != document identity
folder      != retention policy
folder      != authorization model
```

## Standard layout

The normative specification is under [`standard/v1.0/`](standard/v1.0/). Reusable folder templates are under [`templates/`](templates/), controlled vocabulary examples under [`taxonomy/`](taxonomy/), examples under [`examples/`](examples/), and provider-specific projections under [`provider-mappings/`](provider-mappings/).

## Versioning

This convention is independently versioned from EIOS-CIM. Changes to this repository must never silently modify canonical EIOS semantics.
