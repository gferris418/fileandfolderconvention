# Project Template

## Purpose

Use this template as the human-facing workspace/view for information whose strongest business context is a canonical EIOS Project. Canonical Project identity, participating Entity roles, linked Contracts, lifecycle, authorization, and repository bindings remain authoritative outside the folder tree.

```text
[PROJECT_CODE]_[PROJECT_NAME]/
├── 01_PROJECT_CONTROL/
├── 02_CONTRACT_COMMERCIAL/
├── 03_ENGINEERING/
├── 04_PROCUREMENT_LOGISTICS/
├── 05_SITE_EXECUTION/
├── 06_QA_QC_HSE/
├── 07_FINANCE/
├── 08_CORRESPONDENCE/
├── 09_TRAINING/
├── 10_HANDOVER_CLOSEOUT/
└── 99_ARCHIVE/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_PROJECT_CONTROL` | Plan, govern, coordinate, monitor, and report the project. |
| `02_CONTRACT_COMMERCIAL` | Manage the contractual/commercial basis, changes, claims, milestones, and commercial obligations. |
| `03_ENGINEERING` | Manage requirements, design, calculations, specifications, technical submittals, reviews, and engineering deliverables. |
| `04_PROCUREMENT_LOGISTICS` | Manage project-specific sourcing, supplier coordination, shipping, customs, logistics, and delivery evidence. |
| `05_SITE_EXECUTION` | Capture physical implementation, installation, field coordination, commissioning execution, and site progress. |
| `06_QA_QC_HSE` | Preserve quality, inspection/testing, non-conformance, safety, environmental, and assurance evidence. |
| `07_FINANCE` | Manage project cost, forecast, billing, payment, reconciliation, and financial-support evidence. |
| `08_CORRESPONDENCE` | Preserve formal/material project communications not better classified by a stronger subject purpose. |
| `09_TRAINING` | Plan, deliver, and evidence project-required training. |
| `10_HANDOVER_CLOSEOUT` | Manage acceptance, punch lists, as-builts, manuals, warranties, final deliverables, and closeout. |
| `99_ARCHIVE` | Provide closed/historical project navigation only; not a record/retention/disposition declaration. |

## Canonical relationship rule

The folder root is a projection of the canonical Project. Project ownership, project manager, start/end dates, participating entities, and participation roles remain EIOS metadata/relationships.

Do not create separate competing project identities or authoritative project roots for each participating entity. Where multiple entities participate, use provider views/shortcuts if helpful while canonical `ProjectEntityRelationship` records remain authoritative.

Project closeout/archive folder movement does not itself change canonical Project status, revision lifecycle, retention trigger, or authoritative repository binding.

For full typical-content and exclusion/boundary definitions, see `standard/v1.0/05-project-structure.md` and `standard/v1.0/15-purpose-register.md`.
