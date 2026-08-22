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

## 2. Purpose of each enterprise space

| Space | Primary purpose |
|---|---|
| `01_GOVERNANCE` | Direct, control, oversee, and assure the enterprise through strategy, corporate governance, legal, risk, policy, and audit information. |
| `02_OPERATIONS` | Organize information used to win, plan, execute, control, and close operational work. |
| `03_FINANCE_TREASURY` | Organize evidence and working information supporting accounting, cash, banking, tax, financial control, and reporting. |
| `04_COMMERCIAL` | Organize market-facing and counterparty-related commercial information outside a stronger Opportunity/Project/Contract context. |
| `05_PEOPLE_ADMINISTRATION` | Organize workforce administration, recruitment, competency, and people-policy information. |
| `06_KNOWLEDGE` | Preserve reusable institutional knowledge, standards, templates, research, references, and lessons learned. |
| `07_SHARED_SERVICES` | Organize enterprise-support functions serving multiple business units or scopes. |
| `99_ARCHIVE` | Provide a human-facing historical/closed navigation projection without declaring record, retention, legal-hold, disposition, or repository status. |

The complete purpose, typical contents, and boundary/exclusion definition for **every node listed below** is normative in [`15-purpose-register.md`](15-purpose-register.md). A node must not be implemented based only on its label.

## 3. Governance

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

Each child has a distinct governance purpose: strategic direction, corporate-secretarial administration, legal matters, risk/compliance, controlled policy, independent internal audit, and governing-body management respectively. Detailed boundaries are in the Purpose & Boundary Register.

## 4. Operations

```text
02_OPERATIONS/
├── 01_BD_TENDERS/
├── 02_PROJECT_EXECUTION/
├── 03_PROCUREMENT_SUPPLY_CHAIN/
├── 04_QA_QC_HSE/
└── 05_OPERATIONS_MANAGEMENT/
```

These nodes separate pre-award business development, project delivery, procurement/logistics, quality/safety assurance, and cross-project operations management. Their purpose boundaries prevent project-specific records from becoming mixed with enterprise-level process material.

## 5. Finance and treasury

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

The structure deliberately separates accounting support, incoming/outgoing settlement, project financial control, taxation, liquidity/treasury, bank-account administration, documentary credits, guarantees, finance-audit support, and reporting. Detailed purposes and exclusions are in the Purpose & Boundary Register.

## 6. Commercial

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

`01_ORGANIZATIONS` provides a neutral navigational home/index for third-party organizations. EIOS uses one canonical Organization identity with contextual `OrganizationRelationship` roles. Do not create separate canonical customer, supplier, partner, regulator, or subcontractor masters merely because those views are useful.

`02_RELATIONSHIP_VIEWS` exists specifically to present those contextual roles as views, shortcuts, indexes, or provider-native filters. Its purpose is navigation; it does not create independent identities or role truth.

The remaining nodes separate reusable frameworks, pricing/costing knowledge, customer-facing sales-contract navigation, and market intelligence.

## 7. People administration

```text
05_PEOPLE_ADMINISTRATION/
├── 01_ORGANIZATION/
├── 02_RECRUITMENT/
├── 03_EMPLOYEE_ADMINISTRATION/
├── 04_TRAINING_COMPETENCY/
└── 05_POLICIES/
```

These nodes separate workforce structure, recruitment, employee lifecycle administration, learning/competency, and people-function policy. Sensitive personal information remains subject to EIOS security and data-category policy. Folder placement alone never grants access.

## 8. Knowledge

```text
06_KNOWLEDGE/
├── 01_STANDARDS/
├── 02_TEMPLATES/
├── 03_TECHNICAL_REFERENCES/
├── 04_LESSONS_LEARNED/
└── 05_RESEARCH/
```

The purpose of this space is reuse. Standards define controlled reference requirements; templates provide reusable starting artifacts; technical references provide reusable source material; lessons learned preserve validated improvement knowledge; research contains exploratory study material not yet promoted into a controlled standard/policy/template.

## 9. Shared services

```text
07_SHARED_SERVICES/
├── 01_IT/
├── 02_FACILITIES/
├── 03_ADMINISTRATION/
├── 04_PROCUREMENT_SUPPORT/
└── 05_CORPORATE_COMMUNICATIONS/
```

These nodes separate technology support, premises/facilities, genuinely general administrative service, shared procurement support, and corporate communications. `03_ADMINISTRATION` must not become a `Misc` folder; it is valid only for information whose actual business purpose is administration.

## 10. Archive

`99_ARCHIVE` is a human-facing organizational location for closed or historical material. Its sole purpose is navigation of closed/historical information. It must not be treated as proof that an object is a formal record, under retention, immutable, on legal hold, authoritative, synchronized, or eligible for disposition.
