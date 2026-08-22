# 08 — Finance & Treasury Structure

Recommended structure:

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

## Principles

- The ERP/accounting platform remains the accounting system of record where designated.
- EIOS organizes documentary evidence, canonical metadata, relationships, and governance around accounting events.
- Bank-account, tax, payroll, and payment information may require restricted access independent of folder inheritance.
- Intercompany documentation should reference the participating canonical Entity objects and relevant Project/Contract where applicable.
- Currency, jurisdiction, entity, and transaction role should be metadata dimensions rather than inferred from filenames alone.
