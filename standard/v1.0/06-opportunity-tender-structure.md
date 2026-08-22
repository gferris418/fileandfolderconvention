# 06 — Opportunity and Tender Structure

## Normative template

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

## Folder intent

- `01_SOURCE_RFP` — customer-issued tender/RFP/RFQ material and formal amendments.
- `02_REQUIREMENTS` — requirement extraction, compliance matrices, qualification criteria, and controlled interpretations.
- `03_WORKING` — drafts, costing inputs, technical development, partner/supplier inputs, and working analysis.
- `04_INTERNAL_APPROVAL` — bid/no-bid, internal commercial/technical approvals, risk review, and submission authorization.
- `05_FINAL_SUBMISSION` — exact submitted package and submission evidence.
- `06_CLARIFICATIONS` — post-submission questions, responses, negotiations, and revisions.
- `07_AWARD_CONTRACT` — award notice, final negotiated documents, contract formation, and handoff to project execution.
- `99_CLOSED` — lost, cancelled, expired, or completed opportunity projection.

Winning an opportunity should create/link the appropriate Contract and Project canonical objects rather than treating folder movement as the business event itself.
