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

## 3. Local additions

Enterprises may add local subfolders below a normative node when necessary, provided the addition does not redefine canonical semantics or contradict the purpose of the parent space.

## 4. Prohibited exception behavior

Exceptions must not:

- make a folder path the primary identity;
- reuse an enterprise document number;
- broaden authorization contrary to EIOS policy;
- infer legal hold or disposition eligibility from a path;
- override authoritative repository placement decisions;
- create provider-specific requirements in the normative provider-neutral standard.

## 5. Versioning

This convention is independently versioned. Backward-compatible additions may be introduced in a minor version; breaking organizational changes require a major version. Provider mappings may evolve independently as long as they continue to conform to the logical standard.
