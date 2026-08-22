# 10 — Exceptions and Governance

## 1. Purpose

This document exists to prevent local convenience, provider limitations, or one-off operational needs from silently weakening the purpose clarity, provider neutrality, or canonical EIOS semantics of the standard.

## 2. Exception rule

An exception to this convention must document:

- scope;
- business reason;
- affected logical spaces/templates;
- provider limitation, if any;
- owner;
- approval authority;
- effective date;
- review or expiry date where appropriate.

If the exception creates or changes a structural folder, view, or template node, it MUST additionally document:

- item name;
- parent node;
- explicit business purpose;
- typical contents;
- exclusions/boundary;
- owner or steward;
- whether the item is permanent, temporary, or a metadata-driven view;
- effective date;
- review/expiry date where applicable.

A new folder is not justified merely because users currently do not know where an item belongs. If the business purpose cannot be stated clearly, the structure must not be added until the information-routing problem is understood.

## 3. Provider limitations

Provider-specific constraints must be recorded in `provider-mappings/` rather than changing normative logical structures without governance review.

A provider limitation may justify a different projection, shortcut, view, or compensating control. It does not justify changing EIOS canonical identity, policy, scope, relationship, lifecycle, or authorization semantics.

## 4. Local additions

Enterprises may add local subfolders below a normative node when necessary, provided the addition:

1. has a distinct and documented business purpose;
2. defines typical contents and exclusions;
3. does not duplicate a sibling's purpose without a governed reason;
4. does not redefine canonical semantics;
5. does not contradict the parent node's purpose;
6. is added to the local Purpose & Boundary Register before operational use.

If two candidate folders serve materially the same purpose, prefer one folder plus metadata/views rather than creating parallel categories.

## 5. Prohibited exception behavior

Exceptions must not:

- create an undefined catch-all such as `MISC`, `GENERAL`, `STUFF`, `TEMP`, or equivalent;
- define a folder purpose by merely repeating its label;
- make a folder path or filename the primary canonical identity;
- reuse an enterprise document number;
- use a path as a substitute for canonical `informationScope` or required business context;
- create separate canonical Organization identities merely to represent customer, supplier, partner, regulator, subcontractor, or similar role views;
- create competing canonical Project identities for different participating entities;
- force messages, datasets, records, media, or packages into physical file/folder form where a provider-native representation is more appropriate;
- infer CanonicalPackage membership solely from directory contents;
- infer canonical relationships from nesting, path ancestry, co-location, or shortcuts;
- infer revision lifecycle state from folders such as Draft, Published, Record, or Archive;
- infer record declaration, retention, legal hold, immutability, disposition, or data-residency eligibility from a path;
- infer repository binding role, write mode, authoritative-copy designation, synchronization state, or conflict state from a path;
- broaden authorization contrary to EIOS policy;
- override authoritative repository placement decisions;
- repurpose deprecated/superseded canonical taxonomy codes for a new meaning;
- create provider-specific requirements in the normative provider-neutral standard.

## 6. Exception evidence

Where an exception affects a provider mapping, record the native limitation, affected EIOS capability, compensating control, residual risk, and whether the target repository remains eligible for authoritative placement.

Where an exception changes information organization, the approval evidence must also record why existing purpose-defined nodes, metadata, views, or relationships could not satisfy the need.

## 7. Versioning

This convention is independently versioned. Backward-compatible additions may be introduced in a minor version; breaking organizational changes require a major version. Provider mappings may evolve independently as long as they continue to conform to the logical standard and frozen EIOS semantics.

The normative purpose definitions are maintained in `15-purpose-register.md`.
