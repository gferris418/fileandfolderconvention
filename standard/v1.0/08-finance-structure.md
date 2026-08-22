# 08 — Finance & Treasury Structure

## 1. Purpose of the finance and treasury structure

The Finance & Treasury structure organizes documentary evidence and working information used to support accounting, receivables, payables, project financial control, tax, liquidity, banking, trade finance, audit, and reporting. It does not replace the ERP, banking platform, or other designated system of record.

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

## 2. Purpose and boundary of every folder

### `01_ACCOUNTING`
**Purpose:** Organize accounting policy support, journal/support documentation, reconciliations, period-close evidence, and accounting control material.

**Typical contents:** Reconciliations, close packs, accounting support, journal evidence, accounting guidance, balance-support schedules.

**Boundary:** Ledger truth remains in the designated ERP/accounting system. Project-specific operational finance evidence may remain in the Project's `07_FINANCE` folder.

### `02_RECEIVABLES`
**Purpose:** Organize billing, collection, receivable monitoring, receipt support, and customer-account evidence.

**Typical contents:** Sales invoices, billing support, aging support, collection correspondence, receipt/payment evidence, credit/debit notes.

**Boundary:** Customer role is a contextual Organization relationship, not a separate master identity. Contract entitlement belongs in Contract/Commercial structures where that context is stronger.

### `03_PAYABLES`
**Purpose:** Organize supplier invoices, payable approval, payment support, reconciliation, and vendor-account evidence.

**Typical contents:** Supplier invoices, approval evidence, payment support, payable reconciliations, statement reconciliations, debit/credit notes.

**Boundary:** Supplier role is contextual; this folder does not create a supplier master. Procurement/receipt evidence remains in Procurement/Project contexts and may be linked.

### `04_PROJECT_FINANCE`
**Purpose:** Consolidate cross-project financial control, portfolio-level project finance, forecasting, and project-margin reporting.

**Typical contents:** Project budgets, consolidated cost reports, forecasts, margin analyses, cash-flow views, portfolio financial dashboards.

**Boundary:** Project-local invoice/payment evidence belongs in the relevant Project `07_FINANCE`; enterprise accounting truth stays in the ERP.

### `05_TAX`
**Purpose:** Organize tax registrations, filings support, tax calculations, tax advice, jurisdictional evidence, and tax authority correspondence.

**Typical contents:** VAT/GST/tax returns support, tax registrations, tax calculations, tax advice, tax authority correspondence, withholding-tax support.

**Boundary:** Entity/jurisdiction are canonical dimensions. Tax-sensitive information may require access restrictions beyond folder inheritance.

### `06_TREASURY`
**Purpose:** Manage liquidity, cash forecasting, funding, FX, treasury controls, and bank relationship activity.

**Typical contents:** Cash forecasts, liquidity reports, funding records, FX support, treasury approvals, bank relationship material, investment/borrowing support.

**Boundary:** Bank-account-specific legal/administrative material belongs in `07_BANK_ACCOUNTS`; trade instruments belong in LC/BG folders below.

### `07_BANK_ACCOUNTS`
**Purpose:** Organize bank-account establishment, mandates, KYC, authorized-signatory evidence, account administration, and bank correspondence.

**Typical contents:** Account-opening documentation, mandates, KYC, signatory records, service agreements, bank correspondence, account administration records.

**Boundary:** Passwords, API secrets, PINs, or credentials must not be stored merely because this folder exists. Security controls remain separate.

### `08_LETTERS_OF_CREDIT`
**Purpose:** Manage documentary-credit issuance, amendment, presentation, discrepancy, negotiation, and settlement evidence.

**Typical contents:** LC applications, issued LCs, amendments, presentation checklists, shipping/document sets, discrepancy notices, bank correspondence, settlement evidence.

**Boundary:** The LC folder does not determine contractual payment entitlement. Underlying Contract, Project, shipment, invoice, and bank relationships remain explicit/canonical.

### `09_BANK_GUARANTEES`
**Purpose:** Manage guarantees, bonds, amendments, claims, expiry, release, and cancellation evidence.

**Typical contents:** Performance guarantees, advance-payment guarantees, warranty bonds, bid bonds, amendments, claims, release/cancellation evidence.

**Boundary:** Guarantee obligations remain linked to the relevant Contract/Project/Organization contexts. A folder name does not establish whether a guarantee is active or expired.

### `10_AUDIT`
**Purpose:** Organize finance-specific statutory/external audit support, PBC evidence, confirmations, and audit-response material.

**Typical contents:** Audit requests, PBC schedules, confirmations, reconciliations, evidence packs, audit queries/responses, statutory audit support.

**Boundary:** Enterprise Internal Audit is governed under `01_GOVERNANCE/06_INTERNAL_AUDIT`; this node is specifically finance/statutory audit support.

### `11_FINANCIAL_REPORTING`
**Purpose:** Organize management, statutory, regulatory, and consolidated financial reporting outputs and their supporting schedules.

**Typical contents:** Financial statements, management reports, consolidation schedules, reporting packs, regulatory reports, period reporting support.

**Boundary:** Source transactions remain in the designated accounting systems. Reports should identify period, Entity, currency, and reporting context through governed metadata where available.

## 3. Finance principles

- The ERP/accounting platform remains the accounting system of record where designated.
- EIOS organizes documentary evidence, canonical metadata, relationships, and governance around accounting events.
- Bank-account, tax, payroll, and payment information may require restricted access independent of folder inheritance.
- Intercompany documentation should reference the participating canonical Entity objects and relevant Project/Contract where applicable.
- Currency, jurisdiction, entity, and transaction role should be metadata dimensions rather than inferred from filenames alone.

The cross-template purpose definitions are maintained in [`15-purpose-register.md`](15-purpose-register.md).
