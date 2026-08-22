# 04 — Enterprise Document Numbering

## 1. Purpose

Enterprise document numbers provide stable, human-readable business identifiers for controlled documents. They are separate from EIOS canonical `objectUID`s.

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

## 3. Rules

1. Once issued, an enterprise document number is immutable.
2. A number is never reused, even if the document is withdrawn, voided, or disposed.
3. Gaps in a sequence are acceptable and preferable to reuse.
4. Revision identifiers are not part of the immutable document number itself.
5. The numbering service or controlled register is authoritative for issuance.
6. Folder paths and filenames may display the number but do not establish its validity.

## 4. Revision display

A controlled filename may append a revision:

```text
ABC-PRJ001-ENG-DRG-000245_C02_Equipment-Layout.pdf
```

The stable document number remains:

```text
ABC-PRJ001-ENG-DRG-000245
```
