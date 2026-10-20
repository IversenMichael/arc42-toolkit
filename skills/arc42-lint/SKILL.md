---
name: arc42-lint
version: 2.0.0
description:
  Checks the cross-section consistency of arc42 documentation by name, as the
  official arc42 template relates its sections. Verifies that building blocks,
  communication partners, quality goals and decisions are referenced
  consistently between sections and reports every mismatch with its location.
---

# arc42 Consistency Check

You check an arc42 architecture documentation for consistency between its
sections. arc42 prescribes no identifier scheme; sections refer to each other by
the names of building blocks, communication partners, quality goals and
decisions. This check works on those names.

The script `scripts/arc42-lint.py` in this repository checks identifier
conventions (IF-xx, QS-xx, RISK-xx, ADR-xxx) of an earlier toolkit version. It
does not apply to documentation written with the current skills; apply the rules
below manually.

## Step 1: Locate the Documentation

Ask the user, unless already clear, which files hold the sections. Read them
directly.

## Step 2: Apply the Rules

| Rule | Sections   | Check                                                                                                       |
| ---- | ---------- | ----------------------------------------------------------------------------------------------------------- |
| 1    | 3 and 5    | Every communication partner in Section 3 appears at Section 5 level 1, and vice versa                       |
| 2    | 5 and 6    | Every building block named in a Section 6 scenario exists in Section 5                                      |
| 3    | 5 and 7    | Every building block of Section 5 is mapped to an infrastructure element in Section 7                       |
| 4    | 5 and 8    | Every building block named in Section 8 exists in Section 5                                                 |
| 5    | 1.2 and 4  | Every quality goal of Section 1.2 has a row or entry in Section 4                                           |
| 6    | 1.2 and 10 | Every quality goal of Section 1.2 is referenced in Section 10                                               |
| 7    | 4 and 9    | Every decision Section 4 refers to for details exists in Section 9, and Section 9 does not repeat Section 4 |
| 8    | 3 and 6    | Every external participant in a Section 6 scenario is a communication partner in Section 3                  |
| 9    | 12 and all | Every term defined in Section 12 is used with that spelling; synonyms it rules out do not appear            |

For each rule: collect the names from the first section, search for them in the
second section, and record every name that is missing or spelled differently,
with file and line. Skip a rule and say so when one of its sections does not
exist.

## Step 3: Report Findings

```markdown
## arc42 Consistency Report

Files: [list]

| Rule | Sections | Status             | Details                                |
| ---- | -------- | ------------------ | -------------------------------------- |
| 1    | 3 and 5  | PASS / FAIL / SKIP | [e.g. "Billing System missing in 5.1"] |
| ...  |          |                    |                                        |

### Issues

- [Rule N] [file:line]: [name] is [missing from | spelled differently in]
  [section]

### Verdict

[Consistent | N issues to resolve]
```

## Step 4: Offer to Fix

For each issue, offer to align the sections with the relevant arc42-section-NN
skill. Do not change files without the user's agreement.

Based on <https://docs.arc42.org> and the arc42 template by Dr. Gernot Starke and
Dr. Peter Hruschka (CC BY-SA 4.0).
