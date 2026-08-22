# 02 — Folder Naming Standard

## 1. General format

Normative folder names should use:

```text
[NN]_[UPPER_SNAKE_CASE_NAME]
```

Examples:

```text
01_PROJECT_CONTROL
02_CONTRACT_COMMERCIAL
10_HANDOVER_CLOSEOUT
99_ARCHIVE
```

## 2. Dynamic business folders

Folders representing a business object should use a stable business code followed by a short readable name:

```text
[PROJECT_CODE]_[SHORT_PROJECT_NAME]
[OPPORTUNITY_CODE]_[SHORT_NAME]
[CONTRACT_CODE]_[SHORT_TITLE]
[ENTITY_CODE]_[SHORT_ENTITY_NAME]
```

Examples:

```text
PRJ001_PORT_SIMULATOR
OPP024_NAVIGATION_SYSTEM
CTR018_MAINTENANCE_AGREEMENT
```

These codes are navigational/business identifiers, not EIOS `objectUID`s.

## 3. Allowed characters

Normative folder names should use:
- uppercase Latin letters `A-Z` for controlled structural folders;
- digits `0-9`;
- underscore `_` as the preferred word separator;
- hyphen `-` only when it is part of an established business code.

Provider-reserved characters must be avoided in provider-neutral templates.

## 4. Prohibited patterns

Avoid:

```text
New Folder
Misc
Various
Temp
Final
Old
Stuff
Documents
Project Files
```

unless such terms are explicitly defined by a controlled template.

## 5. Numeric prefixes

Use two-digit prefixes for stable ordering. Reserve `99_` for a closed/archive projection. Do not continuously renumber existing folders simply because a new category is inserted; use an available number or revise the template through governance.

## 6. Maximum depth

Prefer shallow, metadata-assisted structures. A default design target is no more than five structural levels below the business-object root. Provider mappings may impose stricter limits.

## 7. Dates in folder names

Do not use dates as the primary organizing hierarchy unless the business process is intrinsically chronological. Where required, use ISO format:

```text
YYYY
YYYY-MM
YYYY-MM-DD
```
