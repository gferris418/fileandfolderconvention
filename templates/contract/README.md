# Contract Template

## Purpose

Use this template to organize information whose strongest business context is a canonical EIOS Contract. It separates formation, execution, change, obligation, payment, correspondence, dispute, and closeout purposes so the contract file remains understandable across its full lifecycle.

```text
[CONTRACT_CODE]_[SHORT_TITLE]/
├── 01_FORMATION/
├── 02_SIGNED_AGREEMENT/
├── 03_AMENDMENTS_CHANGE_CONTROL/
├── 04_OBLIGATIONS_DELIVERABLES/
├── 05_COMMERCIAL_PAYMENT/
├── 06_CORRESPONDENCE/
├── 07_CLAIMS_DISPUTES/
├── 08_CLOSEOUT/
└── 99_ARCHIVE/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_FORMATION` | Preserve negotiation, due diligence, approvals, and pre-signature contract-formation evidence. |
| `02_SIGNED_AGREEMENT` | Preserve the executed contractual instrument, schedules/appendices, and signature/execution evidence. |
| `03_AMENDMENTS_CHANGE_CONTROL` | Manage amendments, variations, change orders, contractual changes, and their approvals. |
| `04_OBLIGATIONS_DELIVERABLES` | Manage obligations, deliverable registers, milestones, compliance evidence, and acceptance obligations. |
| `05_COMMERCIAL_PAYMENT` | Organize price, invoicing, payment, securities, commercial settlement, and related contract-level evidence. |
| `06_CORRESPONDENCE` | Preserve formal contractual notices, letters, material messages, and transmittals. |
| `07_CLAIMS_DISPUTES` | Manage claims, notices, substantiation, disputes, negotiation, and resolution evidence. |
| `08_CLOSEOUT` | Manage completion, final account, release, expiry/termination, and contractual closeout evidence. |
| `99_ARCHIVE` | Provide closed/historical contract navigation only; not a canonical status, retention, or disposition declaration. |

## Canonical boundary

Contract folders are navigational projections. The canonical Contract remains authoritative for contract number/title/type/status, parties and party roles, effective/expiry dates, governing law, and relationships to Projects, Opportunities, Organizations, and Entities.

A folder under one party's name does not make that party the buyer, seller, partner, subcontractor, consultant, or other contractual role. Role and party identity must come from canonical metadata.

Contract closeout/archive movement does not by itself establish completion/termination, start a retention clock, authorize disposition, or change repository binding role.

For full typical-content and exclusion/boundary definitions, see `standard/v1.0/15-purpose-register.md`.
