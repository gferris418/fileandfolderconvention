# Function Template

Use this template when EIOS `informationScope = FUNCTION` and canonical `businessContext.functionCode` identifies the governing business function.

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

The folder name is a navigational projection of the function. The canonical `functionCode` remains authoritative. A `99_ARCHIVE` move does not change lifecycle, record, retention, or disposition state.
