# External Organization Template

## Purpose

Use this template when EIOS `informationScope = EXTERNAL` and canonical `businessContext.counterpartyRef` identifies the third-party `Organization`. Its purpose is to provide one neutral human-facing navigation root for a counterparty while preserving role neutrality across customer, supplier, partner, regulator, subcontractor, consultant, and other contextual relationships.

```text
[ORG_CODE]_[SHORT_NAME]/
├── 01_PROFILE_DUE_DILIGENCE/
├── 02_RELATIONSHIPS/
├── 03_COMMERCIAL/
├── 04_CONTRACTS/
├── 05_DELIVERABLES/
├── 06_CORRESPONDENCE/
├── 07_COMPLIANCE_EVIDENCE/
└── 99_CLOSED/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_PROFILE_DUE_DILIGENCE` | Organize neutral organization profile, onboarding, qualification, ownership, registration, KYC/KYB, and due-diligence evidence. |
| `02_RELATIONSHIPS` | Present contextual role/relationship views and links to relevant Entities, Opportunities, Projects, and Contracts. |
| `03_COMMERCIAL` | Organize general commercial information with the organization that is not yet better scoped to a specific Opportunity or Contract. |
| `04_CONTRACTS` | Provide navigation to contracts with the organization without creating duplicate uncontrolled contract masters. |
| `05_DELIVERABLES` | Organize generic organization-supplied or organization-facing deliverables not already better scoped to a Project/Contract. |
| `06_CORRESPONDENCE` | Preserve material general correspondence with the organization when no stronger Project/Contract/Opportunity context applies. |
| `07_COMPLIANCE_EVIDENCE` | Organize screening, certification, regulatory, qualification, and compliance evidence without making the folder label the current compliance status. |
| `99_CLOSED` | Provide historical/closed navigation for an inactive relationship context; it does not deactivate or erase the canonical Organization. |

## Multi-role rule

A canonical Organization may simultaneously or sequentially act as customer, supplier, partner, regulator, subcontractor, consultant, or another business role. Do not create separate canonical organization identities merely because different role views are useful.

Role-specific navigation may be implemented as metadata views, shortcuts, links, or governed provider-native views. Canonical `OrganizationRelationship` objects remain authoritative for role, scope, effective dates, and related Entity/Opportunity/Project/Contract context.

For full typical-content and exclusion/boundary definitions, see `standard/v1.0/15-purpose-register.md`.
