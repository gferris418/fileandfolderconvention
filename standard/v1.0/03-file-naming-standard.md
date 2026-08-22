# 03 — File Naming Standard

## 1. Preferred controlled-document pattern

```text
[EnterpriseDocumentNo]_[Revision]_[ShortTitle].[ext]
```

Example:

```text
ABC-PRJ001-ENG-DRG-000245_C02_Equipment-Layout.pdf
```

## 2. Minimum principles

- The file name is a display label, not canonical identity.
- The enterprise document number, when assigned, must never be reused.
- Revision labels in a file name must agree with the canonical revision metadata for controlled content.
- File extension must reflect the actual file format.
- Short titles should be readable and concise.

## 3. Uncontrolled/general files

Where no controlled enterprise document number exists, use a descriptive pattern such as:

```text
[BusinessCode]_[YYYY-MM-DD]_[ShortTitle].[ext]
```

Example:

```text
PRJ001_2026-08-22_Site-Coordination-Notes.docx
```

## 4. Avoid version noise

Prohibited examples include:

```text
Final Drawing latest UPDATED v7 FINAL FINAL.pdf
Proposal_new_latest2.docx
Copy of Copy of Contract.pdf
```

Use canonical revision/version metadata rather than uncontrolled adjectives.

## 5. Character guidance

Prefer letters, digits, hyphen, underscore, and period. Avoid provider-sensitive characters such as `\ / : * ? " < > |` in normative examples.

## 6. Dates

When a date is part of the display name, use `YYYY-MM-DD`.

## 7. Personal names

Do not put personal names into filenames merely to indicate ownership or workflow state. Ownership, author, reviewer, and approver should be metadata where available.
