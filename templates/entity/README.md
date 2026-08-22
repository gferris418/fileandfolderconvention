# Entity Template

## Purpose

Use this template as a human-facing navigation projection for information whose strongest canonical context is a specific legal/business Entity. The canonical Entity object remains authoritative for legal identity, entity type, registrations, jurisdictional information, currency, status, and relationships.

```text
[ENTITY_CODE]_[SHORT_NAME]/
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
| `01_GOVERNANCE` | Entity-level statutory governance, legal, risk/compliance, policy, board/management, and audit information. |
| `02_OPERATIONS` | Entity-level opportunities, projects, procurement, QA/HSE, and operational management. |
| `03_FINANCE_TREASURY` | Entity-specific accounting support, receivables/payables, tax, treasury, banking, audit, and reporting. |
| `04_COMMERCIAL` | Entity-specific commercial relationships, agreements, pricing, sales contracts, and market-facing information. |
| `05_PEOPLE_ADMINISTRATION` | Entity workforce administration, recruitment, employee records support, training, and people policy. |
| `06_KNOWLEDGE` | Entity-managed reusable standards, templates, technical references, lessons learned, and research. |
| `07_SHARED_SERVICES` | Entity-level IT, facilities, administration, procurement support, and communications. |
| `99_ARCHIVE` | Closed/historical Entity navigation only; it does not set Entity status, record status, retention, or disposition. |

## Boundary

The folder hierarchy must not be used to infer legal ownership of content when canonical `informationScope` or `businessContext` says otherwise. Cross-Entity projects and contracts remain represented through explicit EIOS relationships rather than duplicated folder roots.

Detailed contents and boundaries are normative in `standard/v1.0/15-purpose-register.md`.
