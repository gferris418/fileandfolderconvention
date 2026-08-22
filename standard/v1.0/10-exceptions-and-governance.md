# 10 — Exceptions and Governance

## 1. Exception rule

An exception to this convention must document:

- scope;
- business reason;
- affected logical spaces/templates;
- provider limitation, if any;
- owner;
- approval authority;
- effective date;
- review or expiry date where appropriate.

## 2. Provider limitations

Provider-specific constraints must be recorded in `provider-mappings/` rather than changing normative logical structures without governance review.

A provider limitation may justify a different projection, shortcut, view, or compensating control. It does not justify changing EIOS canonical identity, policy, scope, relationship, lifecycle, or authorization semantics.

## 3. Local additions

Enterprises may add local subfolders below a normative node when necessary, provided the addition does not redefine canonical semantics or contradict the purpose of the parent space.

## 4. Prohibited exception behavior

Exceptions must not:

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

## 5. Exception evidence

Where an exception affects a provider mapping, record the native limitation, affected EIOS capability, compensating control, residual risk, and whether the target repository remains eligible for authoritative placement.

## 6. Versioning

This convention is independently versioned. Backward-compatible additions may be introduced in a minor version; breaking organizational changes require a major version. Provider mappings may evolve independently as long as they continue to conform to the logical standard and frozen EIOS semantics.
