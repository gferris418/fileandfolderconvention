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

A syntactically valid name is not enough. Every structural folder must also have an approved purpose and boundary recorded in the Purpose & Boundary Register.

## 2. Purpose requirement

Before a structural folder is adopted, its definition MUST answer all of the following:

1. **Why does this folder exist?**
2. **What business process, decision, obligation, or information need does it support?**
3. **What information normally belongs there?**
4. **What information explicitly does not belong there?**
5. **Which parent node and business scope does it serve?**
6. **Is it a permanent structural node, a metadata-driven view, or a temporary governed exception?**

The normative definitions for current nodes are maintained in `15-purpose-register.md`.

Local additions must record at least:

```text
ItemName
ParentNode
Purpose
TypicalContents
ExclusionsOrBoundary
OwnerOrSteward
EffectiveFrom
ReviewDate (if temporary/experimental)
```

A folder must not be created merely because users are unsure where information belongs.

## 3. Dynamic business folders

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

These codes are navigational/business identifiers, not EIOS `objectUID`s. The purpose of a dynamic business root is to provide a human-facing workspace/view for the corresponding canonical business context, not to create that canonical object.

## 4. Allowed characters

Normative folder names should use:
- uppercase Latin letters `A-Z` for controlled structural folders;
- digits `0-9`;
- underscore `_` as the preferred word separator;
- hyphen `-` only when it is part of an established business code.

Provider-reserved characters must be avoided in provider-neutral templates.

## 5. Prohibited or suspect patterns

Avoid generic folders whose labels do not communicate a bounded purpose, including:

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
General
Other
```

A term such as `OTHER` may only be used where a controlled taxonomy explicitly defines its scope and governance. It must never become an uncontrolled catch-all.

## 6. Numeric prefixes

Use two-digit prefixes for stable ordering. Reserve `99_` for a closed/archive projection. Do not continuously renumber existing folders simply because a new category is inserted; use an available number or revise the template through governance.

The numeric prefix expresses presentation order only. The business purpose comes from the registered definition, not from the number.

## 7. Maximum depth

Prefer shallow, metadata-assisted structures. A default design target is no more than five structural levels below the business-object root. Provider mappings may impose stricter limits.

Before adding another level, confirm that the distinction cannot be represented more clearly using canonical metadata, a controlled view, or an existing purpose-defined node.

## 8. Dates in folder names

Do not use dates as the primary organizing hierarchy unless the business process is intrinsically chronological. Where required, use ISO format:

```text
YYYY
YYYY-MM
YYYY-MM-DD
```

Date-based nodes must still have a defined process purpose (for example, period reporting or chronological evidence intake) rather than existing solely because a date is convenient for browsing.
