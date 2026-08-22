# 07 — Governance Structure

## 1. Purpose of the governance structure

The Governance structure organizes information used to direct, control, oversee, assure, and legally govern the enterprise. Each node represents a distinct governance purpose and should not be used as a general repository for operational work.

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

## 2. Purpose and boundary of every folder

### `01_STRATEGY`
**Purpose:** Preserve approved strategic direction and the analysis used to shape enterprise priorities.

**Typical contents:** Strategic plans, objectives, initiatives, portfolio priorities, strategic reviews, approved transformation roadmaps.

**Boundary:** Routine operating plans and project schedules belong in Operations/Project structures. A strategy document is not automatically board-approved merely because it resides here.

### `02_CORPORATE_SECRETARIAL`
**Purpose:** Support statutory corporate administration, corporate authorities, entity governance, and formal company records.

**Typical contents:** Resolutions, statutory filings, corporate registers, powers/authorities, entity-maintenance evidence, annual corporate calendars.

**Boundary:** Legal advice belongs in `03_LEGAL`; board/committee packs belong in `07_BOARD_MANAGEMENT` where that is their primary purpose. Formal record status remains canonical.

### `03_LEGAL`
**Purpose:** Organize legal advice, legal matters, disputes, legal research, and privileged/legal analysis.

**Typical contents:** Legal opinions, matter files, dispute support, legal correspondence, legal research, litigation support, settlement/legal-analysis material.

**Boundary:** Executed commercial contracts are governed through the Contract/Commercial structures; legal hold is an EIOS governance object and cannot be inferred from a `LEGAL` path.

### `04_RISK_COMPLIANCE`
**Purpose:** Manage enterprise risk, regulatory/compliance obligations, control assessments, and compliance evidence.

**Typical contents:** Risk registers, risk assessments, control matrices, regulatory assessments, compliance monitoring, screening evidence, control testing, remediation tracking.

**Boundary:** Independent audit work belongs in `06_INTERNAL_AUDIT`; compliance conclusions/status must be supported by governed evidence/metadata rather than the folder label.

### `05_POLICIES_PROCEDURES`
**Purpose:** Govern controlled enterprise policies, standards, procedures, work instructions, and their approved lifecycle.

**Typical contents:** Policies, procedures, control standards, work instructions, approval evidence, effective-date records, supersession history.

**Boundary:** Draft analysis and operational records belong with their source process. A filename containing `FINAL` or placement in this folder does not establish approved/published status.

### `06_INTERNAL_AUDIT`
**Purpose:** Preserve independent internal-audit planning, fieldwork, evidence, findings, reporting, and management responses.

**Typical contents:** Audit universe/plans, audit programs, working papers, evidence, findings, reports, management responses, follow-up records.

**Boundary:** Operational QA/QC belongs in Operations; finance/statutory audit support may reside under Finance `10_AUDIT`. Audit access should be controlled independently of folder position where required.

### `07_BOARD_MANAGEMENT`
**Purpose:** Organize governing-body and executive governance materials used for meetings, decisions, approvals, and oversight.

**Typical contents:** Agendas, board/committee packs, minutes, resolutions, decision papers, presentations, action/decision registers.

**Boundary:** Corporate registers and statutory maintenance belong in Corporate Secretarial. Confidentiality, retention, and legal privilege are governed separately by EIOS policy.

## 3. Governance control principles

Governance material frequently has heightened classification, retention, legal-hold, or access requirements. These requirements must be implemented through EIOS policy and provider-native controls; the folder hierarchy is only the navigational projection.

Policies and procedures should use controlled titles, effective dates, status, ownership, and supersession metadata rather than relying on file names such as `final` or `old`.

The cross-template purpose definitions are maintained in [`15-purpose-register.md`](15-purpose-register.md).
