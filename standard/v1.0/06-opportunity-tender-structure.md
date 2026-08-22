# 06 — Opportunity and Tender Structure

## 1. Purpose of the opportunity structure

The Opportunity/Tender structure provides a controlled human-facing workspace for pre-award work from receipt of the customer source package through requirement analysis, bid development, internal authorization, submission, clarification, award, and closure.

The folder root does not create or change the canonical Opportunity. Opportunity identity, status, customer/counterparty relationships, submissions/packages, award outcome, Contract creation, and Project creation remain explicit EIOS data and relationships.

## 2. Normative template

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

## 3. Purpose and boundary of every folder

### `01_SOURCE_RFP`
**Purpose:** Preserve the authoritative tender/RFP/RFQ package and formal instructions exactly as received from the issuing party.

**Typical contents:** RFP/RFQ/tender documents, specifications, schedules, forms, customer attachments, formal amendments/addenda, official instructions, issued Q&A, portal-download evidence.

**Boundary:** Internal interpretations, marked-up working copies, compliance matrices, and draft responses belong in later working folders. Source material should not be overwritten to reflect internal conclusions.

### `02_REQUIREMENTS`
**Purpose:** Convert the source package into a structured understanding of what must be satisfied, proven, submitted, or clarified.

**Typical contents:** Compliance matrices, requirement registers, qualification criteria, mandatory-document lists, submission checklists, clarification questions, controlled interpretations, responsibility matrices.

**Boundary:** Customer source files remain in `01_SOURCE_RFP`; actual response drafting, costing, and solution development belong in `03_WORKING`.

### `03_WORKING`
**Purpose:** Develop the technical, commercial, financial, partner/supplier, and narrative content required to prepare the bid or proposal.

**Typical contents:** Draft technical responses, pricing/costing models, solution designs, schedules, supplier/partner inputs, internal analyses, draft forms, draft presentations, working calculations.

**Boundary:** This is not proof of internal approval or external submission. Approved decision evidence belongs in `04_INTERNAL_APPROVAL`; exact submitted artifacts belong in `05_FINAL_SUBMISSION`.

### `04_INTERNAL_APPROVAL`
**Purpose:** Preserve the enterprise decision and authorization evidence required before an external commitment or submission is made.

**Typical contents:** Bid/no-bid approvals, commercial approvals, technical approvals, risk reviews, legal/compliance reviews, pricing approvals, authorization records, management sign-off.

**Boundary:** Customer-facing bid artifacts belong in `05_FINAL_SUBMISSION`; ongoing working drafts remain in `03_WORKING`. A file merely placed here is not automatically approved unless the approval evidence/metadata says so.

### `05_FINAL_SUBMISSION`
**Purpose:** Preserve the exact package that was actually submitted externally and the evidence proving when/how it was transmitted.

**Typical contents:** Final submitted documents, submission manifest, transmittal, portal receipt, email submission evidence, courier evidence, checksums/digests where used, signed forms.

**Boundary:** Physical folder membership does not define an EIOS `CanonicalPackage`. Package identity and `memberObjectRefs` remain canonical. Drafts and superseded working files do not belong in this folder merely because they contributed to the submission.

### `06_CLARIFICATIONS`
**Purpose:** Manage the controlled post-submission exchange used to clarify, negotiate, revise, or finalize the offer.

**Typical contents:** Clarification requests, responses, negotiation records, revised commercial/technical offers, BAFO/final-offer material, meeting records, post-bid queries.

**Boundary:** Unapproved internal drafts remain working material. When a clarification results in a formal revised submission, preserve the submission/package/revision lineage rather than replacing the previous submission.

### `07_AWARD_CONTRACT`
**Purpose:** Manage the transition from opportunity to awarded business, contract formation, and handoff into execution.

**Typical contents:** Award notice, letter of intent, negotiated final terms, contract-formation evidence, execution approvals, signed-agreement handoff, project initiation/handover checklist.

**Boundary:** Ongoing execution belongs in the dedicated Project and Contract structures once those canonical objects exist. A move into this folder does not itself constitute the award event or create the Contract/Project.

### `99_CLOSED`
**Purpose:** Provide a clear human-facing endpoint for an opportunity that is lost, cancelled, withdrawn, expired, or otherwise no longer active.

**Typical contents:** Closure notice, loss/cancellation evidence, final status summary, debrief, loss review, lessons identified for promotion.

**Boundary:** The path does not set canonical Opportunity status, retention, record declaration, disposition, or archive eligibility.

## 4. Canonical package rule

A formal submission/deliverable may be represented by an EIOS `CanonicalPackage`. `05_FINAL_SUBMISSION` may provide a convenient physical projection, but package identity and membership are defined by the canonical package and its `memberObjectRefs`, not by whichever files happen to reside in the folder at a given time.

A revised submission should preserve document/revision/package lineage rather than relying on folder copies named `FINAL`, `FINAL2`, or similar uncontrolled labels.

## 5. Award transition

Winning an opportunity should create/link the appropriate Contract and Project canonical objects and relationships rather than treating a move into `07_AWARD_CONTRACT`, a rename, or a folder-status change as the award event itself.

Opportunity closure must likewise remain canonical; `99_CLOSED` is only the navigational projection.

The cross-template purpose definitions are maintained in [`15-purpose-register.md`](15-purpose-register.md).
