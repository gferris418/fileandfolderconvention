# External Organization Template

Use this template when EIOS `informationScope = EXTERNAL` and canonical `businessContext.counterpartyRef` identifies the third-party `Organization`.

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

## Multi-role rule

A canonical Organization may simultaneously or sequentially act as customer, supplier, partner, regulator, subcontractor, consultant, or another business role. Do not create separate canonical organization identities merely because different role views are useful.

Role-specific navigation may be implemented as metadata views, shortcuts, links, or governed provider-native views. Canonical `OrganizationRelationship` objects remain authoritative for role, scope, effective dates, and related Entity/Opportunity/Project/Contract context.
