# Conformance

A conforming implementation must preserve the distinction between logical organization and canonical EIOS semantics.

Initial test classes:

1. Folder naming pattern checks for normative templates.
2. File-name linting for controlled-document examples.
3. Prohibited-name checks (`Final FINAL`, `Copy of Copy`, uncontrolled version noise).
4. Template completeness checks.
5. Provider-mapping tests proving that canonical identity is unchanged by path mapping.
6. Negative tests ensuring folder placement is not treated as authorization, retention, legal hold, or canonical identity.

The conformance suite will be expanded before this convention is promoted from draft to frozen v1.0.0.
