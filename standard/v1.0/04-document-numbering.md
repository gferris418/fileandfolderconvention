# 04 — Enterprise Document Numbering

## 1. Purpose

Enterprise document numbers provide stable, controlled, human-readable business identifiers for logical documents. Their purpose is to support human recognition, registers, transmittals, contractual references, search, and cross-system communication without replacing EIOS canonical `objectUID` identity.

## 2. Recommended patterns

Group-level:

```text
GRP-[DISCIPLINE]-[DOCTYPE]-[SEQUENCE]
```

Entity-level:

```text
[ENTITY]-[DISCIPLINE]-[DOCTYPE]-[SEQUENCE]
```

Project-level:

```text
[ENTITY]-[PROJECT]-[DISCIPLINE]-[DOCTYPE]-[SEQUENCE]
```

Example:

```text
ABC-PRJ001-ENG-DRG-000245
```

## 3. Purpose of each segment

| Segment | Purpose | Boundary |
|---|---|---|
| `GRP` | Identify that the controlled document number is issued in a group-level numbering context rather than for one specific Entity/Project. | `GRP` is a numbering convention token, not an EIOS canonical object identifier. |
| `ENTITY` | Identify the responsible/numbering Entity context in a human-readable form. | Entity ownership/context must still be canonical metadata; the code alone is not legal identity. |
| `PROJECT` | Identify the Project numbering context so project documents remain recognizable in registers and exchanges. | The project code is not the canonical Project `objectUID` and does not establish project relationships. |
| `DISCIPLINE` | Identify the primary subject-responsibility discipline for routing/search and human interpretation. | Must map to an approved discipline term; do not infer discipline solely from folder location. |
| `DOCTYPE` | Identify the primary business document type, such as drawing, specification, report, or register. | File format does not determine document type; the controlled taxonomy/metadata is authoritative. |
| `SEQUENCE` | Provide a unique serial component within the defined numbering namespace. | Sequence gaps are acceptable; issued numbers must never be recycled or renumbered for cosmetic reasons. |

## 4. Rules

1. Once issued, an enterprise document number is immutable.
2. A number is never reused, even if the document is withdrawn, voided, superseded, or disposed.
3. Gaps in a sequence are acceptable and preferable to reuse.
4. Revision identifiers are not part of the immutable document number itself.
5. The numbering service or controlled register is authoritative for issuance.
6. Folder paths and filenames may display the number but do not establish its validity.
7. Each segment must have a defined purpose and controlled source; decorative/unexplained segments are prohibited.
8. Where a business context does not apply, use a specifically governed pattern rather than filling a segment with misleading placeholder values.

## 5. Revision display

A controlled filename may append a revision:

```text
ABC-PRJ001-ENG-DRG-000245_C02_Equipment-Layout.pdf
```

The stable document number remains:

```text
ABC-PRJ001-ENG-DRG-000245
```

`C02` exists to identify the revision representation for human use; it is not part of the immutable enterprise document number and must correspond to canonical revision metadata.

## 6. Design principle

A document-number segment should exist only when it communicates a stable business distinction that users, registers, external parties, or controlled processes genuinely need. Information better handled as metadata should not be forced into increasingly long document numbers.
