# Provider Mappings

## Purpose

Provider mappings explain how the provider-neutral EIOS File & Folder Convention is projected into a specific platform. Their purpose is to make provider behavior explicit, testable, and honest without changing the logical standard or EIOS-CIM.

They are implementation profiles, not normative changes to the EIOS File & Folder Convention or EIOS-CIM.

## Mandatory mapping declaration and why each item exists

| Declaration item | Purpose |
|---|---|
| Native construct used for each logical level | Identify which provider object (site, library, shared drive, folder, repository, bucket, view, etc.) represents each logical EIOS navigation level. |
| Supported EIOS information scopes | Show which of `GROUP`, `ENTITY`, `OPPORTUNITY`, `PROJECT`, `CONTRACT`, `FUNCTION`, and `EXTERNAL` can be projected and how users navigate them. |
| Naming/path/depth/character constraints | Prevent a provider implementation from generating invalid, inaccessible, or unstable paths. |
| Metadata and taxonomy capabilities | State how canonical metadata/controlled terms can be represented without forcing semantics into filenames/folders. |
| Versioning behavior | Explain how provider-native versions map to EIOS revision/version expectations and where limitations exist. |
| ACL/group/role/inheritance/sharing behavior | Explain how effective authorization is projected and inherited so access is not silently broadened. |
| External-sharing capabilities/restrictions | Make external access behavior and risk explicit rather than relying on provider defaults. |
| Retention/event-based retention capabilities | State whether the provider can preserve information for required durations/triggers and what compensating controls are needed. |
| Legal-hold capabilities | State whether content can be preserved against ordinary deletion/disposition when a canonical legal hold applies. |
| Immutable/WORM capabilities | State whether and how provider-native immutability can satisfy EIOS policy requirements. |
| Classification/DLP capabilities | Explain how handling classification and data-protection controls are represented/enforced. |
| Workflow capabilities | Explain whether approval, review, publication, disposition, or other controlled workflows can be implemented natively or require external orchestration. |
| Full-text/semantic-search capabilities | State how content can be discovered while respecting effective authorization and classification. |
| Webhooks/change-event capabilities | Explain how provider changes can be detected and projected into canonical event/synchronization processing. |
| Audit-log capabilities | State what provider evidence exists for access/change/admin actions and how it complements the EIOS audit evidence ledger. |
| Data-residency controls | State where information can be stored/processed and whether policy-constrained placement is enforceable. |
| Repository-binding roles | Declare which binding roles (`AUTHORITATIVE`, `WORKING`, `PUBLISHED`, `RECORD_COPY`, `REPLICA`, `CACHE`, `MIGRATION_SOURCE`, `MIGRATION_TARGET`) the provider can safely support. |
| Write-mode implementation | Explain how `READ_WRITE`, `READ_ONLY`, `IMMUTABLE`, and `SYSTEM_MANAGED` behavior is enforced or approximated. |
| Synchronization/conflict behavior | Define how `CURRENT`, `BEHIND`, `AHEAD`, `PENDING`, `CONFLICT`, and `ERROR` conditions are detected and handled. |
| Compensating controls | Record the control used when the provider lacks a native capability but EIOS policy still permits use. |
| Known non-conformities | Make limitations explicit so a repository can be denied, restricted, or used only for eligible information. |

Every provider mapping must state all items above. An omitted declaration item is a capability unknown, not an implied capability.

## Authorization invariant

A provider mapping must never redefine canonical identity or silently broaden authorization. A provider-native permission projection may preserve or restrict effective access; it must not broaden it beyond the EIOS authorization decision.

## Repository identity

Provider identity is resolved through the canonical Repository relationship. Do not create folder conventions that require provider codes to become part of canonical business identity.

## Capability honesty

If a provider cannot implement a required EIOS capability, the mapping must declare the gap and compensating control or mark the target repository ineligible. A logical folder name must never be used as evidence that a governance capability exists.
