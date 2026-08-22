# Function Template

## Purpose

Use this template when EIOS `informationScope = FUNCTION` and canonical `businessContext.functionCode` identifies the governing business function. It provides a reusable structure for policy, recurring operations, controls, reporting, reference knowledge, and records-support information belonging primarily to that function.

```text
[FUNCTION_CODE]_[FUNCTION_NAME]/
├── 01_POLICIES_PROCEDURES/
├── 02_OPERATIONS/
├── 03_CONTROLS_COMPLIANCE/
├── 04_REPORTING/
├── 05_REFERENCE_KNOWLEDGE/
├── 06_RECORDS_SUPPORT/
└── 99_ARCHIVE/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_POLICIES_PROCEDURES` | Manage function-specific controlled policies, procedures, SOPs, work instructions, and control guidance. |
| `02_OPERATIONS` | Organize recurring function process execution, operational work, and routine outputs. |
| `03_CONTROLS_COMPLIANCE` | Preserve evidence of function controls, compliance checks, exceptions, and remediation. |
| `04_REPORTING` | Organize recurring function KPIs, dashboards, management reports, and period reporting. |
| `05_REFERENCE_KNOWLEDGE` | Preserve reusable function-specific guidance, references, FAQs, and local best practices. |
| `06_RECORDS_SUPPORT` | Manage record inventories, declaration support, transfer/disposition support, and records-governance evidence without declaring the folder itself to be a record. |
| `99_ARCHIVE` | Provide closed/historical function navigation only; not a lifecycle, retention, or disposition declaration. |

## Boundary

The folder name is a navigational projection of the function. The canonical `functionCode` remains authoritative. Projects, Opportunities, Contracts, and External Organizations should use their dedicated scope structures when those contexts are stronger than the function context.

A `99_ARCHIVE` move does not change lifecycle, record, retention, or disposition state.

For full typical-content and exclusion/boundary definitions, see `standard/v1.0/15-purpose-register.md`.
