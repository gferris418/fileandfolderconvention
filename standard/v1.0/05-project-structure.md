# 05 — Project Structure

## 1. Purpose of the project structure

The Project structure provides a stable human-facing navigation model for information whose strongest business context is a canonical EIOS Project. It separates project management, contractual, technical, procurement, field, assurance, financial, communication, training, and closeout purposes so users can determine where information belongs without relying on ambiguous catch-all folders.

The folder root does not create the Project. Canonical Project identity, participating Entity relationships, contract links, lifecycle, classification, authorization, and repository bindings remain EIOS-controlled data.

## 2. Normative project template

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

## 3. Purpose and boundary of every folder

### `01_PROJECT_CONTROL`
**Purpose:** Control how the project is planned, governed, monitored, coordinated, and reported.

**Typical contents:** Project charter, execution plan, schedules, work breakdown information, meeting records, action registers, risk/issue registers, progress reports, dashboards, management reviews, decision logs, and project-control registers.

**Boundary:** Detailed engineering belongs in `03_ENGINEERING`; contractual/commercial evidence belongs in `02_CONTRACT_COMMERCIAL`; accounting and invoice support belong in `07_FINANCE`. Project Control coordinates those domains but is not a duplicate repository for them.

### `02_CONTRACT_COMMERCIAL`
**Purpose:** Manage the contractual and commercial basis under which the project is executed.

**Typical contents:** Contract copies/links, amendments, variations, change orders, contractual notices, claims, commercial approvals, milestone obligations, price/payment schedules, commercial negotiations, and contract-performance evidence.

**Boundary:** The canonical Contract object remains authoritative for contract identity, parties, status, and governing metadata. Routine project accounting evidence belongs in `07_FINANCE`; technical deliverables remain in Engineering or Handover as appropriate.

### `03_ENGINEERING`
**Purpose:** Manage the project's technical definition, design development, analysis, review, approval, and engineering deliverables.

**Typical contents:** Requirements, specifications, designs, drawings, calculations, models, datasheets, technical submittals, review comments, design approvals, technical queries, interfaces, and engineering registers.

**Boundary:** Physical installation/commissioning evidence belongs in `05_SITE_EXECUTION`; formal quality inspection records belong in `06_QA_QC_HSE`; generic reusable standards belong under Knowledge rather than being duplicated into every project.

### `04_PROCUREMENT_LOGISTICS`
**Purpose:** Manage project-specific sourcing, purchasing support, supplier coordination, packing, shipping, customs, logistics, and delivery evidence.

**Typical contents:** RFQs, quotations, purchase-support documents, supplier submittals, expediting records, packing lists, bills of lading/airway bills, freight documents, customs records, delivery notes, shipping schedules, and logistics correspondence.

**Boundary:** Enterprise procurement policy and vendor-management processes belong in their enterprise/shared-service locations. Technical evaluation content may be linked to Engineering; financial settlement evidence belongs in Finance.

### `05_SITE_EXECUTION`
**Purpose:** Capture the physical implementation of the project at site, including installation, field coordination, testing/commissioning execution, and day-to-day work evidence.

**Typical contents:** Site plans, method statements, daily reports, installation records, field changes, work-front records, commissioning execution records, progress photographs/media references, site coordination, and completion evidence.

**Boundary:** Formal inspections, test certificates, NCRs, permits, and HSE evidence belong in `06_QA_QC_HSE` when their primary purpose is assurance/compliance. Engineering design authority remains in `03_ENGINEERING`.

### `06_QA_QC_HSE`
**Purpose:** Preserve project assurance evidence demonstrating quality, inspection, testing, health, safety, and environmental control.

**Typical contents:** Inspection and Test Plans, inspection requests, test reports, quality plans, NCRs, corrective actions, permits, safety plans, toolbox/support records, incident records, HSE inspections, and compliance certificates.

**Boundary:** Enterprise QA/HSE standards belong in the enterprise Operations/QA-QC-HSE space. Routine site progress belongs in Site Execution; technical design approval remains in Engineering.

### `07_FINANCE`
**Purpose:** Organize the project-specific financial evidence and controls required to manage cost, billing, payment, forecast, and reconciliation.

**Typical contents:** Project budgets, cost reports, forecasts, invoice support, payment certificates, reconciliations, accrual support, milestone billing evidence, payment tracking, and financial closeout support.

**Boundary:** The designated ERP/accounting platform remains the accounting system of record. Cross-project financial reporting belongs in Finance & Treasury. Contracts and commercial entitlement evidence remain in `02_CONTRACT_COMMERCIAL` even when they support an invoice.

### `08_CORRESPONDENCE`
**Purpose:** Preserve formal and material project communications whose primary value is the communication record rather than a stronger technical/commercial/financial subject classification.

**Typical contents:** Formal letters, notices, transmittals, material email/message records, correspondence registers, meeting communications, and external communication evidence.

**Boundary:** Subject-specific documents should remain in their strongest business folder and be linked/referenced rather than duplicated. Native email/chat repositories may remain authoritative provider locations while EIOS maintains canonical message references.

### `09_TRAINING`
**Purpose:** Manage project-required training from planning through delivery and evidence of completion.

**Typical contents:** Training plans, course outlines, agendas, training materials, attendee lists, attendance records, assessments, certificates, feedback, and completion reports.

**Boundary:** Workforce-wide competency records belong under People Administration when they become employee records. Technical manuals delivered as project handover documents may belong in `10_HANDOVER_CLOSEOUT` with links from Training where useful.

### `10_HANDOVER_CLOSEOUT`
**Purpose:** Manage the formal transition from execution to acceptance, handover, warranty/support, and administrative/contractual completion.

**Typical contents:** Punch lists, acceptance certificates, setting-to-work/completion evidence, as-built documentation, O&M manuals, warranties, final deliverables, handover registers, closeout checklists, final training evidence, final account support, and lessons identified for promotion.

**Boundary:** Moving content here does not automatically make it a record, immutable, disposed, retained, or archived. Those states remain governed by canonical lifecycle/policy. Reusable lessons should be promoted to Knowledge rather than leaving the project as the only copy.

### `99_ARCHIVE`
**Purpose:** Provide a project-local navigational view for closed or historical project information that must remain available for reference.

**Typical contents:** Closed historical working sets, superseded navigation collections, completed project reference material, and links to preserved records.

**Boundary:** `99_ARCHIVE` is not a legal/records status. It does not establish `RECORD`, `DISPOSED`, legal hold, retention, immutability, authoritative-copy status, or disposition eligibility.

## 4. Routing rule

When a project item could reasonably fit two locations, choose the folder whose **purpose best matches why the information was created or must be preserved**. Use metadata, canonical relationships, shortcuts, or references to expose the secondary context rather than maintaining uncontrolled duplicate copies.

The complete normative cross-template purpose definitions are maintained in [`15-purpose-register.md`](15-purpose-register.md).
