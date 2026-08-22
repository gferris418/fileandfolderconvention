# 09 — Records, Closeout & Archive

## 1. Organizational archive versus formal record

`99_ARCHIVE` and `99_CLOSED` are human-facing organizational states. They do not by themselves declare an item to be a formal record.

A formal EIOS record has its own canonical Record identity, record number/class, declaration evidence, source-object reference, content digest, and governance context. A file copied into an archive folder does not become a canonical Record merely because of its location.

## 2. Closeout pattern

Where a process has a defined closeout stage, use a dedicated folder such as:

```text
10_HANDOVER_CLOSEOUT
```

before organizational archive. This supports explicit acceptance and completeness checks without pretending that the folder move is the canonical closure event.

## 3. Retention triggers

EIOS retention can be triggered from events such as creation, publication, contract end, project end, record declaration, last modification, or another event-based trigger. Therefore:

- moving a project into `99_ARCHIVE` does not prove the project-end retention clock started;
- moving a contract into archive does not prove contract expiry/termination;
- publishing a file into a `Published` folder does not prove canonical publication;
- declaring a record is a canonical governance action, not a directory operation.

## 4. Legal hold and immutability

Legal hold overrides ordinary disposition regardless of folder location. Immutability/WORM, compliance lock, governance lock, and record-copy requirements must be implemented through EIOS policy and repository capability, not through labels such as `DO_NOT_DELETE` or `LOCKED` in paths.

## 5. Disposition

EIOS disposition actions can include destruction, transfer to archive, review, export-first processing, or permanent retention. A physical deletion or move is not authoritative unless a valid policy decision and required approvals support it.

Canonical identity and audit lineage must survive native deletion/disposition where required by EIOS.

## 6. Data residency

Geographic or jurisdictional storage/processing constraints are policy decisions. Do not encode residency solely through folders such as `EU_ONLY` or `COUNTRY_X`. Provider/repository placement and capability profiles are authoritative.

## 7. Archive principles

- Preserve canonical identity through archival moves.
- Do not duplicate content merely to create a visual archive unless required by policy or repository capability.
- Preserve authoritative-copy designation through EIOS repository bindings.
- Preserve content integrity evidence/digests where controlled by EIOS.
- Do not delete canonical identity, relationships, governance evidence, or audit lineage when native content is disposed.
- Legal hold blocks ordinary disposition regardless of folder location.
- `TRANSFER_TO_ARCHIVE` is a governance disposition action; `99_ARCHIVE` is only a navigational destination unless EIOS says otherwise.
