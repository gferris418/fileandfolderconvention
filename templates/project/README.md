# Project Template

```text
[PROJECT_CODE]_[PROJECT_NAME]/
├── 01_PROJECT_CONTROL/
├── 02_CONTRACT_COMMERCIAL/
├── 03_ENGINEERING/
├── 04_PROCUREMENT_LOGISTICS/
├── 05_SITE_EXECUTION/
├── 06_QA_QC_HSE/
├── 07_FINANCE/
├── 08_CORRESPONDENCE/
├── 09_TRAINING/
├── 10_HANDOVER_CLOSEOUT/
└── 99_ARCHIVE/
```

## Canonical relationship rule

The folder root is a projection of the canonical Project. Project ownership, project manager, start/end dates, participating entities, and participation roles remain EIOS metadata/relationships.

Do not create separate competing project identities or authoritative project roots for each participating entity. Where multiple entities participate, use provider views/shortcuts if helpful while canonical `ProjectEntityRelationship` records remain authoritative.

Project closeout/archive folder movement does not itself change canonical Project status, revision lifecycle, retention trigger, or authoritative repository binding.
