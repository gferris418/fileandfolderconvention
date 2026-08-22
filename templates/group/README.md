# Group Template

## Purpose

Use this template as a human-facing navigation projection for information managed at enterprise/group level. The folder root does not create canonical ownership; EIOS `informationScope = GROUP` and related metadata remain authoritative.

```text
[GROUP_CODE]/
├── 01_GOVERNANCE/
├── 02_OPERATIONS/
├── 03_FINANCE_TREASURY/
├── 04_COMMERCIAL/
├── 05_PEOPLE_ADMINISTRATION/
├── 06_KNOWLEDGE/
├── 07_SHARED_SERVICES/
└── 99_ARCHIVE/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_GOVERNANCE` | Group-level strategy, legal/governance, risk, policy, board, corporate-secretarial, and assurance information. |
| `02_OPERATIONS` | Cross-entity operational management, opportunities, projects, procurement, QA/HSE, and operational coordination. |
| `03_FINANCE_TREASURY` | Group-level finance, consolidation, treasury, banking, tax, and reporting support. |
| `04_COMMERCIAL` | Group-wide commercial frameworks, organization/relationship views, pricing, contracts, and market intelligence. |
| `05_PEOPLE_ADMINISTRATION` | Group-wide people governance, workforce administration, competency, recruitment, and people policy. |
| `06_KNOWLEDGE` | Reusable standards, templates, research, technical references, and lessons learned. |
| `07_SHARED_SERVICES` | Common IT, facilities, administration, procurement support, and corporate communications. |
| `99_ARCHIVE` | Closed/historical group-level navigation only; not a canonical records or retention state. |

Detailed contents and boundaries are normative in `standard/v1.0/15-purpose-register.md`.
