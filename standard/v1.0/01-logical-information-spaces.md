# 01 — Logical Information Spaces

## 1. Enterprise root

The recommended enterprise root is:

```text
ENTERPRISE_INFORMATION/
├── 01_GOVERNANCE/
├── 02_OPERATIONS/
├── 03_FINANCE_TREASURY/
├── 04_COMMERCIAL/
├── 05_PEOPLE_ADMINISTRATION/
├── 06_KNOWLEDGE/
├── 07_SHARED_SERVICES/
└── 99_ARCHIVE/
```

These are logical spaces. A provider may represent them as sites, libraries, shared drives, workspaces, repositories, folders, buckets, views, or another suitable native construct.

They do not replace the seven EIOS `informationScope` values. Group, Entity, Opportunity, Project, Contract, Function, and External scope are canonical metadata/context dimensions that may cut across these navigational spaces.

## 2. Governance

```text
01_GOVERNANCE/
├── 01_STRATEGY/
├── 02_CORPORATE_SECRETARIAL/
├── 03_LEGAL/
├── 04_RISK_COMPLIANCE/
├── 05_POLICIES_PROCEDURES/
├── 06_INTERNAL_AUDIT/
└── 07_BOARD_MANAGEMENT/
```

## 3. Operations

```text
02_OPERATIONS/
├── 01_BD_TENDERS/
├── 02_PROJECT_EXECUTION/
├── 03_PROCUREMENT_SUPPLY_CHAIN/
├── 04_QA_QC_HSE/
└── 05_OPERATIONS_MANAGEMENT/
```

## 4. Finance and treasury

```text
03_FINANCE_TREASURY/
├── 01_ACCOUNTING/
├── 02_RECEIVABLES/
├── 03_PAYABLES/
├── 04_PROJECT_FINANCE/
├── 05_TAX/
├── 06_TREASURY/
├── 07_BANK_ACCOUNTS/
├── 08_LETTERS_OF_CREDIT/
├── 09_BANK_GUARANTEES/
├── 10_AUDIT/
└── 11_FINANCIAL_REPORTING/
```

## 5. Commercial

```text
04_COMMERCIAL/
├── 01_ORGANIZATIONS/
├── 02_RELATIONSHIP_VIEWS/
├── 03_FRAMEWORK_AGREEMENTS/
├── 04_PRICING_COSTING/
├── 05_SALES_CONTRACTS/
└── 06_MARKET_INTELLIGENCE/
```

### Organization neutrality

`01_ORGANIZATIONS` is the preferred master navigational root for third-party organizations. EIOS uses one canonical Organization identity with contextual `OrganizationRelationship` roles. Do not create separate canonical customer, supplier, partner, regulator, or subcontractor masters merely because those views are useful.

`02_RELATIONSHIP_VIEWS` may contain metadata-driven views, shortcuts, indexes, or provider-native filtered views such as Customers, Suppliers, Partners, Regulators, or Subcontractors. Such views should avoid uncontrolled duplicate content.

## 6. People administration

```text
05_PEOPLE_ADMINISTRATION/
├── 01_ORGANIZATION/
├── 02_RECRUITMENT/
├── 03_EMPLOYEE_ADMINISTRATION/
├── 04_TRAINING_COMPETENCY/
└── 05_POLICIES/
```

Sensitive personal information remains subject to EIOS security and data-category policy. Folder placement alone never grants access.

## 7. Knowledge

```text
06_KNOWLEDGE/
├── 01_STANDARDS/
├── 02_TEMPLATES/
├── 03_TECHNICAL_REFERENCES/
├── 04_LESSONS_LEARNED/
└── 05_RESEARCH/
```

## 8. Shared services

```text
07_SHARED_SERVICES/
├── 01_IT/
├── 02_FACILITIES/
├── 03_ADMINISTRATION/
├── 04_PROCUREMENT_SUPPORT/
└── 05_CORPORATE_COMMUNICATIONS/
```

## 9. Archive

`99_ARCHIVE` is a human-facing organizational location for closed or historical material. It must not be treated as proof that an object is a formal record, under retention, immutable, on legal hold, authoritative, synchronized, or eligible for disposition.
