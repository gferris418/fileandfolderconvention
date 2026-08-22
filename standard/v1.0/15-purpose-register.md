# 15 — Purpose & Boundary Register

## 1. Normative rule

Every normative information-space, folder, template node, and controlled navigation item in this convention MUST have an explicit business purpose. A label without a defined purpose is not sufficient.

For each item, this register states:

- **Purpose** — why the item exists and what business outcome it supports.
- **Typical contents** — representative information that belongs there.
- **Boundary** — information that should normally be routed elsewhere, and any canonical EIOS semantics that MUST NOT be inferred from the folder.

This register defines navigation intent only. Canonical identity, information scope, relationships, classification, authorization, lifecycle, repository binding, retention, legal hold, disposition, residency, and record declaration remain EIOS-controlled semantics.

---

## 2. Enterprise information spaces

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_GOVERNANCE` | Preserve information used to direct, control, oversee, and assure the enterprise. | Strategy, board, legal, risk, policy, corporate-secretarial, and audit material. | Operational execution belongs under Operations; placement here does not itself create privileged access, retention, or legal-hold status. |
| `02_OPERATIONS` | Organize information produced while winning, planning, executing, controlling, and closing operational work. | Opportunities, projects, procurement, logistics, QA/QC, HSE, operational management. | Enterprise accounting truth remains in the designated finance/ERP systems; canonical Project/Opportunity identity is metadata-driven. |
| `03_FINANCE_TREASURY` | Organize evidence and working information supporting accounting, cash, banking, tax, financial control, and reporting. | Accounting support, receivables, payables, treasury, banking instruments, tax, audits, reports. | This space does not replace the designated ERP/banking system of record or determine access simply through folder inheritance. |
| `04_COMMERCIAL` | Organize market-facing and counterparty-related commercial information that is not already scoped to a specific opportunity, project, or contract. | Organization views, framework agreements, pricing, sales contracts, market intelligence. | Customer/supplier/partner labels are contextual roles, not separate canonical Organization identities. |
| `05_PEOPLE_ADMINISTRATION` | Organize workforce administration, recruitment, competency, and people-policy information. | Recruitment, employment administration, training, organization administration, HR policies. | Sensitive/personal data requires explicit EIOS security and data-category controls; folder placement never grants access. |
| `06_KNOWLEDGE` | Preserve reusable institutional knowledge and controlled reference material. | Standards, templates, research, lessons learned, technical references. | Project deliverables and live working documents remain in their business context until intentionally promoted as reusable knowledge. |
| `07_SHARED_SERVICES` | Organize enterprise-support functions serving multiple business units or scopes. | IT, facilities, administration, procurement support, communications. | Function-specific authoritative systems remain authoritative where designated. |
| `99_ARCHIVE` | Provide a human-facing location/view for closed or historical material. | Closed historical working sets and references retained for navigation. | `ARCHIVE` does not mean formal record, immutable copy, legal hold, retention, disposition eligibility, or authoritative repository role. |

---

## 3. Governance space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_STRATEGY` | Capture approved strategic direction and the analysis supporting it. | Strategic plans, objectives, initiatives, portfolio priorities, approved strategic reviews. | Routine operational plans belong in Operations; board approvals remain separately identifiable where applicable. |
| `02_CORPORATE_SECRETARIAL` | Maintain corporate-governance administration and statutory company records support. | Entity registers, resolutions, statutory filings, corporate authorities, corporate-calendar evidence. | Legal advice belongs in Legal; formal record status is determined canonically, not by this path. |
| `03_LEGAL` | Organize legal advice, matters, agreements support, disputes, and legal analysis. | Legal opinions, matter files, dispute support, legal correspondence, legal research. | Active contracts may be navigated from Contract/Commercial structures; legal hold is a canonical governance object, not a folder state. |
| `04_RISK_COMPLIANCE` | Organize enterprise risk, compliance, control, and regulatory assurance information. | Risk registers, compliance assessments, regulatory evidence, screening evidence, control testing. | Internal Audit retains independent assurance material under `06_INTERNAL_AUDIT`; compliance status must be represented through governed metadata/evidence. |
| `05_POLICIES_PROCEDURES` | Publish and manage controlled enterprise policies, standards, procedures, and work instructions. | Policy documents, procedures, control standards, approved guidance, supersession records. | Draft work may be separated from published controlled material; `final` filenames do not establish approved status. |
| `06_INTERNAL_AUDIT` | Preserve independent internal-audit planning, fieldwork, findings, evidence, and reports. | Audit plans, working papers, findings, management responses, final reports. | Operational QA/QC belongs under Operations; audit evidence may require restricted access independent of path. |
| `07_BOARD_MANAGEMENT` | Organize governing-body and executive governance materials. | Agendas, packs, minutes, resolutions, decision papers, committee materials. | Corporate-secretarial registers remain under Corporate Secretarial where appropriate; sensitivity is policy-driven. |

---

## 4. Operations space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_BD_TENDERS` | Manage business-development opportunities, tenders, bids, and pre-award submissions. | RFP/RFQ sources, requirements, bid working papers, approvals, submissions, clarifications. | Once awarded, project/contract execution is linked canonically and navigated in its dedicated structure rather than continuing indefinitely as tender working material. |
| `02_PROJECT_EXECUTION` | Provide the primary navigation space for active project delivery and closeout. | Project controls, engineering, procurement, site execution, QA/HSE, correspondence, training, handover. | Project identity and participating entities are canonical objects/relationships, not derived from the folder name. |
| `03_PROCUREMENT_SUPPLY_CHAIN` | Organize enterprise or cross-project procurement, supplier coordination, sourcing, and logistics processes. | Sourcing events, purchase support, supplier coordination, logistics planning, delivery evidence. | Project-specific procurement should normally remain within its Project structure while cross-project/master processes reside here. |
| `04_QA_QC_HSE` | Organize enterprise-level quality, inspection, safety, environmental, and assurance frameworks/evidence. | Quality systems, inspection standards, HSE procedures, enterprise registers, assurance reports. | Project-specific inspection/safety records belong within the relevant Project's `06_QA_QC_HSE`. |
| `05_OPERATIONS_MANAGEMENT` | Manage cross-project operational planning, capacity, performance, coordination, and management reporting. | Resource/capacity plans, operations dashboards, coordination records, portfolio operating reviews. | Detailed project records remain in their project roots; strategic portfolio direction belongs in Governance/Strategy. |

---

## 5. Finance & Treasury space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_ACCOUNTING` | Organize accounting policy support, journals/supporting evidence, reconciliations, and close documentation. | Accounting support, reconciliations, close packs, chart/accounting guidance. | Ledger truth remains in the designated ERP/accounting system. |
| `02_RECEIVABLES` | Organize customer billing, collections, receivable support, and related evidence. | Invoices, billing support, aging support, collection correspondence, receipt evidence. | Customer identity is canonical Organization/relationship data; project-specific billing may also be navigated in project finance. |
| `03_PAYABLES` | Organize supplier invoices, payment support, payable reconciliations, and approvals. | Vendor invoices, approval evidence, payment support, reconciliations. | Supplier role does not create a separate canonical Organization identity. |
| `04_PROJECT_FINANCE` | Consolidate cross-project financial control and project-finance reporting. | Project budgets, cost control, forecasts, margin analysis, consolidated project financial reports. | Project-specific documentary evidence may remain under each Project's `07_FINANCE`; this node is for cross-project/finance-function control. |
| `05_TAX` | Organize tax registrations, filings support, calculations, advice, and jurisdictional evidence. | Tax returns support, VAT/GST files, tax correspondence, tax advice, registration evidence. | Legal entity and jurisdiction are canonical dimensions; tax data may require restricted access. |
| `06_TREASURY` | Manage liquidity, cash positioning, funding, FX, treasury controls, and bank relationship support. | Cash forecasts, funding records, FX support, treasury approvals, bank relationship materials. | Bank-account-specific documentation belongs under `07_BANK_ACCOUNTS` when that is the clearer context. |
| `07_BANK_ACCOUNTS` | Organize bank-account establishment, mandates, KYC, statements support, and account administration. | Account-opening documents, mandates, KYC, authorized-signatory evidence, account correspondence. | Credentials/secrets must not be stored merely because this folder exists; access controls remain separate. |
| `08_LETTERS_OF_CREDIT` | Organize documentary-credit issuance, amendments, presentation support, discrepancies, and settlement evidence. | LC applications, issued instruments, amendments, shipping/document presentation evidence, bank correspondence. | Underlying project/contract and shipment objects remain separately identifiable; this folder does not define payment entitlement. |
| `09_BANK_GUARANTEES` | Organize guarantees, bonds, amendments, claims, releases, and expiry evidence. | Performance guarantees, advance-payment guarantees, warranty bonds, amendments, releases. | Guarantee obligations must remain linked to the relevant canonical Contract/Project/Organization contexts. |
| `10_AUDIT` | Organize finance-specific external/statutory audit support and financial audit evidence. | PBC files, confirmations, audit queries, responses, supporting schedules. | Enterprise Internal Audit remains under Governance; this node supports finance/statutory audit processes. |
| `11_FINANCIAL_REPORTING` | Organize management, statutory, regulatory, and consolidated financial reporting outputs/support. | Financial statements, management packs, consolidation schedules, reporting support. | Source accounting transactions remain in the ERP/accounting system; reports should identify period/entity metadata. |

---

## 6. Commercial space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_ORGANIZATIONS` | Provide a neutral navigational home/index for external organizations. | Organization profiles, approved reference information, due-diligence links, relationship summaries. | Do not duplicate one Organization into separate customer/supplier/partner masters. |
| `02_RELATIONSHIP_VIEWS` | Present role-specific views of organizations and their contextual relationships. | Customer, supplier, partner, regulator, consultant, subcontractor filtered views/shortcuts. | Views are projections of canonical `OrganizationRelationship`; they are not independent identities or authoritative role records. |
| `03_FRAMEWORK_AGREEMENTS` | Organize reusable commercial frameworks that govern multiple future transactions. | Master service agreements, framework agreements, rate agreements, standing terms. | Specific call-offs/projects/contracts remain separately linked and should not be collapsed into the framework folder. |
| `04_PRICING_COSTING` | Organize reusable pricing models, cost bases, rate cards, and commercial analysis. | Cost models, rate cards, pricing assumptions, price books, commercial models. | Opportunity-specific pricing belongs in the opportunity working structure; sensitive access may be separately controlled. |
| `05_SALES_CONTRACTS` | Provide commercial navigation for customer-facing contracts not better handled through a dedicated Contract view. | Executed sales agreements, commercial amendments, contract indexes/links. | The canonical Contract object and dedicated Contract template remain authoritative; avoid duplicate uncontrolled copies. |
| `06_MARKET_INTELLIGENCE` | Preserve market, competitor, sector, pricing, and opportunity intelligence useful for commercial decisions. | Market reports, competitor analysis, sector research, demand/pricing intelligence. | Formal opportunity working files belong in `01_BD_TENDERS` once an opportunity is established. |

---

## 7. People Administration space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_ORGANIZATION` | Organize workforce-structure and people-operations reference material. | Org charts, position structures, workforce planning, role descriptions. | Legal Entity structure remains canonical Entity data; access to personal details remains controlled. |
| `02_RECRUITMENT` | Manage candidate sourcing, selection, assessment, and hiring administration. | Requisitions, candidate materials, interview records, offers, recruitment correspondence. | Candidate personal data requires appropriate data-category/security controls and retention. |
| `03_EMPLOYEE_ADMINISTRATION` | Manage employment lifecycle administration and personnel records support. | Employment documents, changes, leave/admin records, personnel correspondence. | Highly sensitive payroll/health/identity data should follow stricter governed controls and may reside in designated systems. |
| `04_TRAINING_COMPETENCY` | Manage workforce learning, competency, qualification, and certification evidence. | Training plans, attendance, competency matrices, certificates, qualification records. | Project-delivery training may also be navigated within the Project when the audience/context is project-specific. |
| `05_POLICIES` | Provide people-function policy and procedure material. | HR policies, employee handbooks, people procedures, guidance. | Enterprise-wide controlled policy authority remains consistent with Governance `05_POLICIES_PROCEDURES`; avoid conflicting duplicates. |

---

## 8. Knowledge space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_STANDARDS` | Preserve approved internal/external standards used as reusable reference. | Engineering standards, management standards, internal standards, codes of practice. | Live project requirements remain in the relevant Project/Opportunity context even when based on a standard. |
| `02_TEMPLATES` | Provide governed reusable document, data, checklist, and process templates. | Forms, checklists, document templates, model registers, reusable packs. | Completed instances belong in their business context; do not store executed project records here. |
| `03_TECHNICAL_REFERENCES` | Organize reusable technical manuals, references, guides, and knowledge material. | Vendor manuals, technical guides, reference diagrams, generic calculations/reference notes. | Contract/project deliverables remain in their business context unless explicitly promoted as reusable knowledge. |
| `04_LESSONS_LEARNED` | Capture validated lessons and reusable improvement knowledge from completed work. | Lessons registers, post-project reviews, improvement actions, retrospectives. | Raw issue/action records stay in the originating project/process; promote only governed reusable lessons. |
| `05_RESEARCH` | Organize exploratory research, studies, benchmarks, and analytical source material. | Research papers, benchmarking, experiments, evaluations, technology scans. | Approved standards/policies should be promoted to their controlled locations rather than remaining only as research. |

---

## 9. Shared Services space

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_IT` | Organize enterprise IT service-management, architecture, operations, and support documentation. | System documentation, service procedures, change/support records, architecture references. | Secrets, credentials, and security-sensitive configuration require dedicated controls; canonical repository/provider records remain EIOS objects. |
| `02_FACILITIES` | Organize premises, property, maintenance, utilities, and workplace-facility administration. | Maintenance records, leases support, facility plans, service-provider documentation. | Capital projects may require a dedicated Project structure rather than remaining only in Facilities. |
| `03_ADMINISTRATION` | Organize general enterprise administrative support that has no more specific functional home. | Office administration, general logistics, common administrative procedures, support records. | `Misc` dumping is prohibited; an item belongs here only when Administration is its actual business function. |
| `04_PROCUREMENT_SUPPORT` | Organize shared procurement methods, templates, vendor onboarding support, and procurement-function administration. | Procurement templates, sourcing procedures, onboarding guidance, master process support. | Specific purchases/project procurement belong in their relevant operational or project context. |
| `05_CORPORATE_COMMUNICATIONS` | Manage corporate communications, brand, approved public messaging, and communication assets. | Brand material, press releases, corporate presentations, communication plans, approved media. | Project/customer correspondence remains in the corresponding business context unless intentionally republished corporately. |

---

## 10. Project template

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_PROJECT_CONTROL` | Control project planning, schedule, governance, actions, registers, status, and management reporting. | Plans, schedules, meeting records, action logs, risk/issue registers, progress reports. | Detailed engineering/commercial/finance evidence belongs in the specialized project folders below. |
| `02_CONTRACT_COMMERCIAL` | Manage the contractual and commercial basis of project execution. | Contract, amendments, change orders, claims, commercial correspondence, milestone evidence. | The canonical Contract object is authoritative for contract identity/parties/status; accounting evidence belongs in Finance where appropriate. |
| `03_ENGINEERING` | Manage project technical definition, design, analysis, review, and approved engineering deliverables. | Requirements, drawings, calculations, specifications, technical submittals, review comments. | Site execution evidence belongs under Site Execution; generic reusable standards belong under Knowledge. |
| `04_PROCUREMENT_LOGISTICS` | Manage project-specific sourcing, purchasing support, shipping, logistics, customs, and delivery. | RFQs, purchase support, supplier coordination, packing lists, shipping docs, customs/delivery evidence. | Enterprise procurement policy/process lives in shared/operational procurement spaces. |
| `05_SITE_EXECUTION` | Capture physical implementation, installation, commissioning, field progress, and site coordination. | Daily/site reports, installation records, method statements, commissioning evidence, site coordination. | Formal QA/QC inspection evidence should be routed to `06_QA_QC_HSE` when appropriate. |
| `06_QA_QC_HSE` | Preserve project quality, inspection, testing, non-conformance, safety, and environmental evidence. | ITPs, test records, NCRs, inspections, permits, HSE plans, incident/safety evidence. | Enterprise QA/HSE frameworks remain under Operations `04_QA_QC_HSE`. |
| `07_FINANCE` | Organize project financial evidence and controls needed by the delivery team. | Budgets, cost reports, invoice support, reconciliations, payment evidence, forecasts. | Accounting ledger truth remains in the designated ERP; cross-project finance control belongs in Finance/Treasury. |
| `08_CORRESPONDENCE` | Preserve formal or material project communications not better classified by subject elsewhere. | Formal letters, material emails/messages, notices, transmittals, correspondence registers. | Subject-specific evidence should remain with Engineering/Commercial/etc. where that context is stronger; message identity may remain native/canonical. |
| `09_TRAINING` | Manage project-required training planning, delivery, attendance, materials, and completion evidence. | Training plans, agendas, materials, attendance, certificates, evaluations. | Enterprise employee competency records belong under People Administration when they become workforce records. |
| `10_HANDOVER_CLOSEOUT` | Manage acceptance, completion, handover, warranty, closeout, and transition to operation/support. | Punch lists, acceptance certificates, as-builts, manuals, warranties, closeout registers, final deliverables. | Archive/retention status is not created automatically by closeout; governance remains canonical. |
| `99_ARCHIVE` | Provide a project-local navigational view for closed/historical project material. | Superseded/closed working sets retained for reference. | Does not mean canonical `RECORD`, `DISPOSED`, legal hold, or immutable status. |

---

## 11. Opportunity / Tender template

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_SOURCE_RFP` | Preserve authoritative customer/tender-source material exactly as received. | RFP/RFQ, tender documents, amendments, official attachments, issued instructions. | Internal working interpretations belong in Requirements/Working; do not overwrite source material. |
| `02_REQUIREMENTS` | Translate source requirements into structured compliance, qualification, and response obligations. | Compliance matrices, requirement registers, qualification criteria, clarifications-to-raise. | Bid drafting belongs in Working; source documents remain in `01_SOURCE_RFP`. |
| `03_WORKING` | Develop the technical, commercial, pricing, partner, and submission content before approval. | Draft responses, costing, designs, supplier/partner inputs, internal analysis. | Approved final package moves/projects to `05_FINAL_SUBMISSION`; working content is not proof of submission. |
| `04_INTERNAL_APPROVAL` | Preserve internal decision and authorization evidence for bid/no-bid and final submission. | Approval papers, risk reviews, sign-offs, commercial/technical approvals. | Customer-facing submission artifacts belong in `05_FINAL_SUBMISSION`. |
| `05_FINAL_SUBMISSION` | Preserve the exact package submitted externally and evidence of its transmission. | Submitted documents, package manifest, portal receipt, transmittal, submission evidence. | Folder membership does not define canonical `CanonicalPackage.memberObjectRefs`; canonical package membership remains explicit. |
| `06_CLARIFICATIONS` | Manage post-submission questions, responses, negotiations, revisions, and formal clarification exchanges. | Clarification requests/responses, negotiation records, revised offers, BAFO/final clarification material. | A newly approved resubmission should be clearly distinguished from working drafts and linked to the submission package. |
| `07_AWARD_CONTRACT` | Manage award evidence, negotiated final terms, contract formation, and handoff to execution. | Award notice, LOI, negotiated terms, signed contract initiation, handoff checklist. | Ongoing project execution belongs in Project/Contract structures once created; award folder does not become the project root. |
| `99_CLOSED` | Provide a navigational endpoint for lost, cancelled, withdrawn, expired, or completed opportunities. | Closure evidence, loss review, cancellation notice, final opportunity summary. | Closure path does not itself set canonical Opportunity status or retention/disposition. |

---

## 12. Contract template

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_FORMATION` | Preserve negotiation, due diligence, approvals, and pre-signature contract-formation evidence. | Drafts, negotiations, approvals, legal/commercial review, authority evidence. | Executed agreement belongs in `02_SIGNED_AGREEMENT`; drafts must not be confused with executed terms. |
| `02_SIGNED_AGREEMENT` | Preserve the executed contractual instrument and authoritative execution evidence. | Signed agreement, schedules, appendices, signature evidence. | Later amendments are maintained separately in `03_AMENDMENTS_CHANGE_CONTROL` while remaining linked to the base agreement. |
| `03_AMENDMENTS_CHANGE_CONTROL` | Manage contractual amendments, variations, change orders, and formal change-control evidence. | Amendments, variations, change notices, approvals, change registers. | Informal project changes without contractual effect should not be represented as executed amendments. |
| `04_OBLIGATIONS_DELIVERABLES` | Organize contractual obligations, deliverables, milestones, and compliance evidence. | Deliverable registers, obligation matrices, milestone evidence, acceptance obligations. | Actual project execution artifacts may live in Project folders and be linked rather than duplicated. |
| `05_COMMERCIAL_PAYMENT` | Organize contract-level price, invoicing, payment, security, and commercial settlement evidence. | Payment schedules, invoice support, payment certificates, securities, settlement records. | Accounting ledger truth remains in Finance/ERP; banking instruments may also be managed under Finance/Treasury. |
| `06_CORRESPONDENCE` | Preserve formal contractual notices and communications. | Notices, letters, contractual emails/messages, transmittals, correspondence register. | Technical/project correspondence should remain in project subject areas unless contractual significance requires contract linkage. |
| `07_CLAIMS_DISPUTES` | Manage claims, disputes, notices, substantiation, negotiation, and resolution evidence. | Claims, counterclaims, notices, substantiation, settlement discussions, dispute records. | Privileged/legal materials may require a governed Legal matter space with stricter access. |
| `08_CLOSEOUT` | Manage completion, final account, release, expiry, termination, and contractual closeout. | Completion evidence, final settlement, releases, expiry/termination records, closeout checklist. | Closeout does not itself authorize disposition or remove legal hold/retention obligations. |
| `99_ARCHIVE` | Provide a contract-local closed/historical navigational view. | Closed/superseded support material retained for reference. | Does not replace canonical Contract status, retention, record declaration, or repository-binding roles. |

---

## 13. Function template

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_POLICIES_PROCEDURES` | Manage function-specific controlled policy, procedure, and work-instruction material. | Function policies, SOPs, instructions, control procedures. | Enterprise-wide policy authority should remain aligned with Governance policy control. |
| `02_OPERATIONS` | Organize the function's recurring operating work and process execution evidence. | Process records, work queues, operational support material, routine outputs. | Projects/opportunities/contracts should use their dedicated scope templates when those contexts dominate. |
| `03_CONTROLS_COMPLIANCE` | Preserve evidence that function controls and compliance obligations are designed and operating. | Control matrices, compliance checks, control evidence, exception logs. | Independent audit belongs in Governance/Internal Audit. |
| `04_REPORTING` | Organize recurring function management and performance reporting. | KPIs, dashboards, period reports, management packs. | Source transaction records remain in the operational/system-of-record context. |
| `05_REFERENCE_KNOWLEDGE` | Preserve function-specific reusable guidance and reference knowledge. | Guides, FAQs, reference materials, local best practices. | Enterprise reusable standards/templates should be promoted to Knowledge when broadly applicable. |
| `06_RECORDS_SUPPORT` | Organize evidence supporting formal record declaration, record inventories, and governance processes for the function. | Record inventories, declaration support, transfer/disposition support, records registers. | The folder does not itself make its contents canonical `CanonicalRecord` objects. |
| `99_ARCHIVE` | Provide a historical/closed view for the function. | Closed historical process sets/reference. | Does not imply formal record, retention, immutability, or disposition status. |

---

## 14. External Organization template

| Item | Purpose | Typical contents | Boundary |
|---|---|---|---|
| `01_PROFILE_DUE_DILIGENCE` | Organize neutral organization profile, onboarding, qualification, and due-diligence evidence. | Corporate profile, registrations, ownership evidence, KYC/KYB, qualification material. | Compliance screening outcomes remain governed evidence/metadata; avoid role-specific duplicate Organization identities. |
| `02_RELATIONSHIPS` | Present the organization's contextual business relationships and role history. | Relationship summaries, role views, engagement indexes, links to opportunities/projects/contracts. | Canonical `OrganizationRelationship` objects remain authoritative for role, scope, and effective dates. |
| `03_COMMERCIAL` | Organize general counterparty commercial discussions and information not yet tied to a specific contract/opportunity. | Rate discussions, general proposals, commercial profiles, account planning. | Opportunity-specific bid material belongs in the Opportunity structure; executed contracts belong in Contracts. |
| `04_CONTRACTS` | Provide navigation to contracts with the organization. | Contract indexes, links, executed contract views, amendment links. | Avoid uncontrolled duplicate contract masters; canonical Contract identity is authoritative. |
| `05_DELIVERABLES` | Organize organization-supplied or organization-facing deliverables not already better scoped to a project/contract. | Generic deliverables, certificates, product/service information, recurring submissions. | Project/contract-specific deliverables should remain in those dedicated scopes and be linked here if useful. |
| `06_CORRESPONDENCE` | Preserve material general correspondence with the organization. | Formal letters, material emails/messages, notices, account correspondence. | Project/contract/opportunity-specific correspondence belongs in that stronger business context. |
| `07_COMPLIANCE_EVIDENCE` | Organize compliance, screening, qualification, regulatory, and assurance evidence related to the organization. | Screening reports, certifications, sanctions/compliance evidence, renewals. | A folder label never represents the current compliance status; authoritative screening records and decisions remain canonical. |
| `99_CLOSED` | Provide a historical/closed view for an inactive relationship or organization navigation context. | Relationship closure records, historical reference. | Does not dissolve/deactivate the canonical Organization or erase historical relationships. |

---

## 15. Purpose registration for local additions

Any locally added folder beneath a normative node MUST be registered with at least:

```text
ItemName
ParentNode
Purpose
TypicalContents
ExclusionsOrBoundary
OwnerOrSteward
EffectiveFrom
ReviewDate (when temporary or experimental)
```

A proposed local folder named only `MISC`, `GENERAL`, `TEMP`, `OTHER`, `STUFF`, `DOCUMENTS`, or an equivalent catch-all is non-conforming unless governance approves a narrowly defined purpose and boundary.

If two folders cannot be explained by materially different purposes, they should normally be merged, represented as metadata/views, or redesigned before adoption.
