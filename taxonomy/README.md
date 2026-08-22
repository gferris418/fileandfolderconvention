# Taxonomy Crosswalks

## Purpose of this directory

The files in this directory support human-facing naming, linting, examples, template selection, and provider mappings. They are **not** the authoritative EIOS Taxonomy Registry.

EIOS canonical taxonomy objects govern controlled terms, status, hierarchy, and supersession. The CIM supports taxonomy domains including document type, discipline, handling classification, data category, jurisdiction, country, currency, relationship type, record class, retention class, and extensible additional domains.

## Purpose-first rule for terms

Every term in a local crosswalk must contain enough description to explain **why the term exists and when it should be used**. A code and label alone are insufficient.

At minimum, each locally maintained term should have:

```text
code
label
purpose
canonical mapping/example (where applicable)
boundary (when misuse is reasonably likely)
```

Terms that cannot be distinguished by purpose should not be maintained as separate local codes unless a canonical taxonomy difference requires them.

## Rules

1. A local short code must map unambiguously to an approved EIOS canonical term when used as controlled metadata.
2. Every local term must state its purpose/usage meaning; labels alone do not establish semantic meaning.
3. Folder names do not create taxonomy terms.
4. Deprecated or superseded canonical terms must not be silently reused for a different meaning.
5. Provider-native labels may differ, but mappings must preserve the canonical term and purpose.
6. Security handling classification, data category, legal jurisdiction, and retention class must not be inferred solely from file or folder names.
7. Classification should follow the information object's primary business purpose/subject, not merely its storage location or creator's department.

## Files and their purpose

- `disciplines.yaml` — defines presentation codes and purpose descriptions for the subject-responsibility discipline of an information object.
- `document-types.yaml` — defines presentation codes and purpose descriptions for controlled document types based on the document's primary business function.
- `functions.yaml` — defines business-function navigation codes and explains the responsibility represented by each function.
- `lifecycle-states.yaml` — defines human-facing presentation states and their purpose while preserving separation from canonical revision lifecycle.
- `information-scopes.yaml` — defines the seven CIM information-scope navigation crosswalks, required canonical context, template, purpose, and boundary.
- `repository-binding-roles.yaml` — explains the purpose and boundary of each canonical repository-binding role for provider mappings.
