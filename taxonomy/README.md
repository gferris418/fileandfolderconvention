# Taxonomy Crosswalks

The files in this directory support human-facing naming, linting, examples, and provider mappings. They are **not** the authoritative EIOS Taxonomy Registry.

EIOS canonical taxonomy objects govern controlled terms, status, hierarchy, and supersession. The CIM supports taxonomy domains including document type, discipline, handling classification, data category, jurisdiction, country, currency, relationship type, record class, retention class, and extensible additional domains.

## Rules

1. A local short code must map unambiguously to an approved EIOS canonical term when used as controlled metadata.
2. Folder names do not create taxonomy terms.
3. Deprecated or superseded canonical terms must not be silently reused for a different meaning.
4. Provider-native labels may differ, but mappings must preserve the canonical term.
5. Security handling classification, data category, legal jurisdiction, and retention class must not be inferred solely from file or folder names.

## Files

- `disciplines.yaml` — presentation codes for discipline labels.
- `document-types.yaml` — presentation codes for document-type labels.
- `functions.yaml` — business-function navigation codes.
- `lifecycle-states.yaml` — presentation lifecycle states plus canonical revision reference.
- `information-scopes.yaml` — seven CIM information scopes and template crosswalk.
- `repository-binding-roles.yaml` — provider-mapping reference for canonical binding roles.
