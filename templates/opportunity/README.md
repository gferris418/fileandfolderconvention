# Opportunity / Tender Template

## Purpose

Use this template for pre-award opportunity/tender information from source receipt through requirement analysis, bid development, approval, submission, clarification, award transition, and closure. The folder structure supports navigation only; canonical Opportunity identity, status, relationships, and award outcome remain EIOS data.

```text
[OPPORTUNITY_CODE]_[SHORT_NAME]/
├── 01_SOURCE_RFP/
├── 02_REQUIREMENTS/
├── 03_WORKING/
├── 04_INTERNAL_APPROVAL/
├── 05_FINAL_SUBMISSION/
├── 06_CLARIFICATIONS/
├── 07_AWARD_CONTRACT/
└── 99_CLOSED/
```

## Purpose of each node

| Node | Purpose |
|---|---|
| `01_SOURCE_RFP` | Preserve the authoritative tender/RFP/RFQ package and formal amendments exactly as received. |
| `02_REQUIREMENTS` | Translate source material into structured requirements, compliance obligations, qualification criteria, and submission checklists. |
| `03_WORKING` | Develop technical, commercial, pricing, partner/supplier, and narrative bid content before approval. |
| `04_INTERNAL_APPROVAL` | Preserve bid/no-bid, risk, pricing, technical, commercial, legal/compliance, and submission authorization evidence. |
| `05_FINAL_SUBMISSION` | Preserve the exact external submission package and evidence of its transmission. |
| `06_CLARIFICATIONS` | Manage post-submission questions, responses, negotiations, revised offers, and clarification exchanges. |
| `07_AWARD_CONTRACT` | Manage award evidence, final negotiated terms, contract formation, and handoff to Project/Contract execution. |
| `99_CLOSED` | Provide a navigational endpoint for lost, cancelled, withdrawn, expired, or otherwise closed opportunities. |

For complete contents and boundary rules, see `standard/v1.0/06-opportunity-tender-structure.md` and `standard/v1.0/15-purpose-register.md`.
