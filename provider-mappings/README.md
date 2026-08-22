# Provider Mappings

Provider mappings describe how the normative logical convention is projected into a specific platform. They are implementation profiles, not normative changes to the EIOS File & Folder Convention or EIOS-CIM.

## Mandatory mapping declaration

Every provider mapping must state:

- native construct used for each logical level;
- supported EIOS information scopes and how they are presented;
- naming/path/depth/character constraints;
- metadata and taxonomy capabilities;
- versioning behavior;
- native ACL, group, role, permission-inheritance, and sharing behavior;
- external-sharing capabilities and restrictions;
- retention and event-based retention capabilities;
- legal-hold capabilities;
- immutable/WORM storage capabilities;
- classification and DLP capabilities;
- workflow capabilities;
- full-text and semantic-search capabilities;
- webhooks/change-event capabilities;
- audit-log capabilities;
- data-residency controls;
- repository-binding roles supported (`AUTHORITATIVE`, `WORKING`, `PUBLISHED`, `RECORD_COPY`, `REPLICA`, `CACHE`, `MIGRATION_SOURCE`, `MIGRATION_TARGET`);
- write-mode implementation (`READ_WRITE`, `READ_ONLY`, `IMMUTABLE`, `SYSTEM_MANAGED`);
- synchronization-state handling and conflict behavior;
- compensating controls;
- known non-conformities.

## Authorization invariant

A provider mapping must never redefine canonical identity or silently broaden authorization. A provider-native permission projection may preserve or restrict effective access; it must not broaden it beyond the EIOS authorization decision.

## Repository identity

Provider identity is resolved through the canonical Repository relationship. Do not create folder conventions that require provider codes to become part of canonical business identity.

## Capability honesty

If a provider cannot implement a required EIOS capability, the mapping must declare the gap and compensating control or mark the target repository ineligible. A logical folder name must never be used as evidence that a governance capability exists.
