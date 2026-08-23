# EIOS File & Folder Convention v1.0.0-draft.4 — Conformance & Release Certification Design

**Status:** Design specification for review  
**Date:** 2026-08-23  
**Baseline:** EIOS File & Folder Convention v1.0.0-draft.3 on `main`  
**Canonical dependency:** EIOS-CIM v1.0.0, sourced from the corrected v1.0.0-RC3 package  
**Scope:** Documentation hardening H01/H02 plus executable conformance and release-certification design. No EIOS-CIM or Core Architecture changes.

---

## 1. Objective

Promote the EIOS File & Folder Convention from `1.0.0-draft.3` toward frozen `v1.0.0` by proving that its normative requirements are machine-verifiable and remain aligned with EIOS-CIM.

The certification system must verify the convention without turning folders, filenames, or test fixtures into new sources of canonical truth.

Core separation:

```text
EIOS-CIM canonical semantics
        ↓
File & Folder Convention
human-facing navigation / naming projection
        ↓
Provider mapping
        ↓
Native implementation
```

The conformance suite validates the projection boundary. It does not redefine the CIM.

---

## 2. Draft.4 documentation hardening

### H01 — Authorization non-broadening terminology

The provider-mapping rules will state explicitly:

> When a provider-native permission projection is represented by an EIOS `PermissionBinding`, `mappingDirection` MUST be either `PRESERVE` or `RESTRICT`.
>
> `PRESERVE` means the provider mapping reflects the effective EIOS authorization decision without increasing access. `RESTRICT` means the provider mapping applies tighter effective access than the EIOS decision.
>
> `BROADEN` is prohibited by EIOS Invariant 11. Provider adapters MUST NOT silently escalate effective access beyond the canonical authorization decision. A provider projection that would broaden effective access MUST be rejected or constrained before activation.

This is terminology hardening of an existing convention rule, not a new security model.

### H02 — Machine-readable taxonomy crosswalk

Every controlled local taxonomy crosswalk entry used as controlled metadata MUST contain an unambiguous canonical mapping.

Required field:

```yaml
canonicalTermCode: TAXON-DOC-DRG
```

Pattern:

```text
^TAXON-[A-Z0-9-]+$
```

Optional authoritative registry reference:

```yaml
canonicalTermRef:
  objectUID: TAXONTERM-01J9P7K2M4N6Q8R0S2T4U6V8W
```

Pattern:

```text
^TAXONTERM-[A-Z0-9]{6,64}$
```

The two identifiers are distinct:

- `canonicalTermCode` is the controlled business vocabulary code.
- `canonicalTermRef.objectUID` is the immutable canonical identity of the `TaxonomyTerm` object.

Local labels and short codes MUST NOT create a shadow taxonomy or silently replace a canonical term.

The existing `canonicalExample` field is transitional documentation only. Draft.4 will replace controlled mappings with `canonicalTermCode` and conformance will reject controlled entries lacking it.

---

## 3. Important alignment constraints

### 3.1 Canonical UID is not the filename identity

Controlled filename convention:

```text
[EnterpriseDocumentNo]_[Revision]_[ShortTitle].[ext]
```

Example:

```text
ABC-PRJ001-ENG-DRG-000245_C02_Equipment-Layout.pdf
```

Canonical metadata may independently contain:

```json
{
  "objectUID": "DOC-01J9P7K2M4N6Q8R0S2T4U6V8W",
  "enterpriseDocumentNo": "ABC-PRJ001-ENG-DRG-000245"
}
```

The suite must verify separation between canonical identity, enterprise document number, and display filename.

### 3.2 Seven information scopes, six mandatory context rules

Canonical scopes:

```text
GROUP
ENTITY
OPPORTUNITY
PROJECT
CONTRACT
FUNCTION
EXTERNAL
```

Required canonical business context:

```text
GROUP        → no additional scope-specific context required by RC3
ENTITY       → owningEntityRef
OPPORTUNITY  → opportunityRef
PROJECT      → projectRef
CONTRACT     → contractRef
FUNCTION     → functionCode
EXTERNAL     → counterpartyRef
```

A workspace-root fixture may represent this canonical scope/context relationship. Ordinary subfolders are navigation nodes and do not each become separate canonical information objects merely by existing.

A `GROUP` fixture must prove that no extra context reference is required. The suite MUST NOT claim that RC3 rejects a declared `projectRef` solely because `informationScope` is `GROUP`; RC3 does not encode that prohibition.

### 3.3 Governance mechanics remain distinct

The suite must preserve the actual CIM mechanics:

```text
RetentionPolicy
   ↓
PolicyAssignment.targetObjectRef

LegalHold
   ↓
targetObjectRefs[]

AuthorizationGrant
   ↓
targetObjectRef
```

A path such as `LEGAL_HOLD/`, `RECORDS/`, `ARCHIVE/`, `CONFIDENTIAL/`, or `AUTHORITATIVE/` does not create the corresponding canonical state.

The presence of such a folder is not automatically non-conforming. The prohibited behavior is treating its name/location as sufficient evidence of canonical governance, authorization, lifecycle, repository-binding, or residency state.

### 3.4 Repository semantics

`RepositoryBinding` resolves provider identity through:

```text
repositoryRef → Repository → providerCode
```

Provider code is not duplicated into `RepositoryBinding` business identity semantics.

`IMMUTABLE` is a repository binding `writeMode` / repository capability concern, not a `bindingRole`.

---

## 4. Reference implementation approach

The normative reference runner will use:

```text
Python
├── jsonschema (Draft 2020-12)
├── PyYAML
├── pathlib
└── pytest
```

OPA/Rego is optional. The standard will not make OPA a mandatory dependency.

Reasons:

1. JSON Schema validation is the canonical mechanism for CIM fixture validation.
2. Python provides straightforward deterministic directory-tree and YAML/JSON processing.
3. `pytest` supports precise positive/negative assertions and CI integration.
4. Semantic separation rules can remain provider-neutral and testable without binding the standard to one policy engine.

---

## 5. Repository structure for executable certification

```text
conformance/
├── README.md
├── certification/
│   ├── test-catalogue.yaml
│   ├── cim-baseline.lock.json
│   └── certification-profile.yaml
├── schemas/
│   ├── fixture-envelope.schema.json
│   ├── workspace.schema.json
│   ├── tree-node.schema.json
│   ├── purpose-registration.schema.json
│   └── provider-profile.schema.json
├── fixtures/
│   ├── positive/
│   │   ├── purpose/
│   │   ├── scope/
│   │   ├── naming/
│   │   ├── templates/
│   │   ├── semantic-separation/
│   │   ├── taxonomy/
│   │   └── provider-capability/
│   └── negative/
│       ├── purpose/
│       ├── scope/
│       ├── naming/
│       ├── templates/
│       ├── semantic-separation/
│       ├── taxonomy/
│       └── provider-capability/
├── rules/
│   ├── purpose.py
│   ├── scope.py
│   ├── naming.py
│   ├── templates.py
│   ├── semantic_separation.py
│   ├── taxonomy.py
│   └── provider_capability.py
├── runner/
│   ├── cim.py
│   ├── fixtures.py
│   ├── tree.py
│   ├── catalogue.py
│   └── report.py
├── tests/
│   ├── test_purpose.py
│   ├── test_scope.py
│   ├── test_naming.py
│   ├── test_templates.py
│   ├── test_semantic_separation.py
│   ├── test_taxonomy.py
│   └── test_provider_capability.py
├── REPORT.json
└── REPORT.md
```

`REPORT.json` and `REPORT.md` are generated certification outputs, not hand-authored normative inputs.

---

## 6. Fixture model

Test fixtures use a neutral fixture envelope. A fixture sidecar represents metadata available to EIOS for certification; it does not mandate that production providers store physical `.json` sidecar files.

Example:

```json
{
  "fixtureId": "SCOPE-PROJECT-001",
  "expectedValid": true,
  "workspace": {
    "informationScope": "PROJECT",
    "businessContext": {
      "projectRef": {
        "objectUID": "PRJ-01J9P7K2M4N6Q8R0S2T4U6V8X"
      }
    }
  },
  "tree": {},
  "canonicalObjects": []
}
```

The fixture envelope separates:

- workspace/navigation projection;
- canonical objects;
- provider capability declarations;
- expected result;
- source requirement/test ID.

---

## 7. Five certification domains

### Domain 1 — Purpose-first and scope/context

Tests:

- every normative structural node has purpose, typical contents, and boundary;
- label-only purpose definitions fail;
- undefined catch-all nodes fail unless governed;
- all seven scope templates exist;
- six scope-specific CIM context requirements validate;
- `GROUP` validates without an extra context reference;
- subfolders are not required to restate workspace scope/context;
- if a subfolder is independently instantiated as a `CanonicalInformationObject`, it must itself satisfy the CIM schema.

### Domain 2 — Naming and identity separation

Tests:

- controlled filenames follow the convention grammar where the standard marks it normative;
- `EnterpriseDocumentNo`, revision, short title, and extension remain display/business fields, not canonical UID;
- provider-sensitive characters are rejected by normative filename fixtures;
- uncontrolled version-noise patterns are rejected;
- filename/path changes do not alter `objectUID`;
- issued `enterpriseDocumentNo` values are never reused in stateful certification fixtures.

The suite must not invent a requirement that all filenames contain `objectUID`.

### Domain 3 — Template completeness and purpose boundaries

Tests the exact merged seven templates rather than invented folder names.

For example, Project requires the published Project nodes such as:

```text
01_PROJECT_CONTROL
02_CONTRACT_COMMERCIAL
03_ENGINEERING
04_PROCUREMENT_LOGISTICS
05_SITE_EXECUTION
06_QA_QC_HSE
07_FINANCE
08_CORRESPONDENCE
09_TRAINING
10_HANDOVER_CLOSEOUT
99_ARCHIVE
```

Local additions are permitted only when they satisfy the registered-purpose and exception-governance requirements. Additional folders do not fail merely because they are additional.

### Domain 4 — Semantic separation

The suite rejects semantic inferences such as:

```text
folder path → canonical identity
folder path → informationScope/businessContext
folder path → authorization
folder path → record declaration
folder path → legal hold / retention / immutability / disposition
folder path → data residency
folder path → RepositoryBinding role/writeMode/sync state
folder nesting → canonical relationship
folder contents → CanonicalPackage membership
filename change → objectUID change
```

Example LegalHold negative test:

- physical folder `LEGAL_HOLD/` may exist;
- implementation asserts that folder placement creates an active LegalHold;
- assertion must fail;
- a valid LegalHold canonical object uses `targetObjectRefs[]`.

Example archive-move positive test:

```text
Before move:
objectUID = DOC-...
bindingRole = WORKING

Move physical projection:
/WORKING/A.pdf → /99_ARCHIVE/A.pdf

After move absent another canonical operation:
objectUID unchanged
bindingRole unchanged
lifecycle unchanged
legalHold unchanged
retention unchanged
```

### Domain 5 — Taxonomy and provider mapping

Tests:

- every controlled local crosswalk term has `canonicalTermCode`;
- `canonicalTermCode` matches `^TAXON-[A-Z0-9-]+$`;
- optional `canonicalTermRef.objectUID` matches `^TAXONTERM-[A-Z0-9]{6,64}$`;
- code and UID are never confused;
- when authoritative registry data is available, referenced canonical terms must exist;
- `PermissionBinding.mappingDirection = BROADEN` fails;
- `PRESERVE` and `RESTRICT` are valid schema values;
- provider permission implementation that increases effective access fails even if the declared mapping says `PRESERVE` or `RESTRICT`;
- provider capability gaps cause ineligibility, restriction, or declared compensating control rather than semantic invention from folder names.

---

## 8. CIM dependency and locking

The convention repository must not silently fork the frozen CIM.

Certification will use:

```text
conformance/certification/cim-baseline.lock.json
```

The lock records at minimum:

```json
{
  "cimVersion": "1.0.0",
  "schemaCount": 51,
  "manifestDigest": "sha256:<authoritative-release-digest>",
  "source": "<authoritative-release-location>"
}
```

The runner must verify the baseline before issuing a release certificate.

Development may support an explicit `--cim-dir` input. Final release certification must fail closed if the supplied CIM cannot be matched to the locked authoritative baseline.

---

## 9. Test catalogue and traceability

Every test case is registered in `test-catalogue.yaml`.

Example:

```yaml
id: SEM-LEGAL-HOLD-001
domain: semantic-separation
requirement: FF-CONF-15
expected: invalid
source:
  standard: standard/v1.0/00-principles.md
  conformanceClass: 15
fixture: fixtures/negative/semantic-separation/legal-hold-from-path.json
reason: Folder placement cannot establish canonical legal-hold state.
```

Traceability chain:

```text
Normative requirement
    ↓
Conformance class
    ↓
Test case
    ↓
Fixture
    ↓
Execution result
    ↓
Certification report
```

No release-critical `MUST` rule may remain without at least one executable test.

---

## 10. Certification outputs

Generated `REPORT.json` and `REPORT.md` include:

- convention version;
- source Git commit;
- CIM version;
- CIM manifest digest;
- runner version;
- execution timestamp;
- positive test totals/passes;
- negative test totals/rejections;
- coverage across all 24 conformance classes;
- uncovered normative `MUST` rules;
- failures and warnings;
- certification decision.

Freeze gate:

```text
positive fixtures             100% PASS
negative fixtures             100% REJECT
24 conformance classes        100% COVERED
CIM baseline                  VERIFIED
runner/test errors            0
uncovered release-critical MUST rules 0

→ RELEASE CERTIFICATION ELIGIBLE
```

The release decision itself remains a governance action; the runner produces evidence and a recommendation, not unilateral governance authority.

---

## 11. Non-goals

This work does not:

- modify EIOS Core Architecture;
- modify frozen EIOS-CIM v1.0.0 semantics;
- require sidecar files in production repositories;
- require OPA/Rego;
- make paths authoritative for security, lifecycle, retention, hold, residency, relationships, or repository role;
- create provider-specific certification requirements before the corresponding provider profile exists;
- prohibit a folder merely because its label resembles a canonical governance concept; only semantic inference/use is prohibited unless another naming rule separately forbids it.

---

## 12. Implementation sequencing after design approval

1. Apply H01/H02 documentation changes and advance the working convention to `1.0.0-draft.4`.
2. Add schemas for fixture envelopes and provider/taxonomy test inputs.
3. Add failing tests first for each conformance domain.
4. Implement minimal rule/runner logic to satisfy those tests.
5. Add positive and negative fixtures for all 24 conformance classes.
6. Add CIM baseline locking and offline Draft 2020-12 resolution.
7. Generate deterministic JSON/Markdown reports.
8. Run the complete certification suite from a clean checkout.
9. Open a certification PR with machine-generated evidence.
10. Promote to frozen `v1.0.0` only after the governance release decision.
